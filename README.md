# Tickets

# Funcionalidades

- Cadastro e login de usuário por formulário e por autenticação OAuth (Google, Facebook, Github) 

- Usuários
    - Administrador
        - Ver tabela com lista de todos os usuários cadastrados
        - Alocar apenas funcionário para função de administrador
        - Aprovar conta de funcionário (A conta de funcionário fica pendente quando cadastrada)
        - Desativar e deleta conta de cliente e funcionários
        - Exportar lista de admins, funcionários e clientes em arquivo pdf, excel e html
        - Criar conta para novo administrador
        - Visualizar gráfico com as estatísticas do sistema (pelo menos 5)

    - Funcionário
        - Ver tabela com lista de todos os usuários cadastrados
        - Responde tickets de clientes
        - Remover tickets
        - Desativa conta de clientes
        - Mudar status de tickets
    - Cliente
        - Envia ticket
        - Visualiza tabela com seus tickets
        - Mudar status de tickets

## Frameworks
- Laravel v8
- Bootstrap v5

## Comandos utilizados
```
composer require laravel/ui
php artisan ui:auth
php artisan ui bootstrap
npm install && npm run dev
composer require laravel/socialite
composer require maatwebsite/excel
composer require dompdf/dompdf
```

## Modelo do banco de dados
<img src="./docs/imgs/bd.png" width="500">

## Instalação
**Instale as dependências**
```
composer install --no-scripts
```
**Copie o arquivo .env.example para .env**
```
copy .env.example .env
```
**Crie uma nova chave para a aplicação** 
```
php artisan key:generate
```
**Configure o banco de dados no arquivo .env e rodar os migrations com:**
```
php artisan migrate
```
**Adicione e configure as variáveis no arquivo .env para fazer login via rede social, google..**
Pesquise como pegar essas ids de cada rede social
```env
GITHUB_CLIENT_ID=cliente_id_aqui
GITHUB_CLIENT_SECRET=client_secret_aqui
GITHUB_CALLBACK_URL=http://localhost:8000/auth/github/callback

FACEBOOK_CLIENT_ID=cliente_id_aqui
FACEBOOK_CLIENT_SECRET=client_secret_aqui
FACEBOOK_CALLBACK_URL=http://localhost:8000/auth/facebook/callback

GOOGLE_CLIENT_ID=cliente_id_aqui
GOOGLE_CLIENT_SECRET=client_secret_aqui
GOOGLE_CALLBACK_URL=http://localhost:8000/auth/google/callback
```
**Iniciando a aplicação**
```
php artisan serve
```

Se o a variável 'APP_ENV' do arquivo .env tiver como 'APP_ENV=production' vai ser forçado o site para 'https://' se tiver 'APP_ENV=local' vai ser 'http://'

## Factories
Inserindo múltiplos registros “aleatórios” dentro do Banco de Dados. 
Antes de executar esse comando, acesse a págna inicial do site e crie uma conta de administrador
```
php artisan db:seed
```
