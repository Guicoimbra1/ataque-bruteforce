# ataque-bruteforce
Um projeto simples que simula como um ataque de força bruta funciona utilizando a ferramenta medusa no Kali linux.

Uma VM(máquina virtual) rodando Kali Linux foi utilizada para conseguir controle sobre outra VM rodando Metasploitable através de um ataque de força bruta.

## Passo a Passo e listagem dos comandos utilizados
> Os passos podem ser acompanhados pelos prints contidos na pasta "images"
### Utilizando o cmd do Kali Linux:

- Encontrar portas de acesso abertas na máquina alvo. \n
`nmap -sV -p 21-40 192.168.56.102`
Esse comando escaneia todas as portas do numéro 21 a 40 do endereço ip 192.168.56.102 e informa se estão abertas ou fechadas.
