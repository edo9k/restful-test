# RESTful Test

Teste inicial para desenvolvimento de aplicação com banco MySQL, backend Laravel e frontend React.



## Instalação

Necessário: Apache*, MySQL, PHP, Composer, Laravel, Git.
Recomendado: MySQL Workbench, GitKraken. (Facilitam o gerenciamento tanto do banco de dados quanto de commits, branches e outras funções do Git.)

* outras opções de servidor web podem ser usadas, mas só tenho alguma experiência com esse.


### Instalando pré-requisitos:


Apache, PHP, MySQL e Git

`sudo apt install git apache2 mysql-server php php-pear php-mcrypt php-mysql`


Composer 

```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('SHA384', 'composer-setup.php') === '544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php --install-dir=bin
php -r "unlink('composer-setup.php');"
```

MySQL Workbench

`sudo apt install mysql-workbench`

GitKraken

```
wget https://release.gitkraken.com/linux/gitkraken-amd64.deb
sudo dpkg -i gitkraken-amd64.deb
```

## Configurando o projeto

Baixando via GitKraken 

Faça login no GitKraken usando sua conta do GitHub.com, encontre o projeto, escolha a pasta para o qual ele será baixado. 

Baixando via Git

`git clone https://github.com/edo9k/restful-test`

Na raiz do projeto, copie o arquivo `.env.example` para `.env`. (`cp .env.example .env`)

Rode o comando abaixo apra setar a APP_KEY do projeto.
`php artisan key:gererate`

Depois instale os pacotes usados no projeto via composer
`composer install`

Crie um banco MySQL vazio e um usuário que tenha permissões totais dentro desse banco. 
```
DB_DATABASE=nome_do_banco
DB_USERNAME=usuario_do_banco
DB_PASSWORD=senha_desse_usuario
```

Depois rode as migrações dentro do banco pelo comando migrate do laravel
`php artisan migrate`

Popule o banco com dados teste
`php artisan db:seed`

Finalmente, para rodar o projeto, use o comando serve.
`php artisan serve`



## Modelo Article

Só possui  as propriedades título (title) e corpo (body) editáveis.
Também existem propriedades chamadas created_at e updated_at que são geradas/atualizadas automaticamente pelo framework (além do índice, claro).

## Modelo User

Usuários possuem nome (name), email (email), hash de senha gerado com o algorítmo bcrypt (password), tokens de acesso (remember_token) e registro de criação e atualização (created_at e updated_at). 

## Rotas disponívels:

 Method    | URI                    | Name            | Action                                         
:----------|:-----------------------|:----------------|:-----------------------------------------------
 GET/HEAD  | /                      |                 | Closure                                        
 POST      | article                | article.store   | App\Http\Controllers\ArticleController@store   
 GET/HEAD  | article                | article.index   | App\Http\Controllers\ArticleController@index   
 GET/HEAD  | article/create         | article.create  | App\Http\Controllers\ArticleController@create  
 DELETE    | article/{article}      | article.destroy | App\Http\Controllers\ArticleController@destroy 
 PUT/PATCH | article/{article}      | article.update  | App\Http\Controllers\ArticleController@update  
 GET/HEAD  | article/{article}      | article.show    | App\Http\Controllers\ArticleController@show    
 GET/HEAD  | article/{article}/edit | article.edit    | App\Http\Controllers\ArticleController@edit    

