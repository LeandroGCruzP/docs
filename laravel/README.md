# Criando projeto Laravel com NOVA

## Criando projeto Laravel
```cmd
composer create-project laravel/laravel <name_project>
```

Com uma versão de Laravel especifica
```cmd
composer create-project laravel/laravel:^8.1 crud-nova --ignore-platform-reqs
```

#### Ver versão do Laravel
```cmd
php artisan -–version
```

#### Ver versão do Php
```cmd
php -–version
```

#### Rodando projeto
```cmd
php artisan serve
```

#### Vendo lista de rotas
```cmd
php artisan route:list
```

### Navegando pelo projeto
|             | Rota de pastas |
| ----------- | -------------- |
| Routes      | routes > web.php |
| Controllers | app > Http > Controllers |
| Views       | resources > view |
| Models      | app > Models |

### Controlador, migrações, modelos
#### Criando controller
> Exemplo: GameController
```cmd
php artisan make:controller <Name>Controller
```

#### Criando migrações
> Exemplo: create_game_table
```cmd
php artisan make:migration <method_name_table>
```

Rodar as migrations
```cmd
php artisan migrate
```

#### Criando modelos
> O nome é sempre em singular
```cmd
php artisan make:model <Name>
```

## NOVA
- [Instalando NOVA](https://nova.laravel.com/docs/3.0/installation.html#installing-nova)

> Se a versao da problema do php se deve incluir a tua versao com o simbolo |
```cmd
"require": {
    "php": "^7.3|^8.1",
    // ...
},
```

### Criando resources, lenses, actions, metrics, cards, tools, resource tools e dashboard

#### Criando resource
```cmd
php artisan nova:resource <name> --model="Model"
```

#### Criando lenses
```cmd
php artisan nova:lense <name>
```

#### Criando actions
```cmd
php artisan nova:action <name>
```

#### Criando metrics
> Se usa juntamente com o componente Card
```cmd
php artisan nova:value <name>
php artisan nova:trend <name>
php artisan nova:partition <name>
```

#### Criando cards
> Contem qualquer conteúdo, inclusive um componente metric
```cmd
php artisan nova:card <name>
```

#### Criando tools
```cmd
php artisan nova:tool <name>
```

#### Criando resource tools
```cmd
php artisan nova:resource-tool <name>
```

#### Criando dashboard
> Criar outro dashboard 
```cmd
php artisan nova:dashboard <name>
```

