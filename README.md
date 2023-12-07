***
# PostgreSQL :    ![image](https://github.com/userdanixdev/PostgreSQL/assets/132594952/89bd1e1c-9aeb-4418-9f08-f13ff2765b45)

_Conceitos relativos os banco de dados PostgreSQL:_
****
Link para download do PostgreeSQL para WINDOWS:
https://www.enterprisedb.com/downloads/postgres-postgresql-downloads
****
# Para Windows é necessário fazer algumas configurações:
***
 __Configurar as variáveis de ambiente de acesso no Windows:___
1. Encontrar o diretório do software PostgreSQL:  `C:\Program Files\PostgreSQL\14` & criar a variável com o nome: `pgpath` em:
3. Configurações avançadas do sistema, na caixa de diálogo, selecionar `Variáveis de Ambiente`---> `Variáveis do Sistema`---> `novo`:
   ` Nome da variável: pgpath ` & `Valor da variável = C:\Program Files\PostgreSQL\14 `.
1. Fazer o mesmo procedimento para as variáveis: ``` pghost = 127.0.0.1;
                                        pgport = 5432;
                                         pguser = postgres;
                                           pgpassword = **** ```.
1. Inserir uma varíavel dentro de uma variável do sistema já existente do windows chamada: `path` ---> EDITAR ---> inserir: `%pgpath%\bin`.
