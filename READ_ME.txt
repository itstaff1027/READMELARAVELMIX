MODIFICATION - HOSTINGER 

install composer in your laravel app

php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'e21205b207c3ff031906575712edab6f13eb0b361f2085f1f1237b7126d785e826a450292b6cfd1d64d92e6563bbde02') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"


add livewire by prompting this command in your laravel app 'composer requrie livewire/livewire'

php artisan db:seed

php artisan key:generate

php artisan migrate : if the app is FRESH

cp .env.example .env

nano .env then change databse name username and passworrd to your DB

nano .htaccess to add this line of code:
<!-- <IfModule mod_rewrite.c>
	RewriteEngine On
	RewriteRule ^(.*)$ public/$1 [L]
</IfModule> -->

then do php artisan serve to test - go to register then register an account and see if it will work.
use cdn alpine js and tailwind to work with your designs:remove @vite([])

LARAVEL MIX in HOSTINGER WORKS

yarn add laravel-mix --dev

rename vite.config.js to webpack.mix.js if .js not works rename the file into .cjs

then add this:

const mix = require("laravel-mix");

mix.js("resources/js/app.js", "public/js").postCss(
    "resources/css/app.css",
    "public/css",
    [require("tailwindcss")]
);

then go to package.json:
change the scripts into this:

"dev": "npm run development",
"development": "mix",
"watch": "mix watch",
"watch-poll": "mix watch -- --watch-options-poll=1000",
"hot": "mix watch --hot",
"prod": "npm run production",
"production": "mix --production"

then prompt this:

yarn run dev

if there is error in bootstrap then do this:
go to resources/js/app.js change the import './bootstrap' to import './bootstrap.js'

if error occured about postcss.js rename the file type to .cjs

if there is error about export then chnage the postcss.js:
expoprt default to module.exports =