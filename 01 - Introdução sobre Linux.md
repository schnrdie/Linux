## O Que é o Linux
Muita gente acha que o Linux é um sistema operacional completo, mas ele é um Kernel, que é o núcleo do sistema. O Kernel é responsável por gerenciar a CPU, a memória RAM, dispositivos, e fornece uma interface entre o hardware e o software.
O que a gente chama de "Linux" é basicamente GNU/Linux, que é o Kernel e ferramentas GNU (bash, coreutils, etc), gerenciador de pacotes e ambientes gráficos opcionais. **Um exploit de escalada de privilégio explora uma falha no Kernel ou em como um programa interage com ele.**

## Filosofia Unix
Pra entender como o Linux é estruturado, é sempre bom lembrar da filosofia Unix:
1. **Tudo é um arquivo:** discos, processos, dispositivos, até informações do Kernel são mostrados como arquivos em pastas diferentes. Isso significa que a gente pode interagir com quase tudo do sistema e personalizar ele de acordo com nosso objetivo.
2. **Programas pequenos fazem uma coisa muito bem:** em vez de um programa gigante que faz várias coisas, o Unix prefere várias ferramentas pequenas combinadas pelo pipe (|).
3. **Tudo é texto:** configurações, logs, saídas, etc. Tudo é texto. Isso torna automação e parsing muitos poderosos no Linux.

# Estrutura de Diretórios mais importantes
- **/ :** É a raiz do sistema, tudo parte daqui.
- **/etc:** São arquivos de configuração.
- **/var/logs:** São Logs do sistema. 
- **/home:** Diretórios do usuário (dados e pastas pessoais).
- **/root:** Diretórios do superusuário.
- **/bin/usr/bin:** Binários executávies (comandos do terminal).
- **/sbin/usr/sbin:** Binários administrativos (comandos que precisam de sudo)
- **/proc:** Sistema de arquivos virtual (informações sobre processos rodando).
- **/tmp:** Arquivos temporários.
- **/dev:** Dispositivos de hardware.
- **/opt: Software opcional (terceiros).

Os diretórios mais importantes em cibersegurança, configuração de servidor e redes são:
- **/etc:** Tem configs de SSH, user, serviços.
- **/var/logs:** Muito usado em análise forense. É tipo a pegada que o sistema cria a cada alteração.
- **/proc:** Análise de processos rodando no sistema.
- **/tmp:** Onde os malwares normalmente se esconde.
- **/root:** Acesso ao superusuário.

## Minha Avaliação Pessoal sobre Distros Linux
### Ubuntu
A porta de entrada pra praticamente todo mundo. Polêmico na comunidade, mas é inegável que o Ubuntu é uma das distros mais importantes pro Linux (talvez depois do Debian). Tem bom suporte a hardware, uma comunidade gigante, e uma estabilidade muito boa. Provavelmente todo mundo começa aqui, depois lê sobre snaps ou algo sobre a Canonical e vai pro Mint. 
### Linux Mint
Ubuntu, mas sem os snaps forçados e com uma base ainda mais estável. Tem um suporte a hardware muito bom, é muito simples, funcional, estável. Perfeito pra quem tá migrando do Windows/Ubuntu. Pode ser meio chatinha pra quem quer aprender Linux profundamente.
### Debian
O pai de todos (o FreeBSD é o avô). Estável, minimalista, seguro, roda até em uma batata, documentação excelente, pode ser usado tanto pra Desktop quanto pra Servidor. Pode ser estável até demais, "engessado", pacotes antigos, tem uma curva de aprendizagem até que grande. 
### Arch Linux (e CachyOS)
Bom, mas é overrated. Acho mais importante algo funcional e prático do que algo extremamente customizável, possivelmente caótico e com uma manutenção maior.  É o mais atualizado de todos, tem uma comunidade muito ativa que cria e documenta os próprios pacotes (AUR), justamente por ser totalmente personalizável tem um desempenho gigante.
### Fedora
Fica entre o Debian e o Arch nas autalizações, é o meio termo. É estável, boa pra desenvolvimento, tem muitas ferramentas úteis de segurança (SELinux, Firewall configurado por padrão, isolamento de processos). Porém, tem um ciclo de vida bem curto (uns 13 meses) quando comparado a outras distros que fazem praticamente a mesma coisa.
