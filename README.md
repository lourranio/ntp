# ntp

Testado no ubuntu 22


 No tutorial abaixo você verá como instalar e configurar o NTP para realizar a sincronização do relógio.

 
## Etapa 1: lista de fusos horários disponíveis
 

```timedatectl list-timezones```
     

## Etapa 2: definir o fuso horário desejado
 

```sudo timedatectl set-timezone America/Sao_Paulo```
     

 
## Procedimento: configurar o NTPD no Ubuntu 22 configurar o NTP ubuntu

Abra o terminal ou conecte a sua SSH. Você deve logar como o usuário root. Digite o seguinte comando apt para instalar o NTP:

```
sudo apt-get update

sudo apt-get install ntp ntpdate
```     

## Sincronize o relógio do sistema com o servidor a.ntp.br manualmente (use este comando apenas uma vez, ou conforme necessário):

```
service ntp stop
sudo ntpdate a.ntp.br
service ntp start
```
 

## Configurar o NTP (opcional)     

Abra o arquivo ntp.conf

```
sudo nano /etc/ntp.conf     
```

Abra o arquivo /etc/ntp.conf e procure pelas linhas:

```
server 0.ubuntu.pool.ntp.org
server 1.ubuntu.pool.ntp.org
server 2.ubuntu.pool.ntp.org
server 3.ubuntu.pool.ntp.org
# Use Ubuntu's ntp server as a fallback.
server ntp.ubuntu.com
```     

Altere para os servidores públicos do projeto http://ntp.br :

```
server a.ntp.br
server b.ntp.br
server c.ntp.br
```
     

Parar e iniciar o servidor NTP.

 

Para iniciar, parar, reiniciar o servidor NTP use os comandos abaixo:

```
service ntp start
service ntp stop
service ntp restart
```


Tags: NTP • SSH • Ubuntu • ubuntu server
