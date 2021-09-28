# Railway Laravel Starter
<img src="https://i.ibb.co/NyYLCbc/Laravel-Welcome-Page.png" />
<p align="middle">
<img src="https://img.shields.io/badge/Laravel-v8.x-red?style=for-the-badge&logo=laravel" />
<img src="https://img.shields.io/badge/Postgresql-26689A?style=for-the-badge&logo=postgresql&logoColor=white" />
<img src="https://img.shields.io/badge/Railway-0B0D0E?style=for-the-badge&logo=railway&logoColor=white" />
</p>

> This is (my) [Laravel](https://laravel.com/) starter app that connects to a Railway with Postgres database.
## 🚢 Deploy now
[![Deploy on Railway Test](https://railway.app/button.svg)](https://railway.app/new?template=https%3A%2F%2Fgithub.com%2Fabelchrist%2Frailway-laravel%2Ftree%2F8.x&plugins=postgresql)


## 💁‍♀️ How to use
- Install Railway CLI in terminal: `npm i -g @railway/cli`
- [Create a Railway project with the Postgres plugin](https://railway.app/project?plugins=postgresql) or just click `Deploy on Railway` button 
- if manually create Railway project, clone this project within terminal: `git clone https://github.com/AbelChrist/railway-laravel.git` or if using deploy button, clone it that project from your repository (github) to local
- In that cloned project, connect to your Railway project with `railway link` in terminal and select your project
- Set up your Railway variables project in https://railway.app/project/<YOUR-PROJECT-ID\>/variables (See `.env.railway` file for more detail)
-  To deploy your project on Railway, in terminal: `railway up`

## 📝 Notes
- **Dockerfile**: The `Dockerfile` and associated files in `docker/` are based on [Laravel Sail PHP 8.0](https://github.com/laravel/sail/tree/1.x/runtimes/8.0)
- **Plugin Config**: To connect to a Railway Plugin, Postgres for example, you will need to utilize the environment variables listed for that plugin in the [Railway Docs](https://docs.railway.app/). See the `.env.railway` for an example of using these with Postgres.
- **Web server port**: Railway dynamically assigns a port for your webserver. We grab the `$PORT` environment variable in `docker/start-container` to set this on Artisan `serve`
- **Logging**: Because the disk on Railway containers is ephemeral, we pipe the logs normally output to `storage/logs/laravel.log` to `stdout` (edited `config/logging.php`)
- **APP_KEY**: This starter will automatically generate the `APP_KEY` (`php artisan key:generate --show` in the `docker/start-container`) when deployed
- **Migrations**: This starter automatically runs migrations on deploy (in the `docker/start-container`)
- This is modified repository from https://github.com/railwayapp/starters/tree/master/examples/laravel
- Read [Railway Docs](https://docs.railway.app/)!
- If cloned this project to local you need to installing packages/dependencies and bit of configuration, to do so:
```bash
# in your project
composer install
npm install && npm run dev
copy .env.example .env
php artisan key:generate
```
