- [Краткая характеристика функционала файлов, представленных на странице](#краткая-характеристика-функционала-файлов-представленных-на-странице)
- [Каталог .\\src\\helpers\\](#каталог-srchelpers)
  - [**.\\src\\helpers\\index.js**](#srchelpersindexjs)
  - [**.\\src\\helpers\\fake-backend.js**](#srchelpersfake-backendjs)
  - [**.\\src\\helpers\\fetch-wrapper.js**](#srchelpersfetch-wrapperjs)
  - [**.\\src\\helpers\\router.js**](#srchelpersrouterjs)
- [Каталог: .\\src\\stores](#каталог-srcstores)
  - [**.\\src\\stores\\index.js**](#srcstoresindexjs)
  - [**.\\src\\stores\\users.store.js**](#srcstoresusersstorejs)
  - [**.\\src\\stores\\auth.store.js**](#srcstoresauthstorejs)
- [Каталог: .\\src\\views](#каталог-srcviews)
  - [**.\\src\\views\\index.js**](#srcviewsindexjs)
  - [**.\\src\\views\\LoginView.vue**](#srcviewsloginviewvue)
  - [**.\\src\\views\\HomeView.vue**](#srcviewshomeviewvue)
- [Каталог: .\\src](#каталог-src)
  - [**.\\src\\App.vue**](#srcappvue)
  - [**.\\src\\main.js**](#srcmainjs)
- [Каталог .\\](#каталог-)
  - [**.\\index.html**](#indexhtml)

# Краткая характеристика функционала файлов, представленных на странице
- **main.js**: Главный файл JavaScript, который инициализирует Vue-приложение, подключает маршрутизатор и хранилище состояний.
- **router.js**: Файл содержит настройки маршрутизатора для Vue-приложения, определяя маршруты и перенаправления в зависимости от статуса аутентификации пользователя.
- **fake-backend.js**: Этот файл имитирует бэкенд сервер с использованием JavaScript. Он перехватывает HTTP-запросы и возвращает фиктивные ответы, имитируя работу реального API. В нем определены функции для аутентификации пользователей и получения списка пользователей.
- **fetch-wrapper.js**: Этот файл предоставляет обертку для стандартной функции `fetch` для упрощения отправки HTTP-запросов. Он добавляет необходимые заголовки авторизации и обрабатывает ответы от API.
- **auth.store.js**: Этот файл использует библиотеку Pinia для создания хранилища состояний, которое управляет процессом аутентификации пользователя, включая вход в систему и выход из нее.
- **users.store.js**: Здесь определено хранилище для управления данными пользователей, включая загрузку списка пользователей с сервера.
- **HomeView.vue и LoginView.vue**: Эти файлы являются компонентами Vue, которые представляют домашнюю страницу и страницу входа соответственно.

# Каталог .\src\helpers\
##  **.\src\helpers\index.js**
```javascript
// Файл: .\src\helpers\index.js
export * from './fake-backend';
export * from './fetch-wrapper';
export * from './router';
```

## **.\src\helpers\fake-backend.js** 
```javascript
// Файл: **.\src\helpers\fake-backend.js**

export { fakeBackend };

function fakeBackend() {
    let users = [{ id: 1, username: 'test', password: 'test', firstName: 'Test', lastName: 'User' }];
    let realFetch = window.fetch;
    window.fetch = function (url, opts) {
        return new Promise((resolve, reject) => {
            // wrap in timeout to simulate server api call
            setTimeout(handleRoute, 500);

            function handleRoute() {
                switch (true) {
                    case url.endsWith('/users/authenticate') && opts.method === 'POST':
                        return authenticate();
                    case url.endsWith('/users') && opts.method === 'GET':
                        return getUsers();
                    default:
                        // pass through any requests not handled above
                        return realFetch(url, opts)
                            .then(response => resolve(response))
                            .catch(error => reject(error));
                }
            }

            // route functions

            function authenticate() {
                const { username, password } = body();
                const user = users.find(x => x.username === username && x.password === password);

                if (!user) return error('Username or password is incorrect');

                return ok({
                    id: user.id,
                    username: user.username,
                    firstName: user.firstName,
                    lastName: user.lastName,
                    token: 'fake-jwt-token'
                });
            }

            function getUsers() {
                if (!isAuthenticated()) return unauthorized();
                return ok(users);
            }

            // helper functions

            function ok(body) {
                resolve({ ok: true, text: () => Promise.resolve(JSON.stringify(body)) })
            }

            function unauthorized() {
                resolve({ status: 401, text: () => Promise.resolve(JSON.stringify({ message: 'Unauthorized' })) })
            }

            function error(message) {
                resolve({ status: 400, text: () => Promise.resolve(JSON.stringify({ message })) })
            }

            function isAuthenticated() {
                return opts.headers['Authorization'] === 'Bearer fake-jwt-token';
            }

            function body() {
                return opts.body && JSON.parse(opts.body);
            }
        });
    }
}
```

## **.\src\helpers\fetch-wrapper.js**
```javascript
// Файл: .\src\helpers\fetch-wrapper.js
import { useAuthStore } from '@/stores';

export const fetchWrapper = {
    get: request('GET'),
    post: request('POST'),
    put: request('PUT'),
    delete: request('DELETE')
};

function request(method) {
    return (url, body) => {
        const requestOptions = {
            method,
            headers: authHeader(url)
        };
        if (body) {
            requestOptions.headers['Content-Type'] = 'application/json';
            requestOptions.body = JSON.stringify(body);
        }
        return fetch(url, requestOptions).then(handleResponse);
    }
}

// helper functions

function authHeader(url) {
    // return auth header with jwt if user is logged in and request is to the api url
    const { user } = useAuthStore();
    const isLoggedIn = !!user?.token;
    const isApiUrl = url.startsWith(import.meta.env.VITE_API_URL);
    if (isLoggedIn && isApiUrl) {
        return { Authorization: `Bearer ${user.token}` };
    } else {
        return {};
    }
}

function handleResponse(response) {
    return response.text().then(text => {
        const data = text && JSON.parse(text);
        
        if (!response.ok) {
            const { user, logout } = useAuthStore();
            if ([401, 403].includes(response.status) && user) {
                // auto logout if 401 Unauthorized or 403 Forbidden response returned from api
                logout();
            }

            const error = (data && data.message) || response.statusText;
            return Promise.reject(error);
        }

        return data;
    });
}    
```

## **.\src\helpers\router.js**
```javascript
// Файл: .\src\helpers\router.js
import { createRouter, createWebHistory } from 'vue-router';

import { useAuthStore } from '@/stores';
import { HomeView, LoginView } from '@/views';

export const router = createRouter({
    history: createWebHistory(import.meta.env.BASE_URL),
    linkActiveClass: 'active',
    routes: [
        { path: '/', component: HomeView },
        { path: '/login', component: LoginView }
    ]
});

router.beforeEach(async (to) => {
    // redirect to login page if not logged in and trying to access a restricted page
    const publicPages = ['/login'];
    const authRequired = !publicPages.includes(to.path);
    const auth = useAuthStore();

    if (authRequired && !auth.user) {
        auth.returnUrl = to.fullPath;
        return '/login';
    }
});
```

# Каталог: .\src\stores
## **.\src\stores\index.js**
```javascript
// Файл: .\src\stores\index.js
export * from './auth.store';
export * from './users.store';
```
## **.\src\stores\users.store.js**
```javascript
// Файл: .\src\stores\users.store.js
import { defineStore } from 'pinia';

import { fetchWrapper } from '@/helpers';

const baseUrl = `${import.meta.env.VITE_API_URL}/users`;

export const useUsersStore = defineStore({
    id: 'users',
    state: () => ({
        users: {}
    }),
    actions: {
        async getAll() {
            this.users = { loading: true };
            fetchWrapper.get(baseUrl)
                .then(users => this.users = users)
                .catch(error => this.users = { error })
        }
    }
});
```
## **.\src\stores\auth.store.js**
```javascript
// Файл: .\src\stores\auth.store.js
import { defineStore } from 'pinia';

import { fetchWrapper, router } from '@/helpers';

const baseUrl = `${import.meta.env.VITE_API_URL}/users`;

export const useAuthStore = defineStore({
    id: 'auth',
    state: () => ({
        // initialize state from local storage to enable user to stay logged in
        user: JSON.parse(localStorage.getItem('user')),
        returnUrl: null
    }),
    actions: {
        async login(username, password) {
            const user = await fetchWrapper.post(`${baseUrl}/authenticate`, { username, password });

            // update pinia state
            this.user = user;

            // store user details and jwt in local storage to keep user logged in between page refreshes
            localStorage.setItem('user', JSON.stringify(user));

            // redirect to previous url or default to home page
            router.push(this.returnUrl || '/');
        },
        logout() {
            this.user = null;
            localStorage.removeItem('user');
            router.push('/login');
        }
    }
});
```

# Каталог: .\src\views
## **.\src\views\index.js**
```javascript
// Файл: .\src\views\index.js
export { default as HomeView } from './HomeView.vue';
export { default as LoginView } from './LoginView.vue';
```

## **.\src\views\LoginView.vue**
```javascript
// Файл: .\src\views\LoginView.vue
<script setup>
import { Form, Field } from 'vee-validate';
import * as Yup from 'yup';

import { useAuthStore } from '@/stores';

const schema = Yup.object().shape({
    username: Yup.string().required('Username is required'),
    password: Yup.string().required('Password is required')
});

function onSubmit(values, { setErrors }) {
    const authStore = useAuthStore();
    const { username, password } = values;

    return authStore.login(username, password)
        .catch(error => setErrors({ apiError: error }));
}
</script>

<template>
    <div>
        <div class="alert alert-info">
            Username: test<br />
            Password: test
        </div>
        <h2>Login</h2>
        <Form @submit="onSubmit" :validation-schema="schema" v-slot="{ errors, isSubmitting }">
            <div class="form-group">
                <label>Username</label>
                <Field name="username" type="text" class="form-control" :class="{ 'is-invalid': errors.username }" />
                <div class="invalid-feedback">{{errors.username}}</div>
            </div>            
            <div class="form-group">
                <label>Password</label>
                <Field name="password" type="password" class="form-control" :class="{ 'is-invalid': errors.password }" />
                <div class="invalid-feedback">{{errors.password}}</div>
            </div>            
            <div class="form-group">
                <button class="btn btn-primary" :disabled="isSubmitting">
                    <span v-show="isSubmitting" class="spinner-border spinner-border-sm mr-1"></span>
                    Login
                </button>
            </div>
            <div v-if="errors.apiError" class="alert alert-danger mt-3 mb-0">{{errors.apiError}}</div>
        </Form>
    </div>
</template>
```
## **.\src\views\HomeView.vue**
```javascript
// Файл: .\src\views\HomeView.vue
<script setup>
import { storeToRefs } from 'pinia';

import { useAuthStore, useUsersStore } from '@/stores';

const authStore = useAuthStore();
const { user: authUser } = storeToRefs(authStore);

const usersStore = useUsersStore();
const { users } = storeToRefs(usersStore);

usersStore.getAll();
</script>

<template>
    <div>
        <h1>Hi {{authUser?.firstName}}!</h1>
        <p>You're logged in with Vue 3 + Pinia & JWT!!</p>
        <h3>Users from secure api end point:</h3>
        <ul v-if="users.length">
            <li v-for="user in users" :key="user.id">{{user.firstName}} {{user.lastName}}</li>
        </ul>
        <div v-if="users.loading" class="spinner-border spinner-border-sm"></div>
        <div v-if="users.error" class="text-danger">Error loading users: {{users.error}}</div>
    </div>
</template>
```

# Каталог: .\src
## **.\src\App.vue**
```javascript
// Файл: .\src\App.vue
<script setup>
import { RouterLink, RouterView } from 'vue-router';

import { useAuthStore } from '@/stores';

const authStore = useAuthStore();
</script>

<template>
    <div class="app-container bg-light">
        <nav v-show="authStore.user" class="navbar navbar-expand navbar-dark bg-dark">
            <div class="navbar-nav">
                <RouterLink to="/" class="nav-item nav-link">Home</RouterLink>
                <a @click="authStore.logout()" class="nav-item nav-link">Logout</a>
            </div>
        </nav>
        <div class="container pt-4 pb-4">
            <RouterView />
        </div>
    </div>
</template>

<style>
@import '@/assets/base.css';
</style>
```

## **.\src\main.js**
```javascript
// Файл: .\src\main.js
import { createApp } from 'vue';
import { createPinia } from 'pinia';

import App from './App.vue';
import { router } from './helpers';

// setup fake backend
import { fakeBackend } from './helpers';
fakeBackend();

const app = createApp(App);

app.use(createPinia());
app.use(router);

app.mount('#app');
```

# Каталог .\
## **.\index.html**
```html
<!-- Файл: .\index.html -->
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <link rel="icon" href="/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vue 3 + Pinia - JWT Authentication Example</title>

    <!-- bootstrap css -->
    <link href="//netdna.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet" />
</head>

<body>
    <div id="app"></div>
    <script type="module" src="/src/main.js"></script>

    <!-- credits -->
    <div class="text-center mt-4">
        <p>
            <a href="https://jasonwatmore.com/post/2022/05/26/vue-3-pinia-jwt-authentication-tutorial-example">Vue 3 + Pinia - JWT Authentication Example & Tutorial</a>
        </p>
        <p>
            <a href="https://jasonwatmore.com">JasonWatmore.com</a>
        </p>
    </div>
</body>

</html>
```