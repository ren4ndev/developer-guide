# Setup Project Nginx

1 - Clonar repositório para o caminho `/var/www/<nomedoprojeto>`

`git clone <repo> /var/www/<nomedoprojeto>/`

2 - Para configurar um site novo entre na pasta `cd /etc/nginx/sites-enabled`:

3 - Crie um arquivo com nome do site que você quer configurar:

`sudo touch <nome_arquivo>`

4 - Dentro arquivo adicione o conteúdo abaixo:

```
server {
  set $prod_domain <dominio_producao>; //site.com.br

  listen 80;
  server_name <dominio_local>; //site.local
  root /var/www/<site_folder>;

  include server.conf;
}
```

5 - Adicionar host no arquivo `/etc/hosts`:

`code /etc/hosts`

```
127.0.0.1	localhost
127.0.0.1	drd.local
127.0.0.1 univale.local //Linha adicionada

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters

```

6 - Entrar na raiz do projeto e executar o `composer install` e `npm install`

7 - Criar branch no formato: 

`care_[numerocard]_descricao`

8 - Configurando banco de dados no arquivo `wp-config.php`:

```
// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define( 'DB_NAME', '<nomedobanco>' );

/** MySQL database username */
define( 'DB_USER', 'admin' );

/** MySQL database password */
define( 'DB_PASSWORD', '<senha>' );

/** MySQL hostname */
define( 'DB_HOST', 'localhost' );

/** Database Charset to use in creating database tables. */
define( 'DB_CHARSET', 'utf8' );

/** The Database Collate type. Don't change this if in doubt. */
define( 'DB_COLLATE', '' );
```

```
define('WP_SITEURL', 'http://<url_local>/');
define('WP_HOME', 'http://<url_local>/');
```

9 - Com as dependências intaladas acessar ambiente de homologação ou projeto e exportar database

10 - Na interface do MySQL Workbench acessar o usuário e ir em Server>>Data import

Selecionar **"Import from Self-Contained File"** e escolher _path_ do database baixado.

Clicar em _New_ na barra **"Default Schema to be Imported to"** e digitar o nome do _db_ e clicar em **"Start Import"**

Aguardar importação ser feita.

Refresh schemas.

11 - Rodar o comando `sudo service nginx restart`

12 - Caso seja multisite: (Hostingator Multisites)[https://www.hostinger.com.br/tutoriais/como-ativar-multisite-wordpress/]

`define( 'WP_ALLOW_MULTISITE', true );`

