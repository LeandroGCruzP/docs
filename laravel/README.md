# Criando projeto Laravel com Laravel NOVA

<details open>
<summary><b>Tabela de conteúdos</b></summary>

- [Requisitos de instalação](#requisitos-de-instalação)
- [Criando projeto Laravel](#criando-projeto-laravel)
- [Adicionando NOVA ao projeto](#adicionando-NOVA-ao-projeto)
- [Fazer rodar o projeto em NOVA](#fazer-rodar-o-projeto-em-NOVA)
- [Criando novo usuario para fazer Login](#criando-novo-usuario-para-fazer-Login)
- [Criando novo resource da app](#criando-novo-resource-da-app)
- [Criando um novo filter para as tabelas](#criando-um-novo-filter-para-as-tabelas)
- [Navegando pelo projeto](#navegando-pelo-projeto)
</details>

### **Requisitos de instalação**
- [Composer](https://getcomposer.org/download/)
- [Laragon](https://laragon.org/download/)

------------------------------

### **Criando projeto Laravel**
Criando com a versão lastest
```shell
composer create-project laravel/laravel <name_project>
```

Com uma versão de Laravel especifica
```shell
composer create-project laravel/laravel:^8.1 <name_project> --ignore-platform-reqs
```

Ver versão do Laravel
```shell
php artisan -–version
```

Ver versão do Php
```shell
php -–version
```

### **Adicionando NOVA ao projeto**
- [Instalando NOVA](https://nova.laravel.com/docs/3.0/installation.html#installing-nova)

Se a versão do php dar problema se deve incluir a tua versão com o simbolo | ```composer.json```
```
"require": {
    "php": "^7.3|^8.1",
},
```

Adicionar a pasta /nova dentro do .gitignore da raiz do projeto ```.gitignore```
```
nova
```

------------------------------

### **Fazer rodar o projeto em NOVA**
1. Ligar o laragon e pressionar "Start All"
2. Pressionar "Database" e fazer duplo click em "Laragon.MySQL"
3. Novamento em Laragon.MySQL clicar com o botão direito e ir até a opção "Criar Novo" > "Banco de Dados"
4. Preencher o campo "Nome" e clicar em "Ok"
5. Copiar o nome prenchido anteriormente e colar no arquivo ```.env``` da raiz do projeto
    ```
    DB_DATABASE=<name_db>
    ```
6. Depois de configurar o .env roda a migration de usuário que já vem criado
    ```shell
    php artisan migrate
    ```
7. Para testar se está tudo certo se pode revisar todas as rotas da aplicação
    ```shell
    php artisan route:list
    ```
8. Logo ir até a tela de [login](http://127.0.0.1:8000/nova/login) do Laravel NOVA

------------------------------

### **Criando novo usuario para fazer Login**
```shell
php artisan nova:user

Name: <your_name>
Email Address: <your_email>
Password: <your_password>
```

------------------------------

### **Criando novo resource da app**
Criando novo resource
```shell
php artisan nova:resource <Name>
```
```php artisan nova:resource Car```

Para criar a migration somente se necesita rodar o comando
```shell
php artisan migrate
```
Si se realizan nomas modificações na migration se deve rodar o comando novamente

------------------------------

### **Criando um novo filter para as tabelas**
Criando novo filter
```shell
php artisan nova:filter <NameFilter>
```
```php artisan nova:filter CarBrand```

------------------------------

### **Navegando pelo projeto**
|            | Rota de pastas |
| ---------- | -------------- |
| Resources  | app > Nova |
| Migrations | database > migrations |
| Models     | app > Models |
| Filters    | app > Nova > Filters |
