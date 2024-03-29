# Laravel6 Vuejs Kickstarter

A Laravel 6 Single Page Application boilerplate using Vue.js 2.6, GraphQL, Bootstrap 4, TypeScript, Sass and Pug with:

* A users CRUD if the current user is an admin written in RESTful and GraphQL.
* i18n for English, Portuguese and Spanish, based on browser language settings.
* Authentication using JWT.
* WebSockets with Laravel Echo and Pusher.
* Vue component tests using Jest and API tests using PHPUnit.
* Dockerfile configured with PHP 7.2, Node.js 12 and Composer, with MySQL and phpMyAdmin on Docker Compose.

## Main dependencies

Front-end:

* [Vue](https://github.com/vuejs/vue)
* [VueRouter](https://github.com/vuejs/vue-router)
* [Vuex](https://github.com/vuejs/vuex)
* [vue-apollo](https://github.com/Akryum/vue-apollo)
* [Vue Auth](https://github.com/websanova/vue-auth)
* [vuex-i18n](https://github.com/dkfbasel/vuex-i18n)
* [vue-awesome](https://github.com/Justineo/vue-awesome)
* [Bootstrap 4](https://github.com/twbs/bootstrap)
* [BootstrapVue](https://github.com/bootstrap-vue/bootstrap-vue)
* [TypeScript](https://github.com/microsoft/typescript)
* [Pug](https://github.com/pugjs/pug)
* [Sass](https://github.com/sass/node-sass)
* [Laravel Echo](https://github.com/laravel/echo)
* [Laravel Mix](https://github.com/JeffreyWay/laravel-mix)
* [Jest](https://github.com/facebook/jest)

The TypeScript code tries to follow the [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript), the linters are already included and configured.

Back-end:

* [Laravel](https://github.com/laravel/laravel)
* [Laravel GraphQL](https://github.com/rebing/graphql-laravel)
* [jwt-auth](https://github.com/tymondesigns/jwt-auth)
* [laravel-vue-i18n-generator](https://github.com/martinlindhe/laravel-vue-i18n-generator)
* [PHPUnit](https://github.com/sebastianbergmann/phpunit)
* [Laravel Envoy](https://github.com/laravel/envoy)

## Steps to run it

### Docker

Run:

    docker-compose up --build

Just on the first time, after it starts run on another terminal:

    docker exec laravel6-vuejs-kickstarter bash -c "composer update && composer start"
    docker exec laravel6-vuejs-kickstarter bash -c "npm update && npm start"

The application will be available on http://localhost:8080 and the phpMyAdmin on http://localhost:8081

### Manual

Rename the .env.example file to .env, and fill it with your local info, then:

Install PHP and JavaScript dependencies:

    composer install
    npm install

Generate Laravel keys:

    php artisan key:generate

Generate JWT keys

    php artisan jwt:secret

Generate i18n string for Vue, based on Laravel i18n files:

    php artisan vue-i18n:generate

Migrate and seed the database:

    php artisan migrate --seed

Compile all the front-end stuff:

    npm run prod

Test:

    composer test
    npm test
