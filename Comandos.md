# Comandos de Terminal

## Navegação de Diretórios

- `cd nome_do_diretorio`: Altera o diretório atual para `nome_do_diretorio`.
- `cd -`: Retorna para o último diretório acessado.
- `cd ~`: Retorna para o diretório home do usuário.
- `cd /`: Vai para a raiz do sistema de arquivos Linux.
- `cd ../`: Volta para o diretório anterior (um nível acima).

## Listagem de Arquivos e Diretórios

- `ls`: Lista todos os arquivos e diretórios dentro do diretório atual.
- `ls -l`: Lista o conteúdo em formato de lista detalhada, incluindo permissões, dono e data de modificação.
- `ls -h`: Exibe o conteúdo com tamanhos legíveis para humanos (ex: KB, MB, GB).
- `ls -a`: Lista todos os arquivos, incluindo os ocultos (arquivos que começam com `.`).
- `ls -t`: Lista o conteúdo ordenado por data de modificação (do mais recente ao mais antigo).

## Manipulação de Arquivos e Conteúdo

- `cat nome_do_arquivo`: Mostra o conteúdo do arquivo `nome_do_arquivo`.
- `cat -n nome_do_arquivo`: Exibe o conteúdo do arquivo com as linhas numeradas.
- `touch nome_do_arquivo`: Cria um arquivo vazio chamado `nome_do_arquivo`.
- `mkdir nome_do_diretorio`: Cria um novo diretório com o nome `nome_do_diretorio`.
- `rmdir nome_do_diretorio`: Remove o diretório vazio `nome_do_diretorio`.

## Remoção de Arquivos e Diretórios

- `rm nome_do_arquivo`: Remove o arquivo `nome_do_arquivo`.
- `rm -i nome_do_arquivo`: Solicita confirmação antes de remover o arquivo.
- `rm -f nome_do_arquivo`: Remove o arquivo sem confirmação, mesmo que ele esteja protegido por escrita.
- `rm -r nome_do_diretorio`: Remove o diretório e todo o seu conteúdo recursivamente.
- `rm -rf nome_do_diretorio`: Remove o diretório e seu conteúdo, forçando a remoção sem confirmação.
- `rm -v nome_do_arquivo`: Remove o arquivo e exibe uma mensagem com informações sobre a remoção.

## Cópia e Movimentação de Arquivos e Diretórios

- `cp nome_do_arquivo nome_do_diretorio/`: Copia o arquivo para o diretório de destino.
- `cp -r nome_do_diretorio destino/`: Copia o diretório e todo o seu conteúdo para o diretório `destino`.
- `cp -u nome_do_arquivo nome_do_diretorio/`: Copia o arquivo apenas se for mais recente que o arquivo de destino ou se ele não existir no destino.
- `mv nome_do_arquivo nome_do_diretorio/`: Move o arquivo ou diretório para o diretório de destino.
- `mv -n nome_do_arquivo nome_do_diretorio/`: Move o arquivo para o diretório sem sobrescrever arquivos existentes no destino.

## Exibir Linhas de um Arquivo

- `head nome_do_arquivo`: Exibe as primeiras 10 linhas do arquivo.
- `head -n 3 nome_do_arquivo`: Exibe as primeiras 3 linhas do arquivo.
- `tail nome_do_arquivo`: Exibe as últimas 10 linhas do arquivo.
- `tail -n 5 nome_do_arquivo`: Exibe as últimas 5 linhas do arquivo.

## Buscar Texto em Arquivos

- `grep "texto" nome_do_arquivo`: Busca por "texto" dentro do arquivo e exibe as linhas que o contêm.
- `grep -i "texto" nome_do_arquivo`: Busca ignorando maiúsculas e minúsculas.
- `grep -c "texto" nome_do_arquivo`: Conta quantas vezes "texto" aparece no arquivo.

## Buscar Arquivos e Diretórios

- `find /caminho/ -name "nome_do_arquivo"`: Procura por um arquivo ou diretório com o nome especificado no diretório informado.
- Exemplo: `find . -iname 'hel*' -type f`: Busca, no diretório atual (`.`), todos os arquivos (`-type f`) que contenham "hel" no nome (ignora maiúsculas/minúsculas com `-iname`).
- `locate nome_do_arquivo`: Busca um arquivo pelo nome. Tem desempenho mais rápido que `find`, mas pode não encontrar arquivos recentes.

## Editores de Texto

- `nano`: Abre o editor `nano` em um arquivo novo.
- `nano nome_do_arquivo`: Abre o editor no arquivo.
- `vim nome_do_arquivo`: Abre o editor no arquivo.

## Comandos para Gerenciar Aplicativos

