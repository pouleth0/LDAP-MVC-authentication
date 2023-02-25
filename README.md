# LDAP-MVC-authentication
 utilizando uma arquitetura MVC (Model-View-Controller) robusta e escalável. O Ldap_MVC_Spring é um projeto de código aberto!

*Classe [LdapServerConfig]:*

Essa classe é responsável por configurar o servidor LDAP. Ela utiliza a anotação @Configuration do Spring para indicar que é uma classe de configuração e @PropertySource para carregar as propriedades de um arquivo de propriedades. Possui os seguintes métodos:
[ldapContextSource()]: retorna um objeto LdapContextSource que é responsável por criar um contexto de conexão com o servidor LDAP.
[ldapTemplate()]: retorna um objeto LdapTemplate que é responsável por executar operações no servidor LDAP, como adicionar, modificar, pesquisar e excluir entradas.

*Classe [LdapUser]:*

Essa classe representa um usuário no servidor LDAP. Possui os seguintes atributos:
[cn]: o nome comum do usuário.
[givenName]: o nome próprio do usuário.
[sn]: o sobrenome do usuário.
[userPrincipalName]: o nome do usuário seguido pelo nome do domínio, que é usado para autenticação.
[sAMAccountName]: o nome do usuário que é usado como identificador único no Active Directory.
[unicodePwd]: a senha do usuário codificada em unicode.
Possui os seguintes métodos:
[toAttributes()]: retorna um objeto Attributes que representa os atributos do usuário no servidor LDAP.
[fromAttributes()]: preenche os atributos do usuário a partir de um objeto Attributes.

*Classe [LdapUserDao]:*

Essa classe é responsável por executar operações CRUD no servidor LDAP para a entidade LdapUser. Possui os seguintes métodos:
[create()]: adiciona um novo usuário ao servidor LDAP.
[update()]: atualiza um usuário existente no servidor LDAP.
[delete()]: exclui um usuário do servidor LDAP.
[findByDn()]: busca um usuário no servidor LDAP pelo seu DN.
[findByAttribute()]: busca usuários no servidor LDAP por um atributo específico e seu valor.
[findAll()]: busca todos os usuários no servidor LDAP.

*Classe [LdapUserService]:*

Essa classe é responsável por fornecer serviços de negócios para a entidade LdapUser. Possui os seguintes métodos:
[authenticate()]: verifica se as credenciais de um usuário são válidas no servidor LDAP.
[createUser()]: cria um novo usuário no servidor LDAP.
[modifyUser()]: atualiza um usuário existente no servidor LDAP.
[deleteUser()]: exclui um usuário do servidor LDAP.
[addUser()]: adiciona um usuário a um grupo no servidor LDAP.
[getAllUsers()]: busca todos os usuários no servidor LDAP.

*Classe [LdapController]:*

Essa classe é responsável por receber e tratar as requisições do usuário, chamando os métodos apropriados do serviço LdapService.
Métodos:
[authenticate]: recebe um nome de usuário e senha e verifica se as credenciais são válidas no LDAP.
[createUser]: recebe informações de um novo usuário e adiciona-o ao LDAP.
[modifyUser]: recebe informações atualizadas de um usuário existente e modifica seus dados no LDAP.
[deleteUser]: recebe o nome de usuário de um usuário existente e o remove do LDAP.
[getAllUsers]: busca e retorna todos os usuários do LDAP.

*Classe [LdapView]:*

Essa classe é responsável por conter a lógica de negócios do LDAP.
Métodos:
[authenticate]: recebe um nome de usuário e senha e verifica se as credenciais são válidas no LDAP.
[createUser]: recebe informações de um novo usuário e adiciona-o ao LDAP.
[modifyUser]: recebe informações atualizadas de um usuário existente e modifica seus dados no LDAP.
[deleteUser]: recebe o nome de usuário de um usuário existente e o remove do LDAP.
[getAllUsers]: busca e retorna todos os usuários do LDAP.
[buildSearchFilter]: constrói um filtro de pesquisa LDAP com base nos parâmetros informados.
[buildUserDn]: constrói o DN do usuário com base no seu nome de usuário.
[getLdapEnv]: retorna uma instância do ambiente LDAP configurada com os parâmetros informados.

*Classe [LdapSecurity]:*

Essa classe é responsável por definir as configurações de conexão LDAP.
Métodos:
[getContextSource]: retorna uma instância do ContextSource configurada com os parâmetros informados.
[getSecureMethodName]: a definir
[getEcriptPassword]: a definir



