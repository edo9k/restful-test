# RESTful Test

Teste inicial para desenvolvimento de aplicação com banco MySQL, backend Laravel e frontend React.


## Modelo Article

Só possui  as propriedades título (title) e corpo (body) editáveis.
Também existem propriedades chamadas created_at e updated_at que são geradas/atualizadas automaticamente pelo framework.

## Rotas disponívels:

+-----------+------------------------+-----------------+------------------------------------------------+
| Method    | URI                    | Name            | Action                                         |
|-----------+------------------------+-----------------+------------------------------------------------+
| GET|HEAD  | /                      |                 | Closure                                        |
| POST      | article                | article.store   | App\Http\Controllers\ArticleController@store   |
| GET|HEAD  | article                | article.index   | App\Http\Controllers\ArticleController@index   |
| GET|HEAD  | article/create         | article.create  | App\Http\Controllers\ArticleController@create  |
| DELETE    | article/{article}      | article.destroy | App\Http\Controllers\ArticleController@destroy |
| PUT|PATCH | article/{article}      | article.update  | App\Http\Controllers\ArticleController@update  |
| GET|HEAD  | article/{article}      | article.show    | App\Http\Controllers\ArticleController@show    |
| GET|HEAD  | article/{article}/edit | article.edit    | App\Http\Controllers\ArticleController@edit    |
+-----------+------------------------+-----------------+------------------------------------------------+