- `apt-cache search nome_do_aplicativo`: Procura por um aplicativo no repositório, exibindo uma lista de pacotes correspondentes ao nome ou termo pesquisado.
- `sudo apt-get autoremove`: Remove pacotes e dependências que não são mais necessários.
- `sudo apt-get install nome_do_aplicativo`: Instala um aplicativo pelo nome.
- `sudo apt-get purge nome_do_aplicativo`: Remove um aplicativo e seus arquivos de configuração.

## Gerenciamento de Grupos e Usuários

- `sudo adduser nome_do_usuario`: Adiciona novo usuário.
- `sudo userdel --remove nome_do_usuario`: Remove usuário.
- `sudo usermod -c 'novo_nome' nome_do_usuario`: Altera o nome do usuário.
- `sudo usermod -l novo_nome -d /home/novo_nome -m nome_atual`: Altera o nome do usuário na pasta.
- `sudo usermod -L nome_do_usuario`: Desabilita usuário.
- `sudo usermod -U nome_do_usuario`: Reabilita usuário.
- `getent group`: Mostra todos os grupos.
- `sudo groupadd -g id_do_grupo nome_do_grupo`: Adiciona novo grupo.
- `sudo groupdel nome_do_grupo`: Remove grupo.
- `sudo usermod -a -G nome_do_grupo nome_do_usuario`: Adiciona usuário a um grupo.
- `sudo gpasswd -d nome_do_usuario nome_do_grupo`: Remove usuário do grupo.
- `passwd`: Altera a senha do usuário logado.
- `sudo su`: Transforma em Super usuário (não precisa mais usar `sudo` antes dos comandos); para sair basta digitar `exit`.

## Permissões

### Permissões Numéricas (mais usadas)

- Comando `chmod` seguido de 3 números onde:
  - O primeiro número representa a permissão do dono.
  - O segundo representa a permissão do grupo.
  - O terceiro representa a permissão dos demais usuários.
  - Exemplo de permissões:
    - `chmod 777 nome_do_arquivo`: Todos têm permissão para tudo (não recomendado).
    - `chmod 400 nome_do_arquivo`: Apenas o dono tem permissão de leitura.
    - `chmod 764 nome_do_arquivo`: Dono tem todas as permissões, grupo pode ler e alterar, demais apenas ler.
    - `chmod 644 nome_do_arquivo`: Dono tem permissão de leitura e escrita, grupo e demais apenas leitura.
    - `chmod 700 nome_do_arquivo`: Dono tem todas as permissões, grupo e demais não têm acesso.
    - `chmod 755 nome_do_arquivo`: Dono tem todas as permissões, grupo e demais apenas leitura e execução.
    - `chmod 000 nome_do_arquivo`: Ninguém tem permissão para nada, apenas com `sudo` ou `root`.

### Permissões Simbólicas

- Comando `chmod` seguido de uma letra (a para todos, u para o dono, g para o grupo, e o para os demais) + um sinal (= para substituir a permissão, + para adicionar permissão, - para remover permissão) + as permissões (x para executar, r para ler, w para escrever) + `nome_do_arquivo`.

### Outros Comandos de Permissões

- `chown nome_do_usuario nome_do_arquivo`: Altera o dono do arquivo.
- `chown nome_do_usuario:nome_do_grupo nome_do_arquivo`: Altera o dono e o grupo do arquivo.
- `chgrp nome_do_grupo nome_do_arquivo`: Altera o grupo do arquivo.

## Gerenciamento Básico de Redes

- `ping nome_do_dominio_ou_ip`: Faz conexão com um site ou um IP.
- `netstat`: Ver conexões que a máquina possui.
- `netstat -at`: Ver as conexões TCP.
- `netstat -au`: Ver as conexões UDP.
- `ifconfig`: Configurar, visualizar e gerenciar interfaces de rede.
- `nslookup nome_do_dominio`: Ver o IP de uma máquina pelo DNS.
- `tcpdump`: Mostra todas as conexões TCP que a máquina está fazendo.
- `hostname -I`: Ver o IP da máquina.

## Compactação e Descompactação de Arquivos

- `tar -czvf nome_do_arquivo_a_ser_compactado.tar.gz nome_do_diretorio_ou_arquivo`: Compactar com `tar`.
- `tar -xzvf nome_do_arquivo_compactado`: Descompactar com `tar`.
- `tar -xzvf nome_do_arquivo_compactado -C nome_do_diretorio`: Descompactar com `tar`, especificando o diretório de destino.
- `zip -r nome_do_arquivo_a_ser_compactado.zip nome_do_diretorio_ou_arquivo`: Compactar com `zip`.
- `unzip nome_do_arquivo_compactado`: Descompactar com `zip`.

