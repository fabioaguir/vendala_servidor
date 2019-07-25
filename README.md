# vendala_servidor
Projeto Servidor

versões
- PHP: "^7.1.3"
- Laravel: "5.7.*"

# Clonar do git
- Entrar no diretório do projeto
- executar o comando composer install
- php artisan key:generate

# Configuração Token
 - Adicione o provedor de serviços à providers no config/app.php arquivo de configuração da seguinte maneira:
'providers' => [
    ...
    Tymon\JWTAuth\Providers\LaravelServiceProvider::class,
]
- Execute o seguinte comando para publicar o arquivo de configuração do pacote:
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
- php artisan jwt:secret

# Configuração Cors
 - adicione Cors\ServiceProvider ao seu array de provedores config/app.php:
'providers' => [
    ...
    Barryvdh\Cors\ServiceProvider::class,
]
- Para permitir o CORS para todas as suas rotas, inclua o middleware HandleCors na propriedade $middleware da classe app/Http/Kernel.php:
protected $middleware = [
    // ...
    \Barryvdh\Cors\HandleCors::class,
];
- Rodar o comando para publicar o provider do cros
php artisan vendor:publish --provider="Barryvdh\Cors\ServiceProvider"

# Configuração Banco de Dados SQLite
- no arquivo .env deixar da seguinte forma os parâmetro de conexão com o banco de dados
DB_CONNECTION=sqlite
#DB_HOST=127.0.0.1
#DB_PORT=3306
#DB_DATABASE=homestead
#DB_USERNAME=homestead
#DB_PASSWORD=secret

- depois executar o seguinte comando:
touch database/database.sqlite
- Criar as tabelas de banco de dados, execute o comando:
php artisan migrate:refresh --seed


