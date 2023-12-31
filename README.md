***
# PostgreSQL :    ![image](https://github.com/userdanixdev/PostgreSQL/assets/132594952/89bd1e1c-9aeb-4418-9f08-f13ff2765b45)

_Conceitos relativos oo banco de dados PostgreSQL:_
****
_Link para download do PostgreeSQL do software:_
https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
****
# Aferi-se a necessidade de realizar algumas configurações:
***
 __Configurar as variáveis de ambiente de acesso no Sistema Operacional Windows:__
1. Encontrar o diretório do software PostgreSQL:  `C:\Program Files\PostgreSQL\14` & criar a variável com o nome: `pgpath` em:
3. Meu computador--> Propriedades-->Configurações avançadas do sistema, na caixa de diálogo, selecionar `Variáveis de Ambiente`---> `Variáveis do Sistema`---> `novo`:
   ` Nome da variável: pgpath ` & `Valor da variável = C:\Program Files\PostgreSQL\14 `.
1. Fazer o mesmo procedimento para as variáveis: ``` pghost = 127.0.0.1;
                                        pgport = 5432;
                                         pguser = postgres;
                                           pgpassword = **** ```.
1. Inserir uma varíavel dentro de uma variável do sistema já existente do windows chamada: `path` ---> EDITAR ---> inserir: `%pgpath%\bin`.
***
## Configurar caso houver problemas de autenticação:
1. Vá na pasta `Data` em arquivos e programas do Windows.
2. Procure o arquivo em CONF. (abre com bloco de notas ) -->  `pg_hba` e altere o método de conexão com o servidor
Ivp4 & Ipv6 de `scram-sha-256` para `trust`:

       # TYPE  DATABASE        USER            ADDRESS                 METHOD
       
       # "local" is for Unix domain socket connections only
       local   all             all                                     trust
       # IPv4 local connections:
       host    all             all             127.0.0.1/32            trust
       # IPv6 local connections:
       host    all             all             ::1/128                 scram-sha-256
       # Allow replication connections from localhost, by a user with the
       # replication privilege.
       local   replication     all                                     scram-sha-256
       host    replication     all             127.0.0.1/32            scram-sha-256
       host    replication     all             ::1/128                 scram-sha-256


3. Após a alteração o serviço do PostgreSQL deve ser reiniciado para carregar a alteração da configuração:
   `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` e REINICIE o serviço do PostgreSQL.
***   

  * Qualquer senha pode ser utilizada para o acesso ao banco de dados a partir deste momento.
  * Tendo retomado o acesso, uma nova senha pode ser definida.
  * Após a redefinição da senha a configuração do método de autenticação para trust pode ser desfeita.
  * O serviço do PostgreSQL deve ser reiniciado para carregar a alteração da configuração
  * A nova senha pode ser utilizada para o acesso ao banco de dados (com o método de autenticação anterior)
****
### Problemas com Portas para conexão com Servidor:
* Por padrão é utilizada a porta: `5432`, porém, caso ela estiver em uso por outro BD será necessário mudá-la.
* Acesse a pasta : `C:\Program Files\PostgreSQL\16\data` do arquivo `CONF` ----> nome: `postgreSQL` e mude a porta para `5433`, dentro do arquivo e salve.
* Altere o PGadmin, em caso de problemas de autenticação, para a porta `5433`.
* Entre em propriedades do servidor `PostgreSQL16`, na interface gráfica, e altere a porta também para `5433` para se conectar com o servidor através do `PGAdmin`.
  ***

--
