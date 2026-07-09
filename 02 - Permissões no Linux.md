## Permissões no Linux
### Modelo Básico
Todo arquivo no Linux tem três grupos de permissões básicas pra três categorias de "quem". Por exemplo, quando decompomos as permissões do arquivo "app.py" que tem "-rwxr-xr--", temos:
- O primeiro "-" mostra que é um arquivo. Se fosse um diretório seria "drwxr-xr--".
- O primeiro bloco de permissões "rwx" **(read, write e execute)**, mostra as permissões do dono.
- O segundo bloco de permissões "r-x" **(read e execute)**, mostra as permissões do grupo
- O terceiro bloco de permissões "r--" **(só read)**, mostra as permissões dos outros.
## Notação Numérica (octoal)
Nesse modo, cada número tem um valor, sendo:
- r = 4
- w = 2
- x = 1
E assim somamos por categoria. Por exemplo: "chmod 754 app.py" faz,
- O dono tem permissão 7, ou seja: ele pode ler, escrever e executar o arquivo.
- O grupo tem permissão 5, ou seja: ele pode ler e executar o arquivo.
- Os outros tem permissão 4, ou seja: eles podem somente ler o arquivo.

## Extras Perigosos
- **SUID (Set User ID):** Quando um executável tem SUID, ele roda com permissão do dono do arquivo, não de quem tá executando. Aparece como "s" no lugar do "x" do dono.
- **SGID (Set Group ID):** Mesma coisa que o SUID, só que com grupos.
- **Sticky Bit:** É feito pra diretórios e impede que um usuário delete arquivos dentro dele e de outro diretório compartilhado, mesmo tendo permissão.

## Usuários, Grupos e Superusuário
### Usuários
1. **Root (Superusuário):** é o administrador do sistema com UID 0. Tem controle total e irrestrito sobre praticamente tudo do sistema, sem restrições de seguranças.
2. **Usuários Comuns:** Criado para usuários que fazem login, as ações ficam limitadas ao diretório "/home/usuário" e possuem permissões restritas pra modificar arquivos da raiz do sistema. Normalmente tem UID acima de 1000
3. **Usuários do Sistema:** Contas criadas por apps ou processos. Elas não precisam de login e são usadas pra executar serviços específicos de forma isolada.
### Grupos
1. **Grupo Primário(Login Group):** Grupo automático quando um usuário é criado, normalmente tem o mesmo nome do usuário. Arquivos criados por usuários assumem esse grupo por padrão.
2. **Grupo Secundário(Suplementar):** Grupo pro usuário acessar diretórios ou arquivos específicos sem mudar de grupo principal.
3. **Grupo de Sistemas/Administrativos:** Grupos especiais para gerenciar permissões como sudo, wheel ou adm. 

## SUDO VS SU
- **su:** Troca completamente de usuário (pra root) pedindo a senha do usuário de destino.
- **sudo:** Executa um único comando como root (ou outro usuário), pedindo a senha do usuário atual e registra a ação em log (/varlog/auth.log). Configuração de sudo em /etc/sudoers.