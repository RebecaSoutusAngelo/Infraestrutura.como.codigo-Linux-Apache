# Infraestrutura.como.codigo-Linux-Apache
Script do provisicionamento de um servidor web (Apache)

Por motivos técnicos, não consegui manipular o código e os comandos no Virtual Box e nem no Git Bash. 
Não acrescentei a este Read.me as informações que o sistema 
disponibilizou para justificar o porquê deste Repositório não estar completo, ou "como deveria estar", porque só estavam disponíveis em "PrintScreeen".

Não consegui ajuda especializada pelo Discord...

Para ajudar na compreensão:
Utilizei: >Para expressão uma ideia ou contexto<
--> Para enfatizar comando ou título
-> Para enfatizar ação.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------

1° Passo: Restaurar o snapshot criado anteriormente no VirtualBox.
Neste procedimento: 
-> Abrimos o VirtualBox, tiramos um snapshot e restauramos a máquina.
-> Reiniciamos a máquina a partir do último sanpshot e atualizamos o IP.
-> Ao localizar o IP atualizado, "abrimos" o PuTTy e o configuramos com o novo IP.
-> Acessamos o sistema como "root".

2° Passo: Criamos uma pasta ou subpasta e a nomeio como "script" ou "script2" - padrão do exercício.
> Contextualizando <
Para melhor compreensão do exercício, suponhamos que o linha de código no servidor esteja assim:
root@server:/script# 
> Fim da Contextualizacao <

3° Passo: Iniciamos o "modo nano".
-> Digitamos o comando:
root@server:/script# nano script-iac2.sh
-> A partir de então, o sistema apresentará a informação: GNU nano 4.8 (ou versão atualizada)

4° Passo: Criar um script.
-> Digitar o comando: #!/bin/bash

5° Atualizar o servidor:
--> Comandos:

echo "Atualizando o servidor..."

apt-get update
apt-get upgrade -y
apt-get install apache2 -y
apt-get install unzip -y

echo "Baixando e copiando os arquivos da aplicação..."

cd /tmp

>supondo que o wget já está instalado, solicitar a descompactação do arquivo no link, por exemplo:<
wget https://github.com/nomedoperfil/linux-dio/archive/refs/heads/main.zip
unzip main.zip

-> Abrir o diretório e copiar os arquivos para a pasta padrão do apache
cd linux-site-dio-main
cp -R */var/www/html/

6° Passo: Salvar e permitir execução: -> Ctrl + O, Ctrl + X.
chmod +x script-iac2.sh

>Sugestão: Salvar snapshot deste comando/momento no VirtualBox <

7° Passo: Executar:
./script.iac2.sh
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
Para testar o código:
1° Passo:
-> Abra um Browser e digite o IP da máquina





