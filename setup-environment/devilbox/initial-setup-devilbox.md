# Devilbox setup machine

1 - Certifique-se de ter instalado o `Docker` e o `Docker Compose` na sua máquina bem como o `git`.

    Para instalar as dependências e configurá-las siga esse passo a passo - (Getting started)[https://devilbox.readthedocs.io/en/latest/getting-started/prerequisites.html]

2 - Siga o passo a passo para instalar o devilbox encontrado (nesse link)[https://devilbox.readthedocs.io/en/latest/getting-started/install-the-devilbox.html]

    Para o arquivo `.env` (passo 2.2) copie o conteúdo encontrado nesse (repositório)[./helpers/.env]

    Faça as alterações nesse arquivo de acordo com os próximos passos do guia

3 - Depois de tudo instalado, para o primeiro startup rode o comando sem especificar os containers a serem subidos para garantir que não há erros (lembre-se de estar sempre no diretório do devilbox para executar o comando):

`sh
docker-compose up
`

4 - Em algums OS é preciso parar o apache2 que roda por padrão na porta 80.

    Para verificar se o apache esta rodando execute:
    `sudo service apache2 status`

    Para parar o apache:
    `sudo service apache2 stop`

    Para evitar ter que parar o apache toda vez que o OS é iniciado você pode configurar para que ele não inicie, ou removê-lo completamente.
    Para removê-lo, execute:
    `sh
    sudo apt-get purge apache2 apache2-utils apache2.2-bin apache2-common
    sudo apt-get autoremove --purge
    `

5 - Se não houver erros, está tudo pronto para configurar o primeiro projeto, e para subir os containers basta executar o comando:

`sh
docker-compose up httpd php mysql
`

Para iniciar em segundo plano em vez disso:

`sh
docker-compose up -d httpd php mysql
`

Para parar os containers:

`sh
docker-compose stop
`