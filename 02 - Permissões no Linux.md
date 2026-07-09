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
Na hierarquia:
1. **root (UID 0):** O superusuário, sem restrições de permissões.
2. **Usuários do Sistema:** Contas usadas por serviços, mas não para login pessoal.
3. **Usuários Comuns:** Contas pessoais, UID geralmente maior que 1000.
