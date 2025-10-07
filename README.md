# ataque-bruteforce
Um projeto simples que simula como um ataque de força bruta funciona utilizando a ferramenta medusa no Kali linux.

Um ataque de força bruta é um método de hacking que usa tentativa e erro para adivinhar nomes de usuário, senhas ou chaves de criptografia, testando muitas combinações até encontrar a correta.

Uma VM(máquina virtual) rodando Kali Linux foi utilizada para conseguir controle sobre outra VM rodando Metasploitable através de um ataque de força bruta para adivinhar o nome e senha da máquina.

## Passo a Passo e listagem dos comandos utilizados
> Os passos podem ser acompanhados pelos prints contidos na pasta "images"
### Utilizando o cmd do Kali Linux:

- Encontrar portas de acesso abertas na máquina alvo. \
  `nmap -sV -p 21-40 192.168.56.102` \
  Esse comando escaneia todas as portas do numéro 21 a 40 do endereço ip 192.168.56.102 e informa se estão abertas ou fechadas. \

- Criar arquivos de texto contendo listas de nomes de usuários e senhas para serem combinadas e testados na máquina alvo. \
  Normalmente em um ataque real, centenas ou milhares de nomes e senhas estariam contidas nos arquivos de texto para maior probabilidade de acerto.

- Utilizar a ferramenta Medusa, este comando realiza o teste de cada combinação possível utilizando os nomes e senhas contidas nos arquivos criados anteriormente através da porta aberta identificada no primeiro passo, avisando caso alguma combinação seja aceita. ("-t 5" é a quantidade de threads usadas no ataque [faz o ataque ser mais rápido]) \
  `medusa -h 192.168.56.102 -U usuarios.txt -P senhas.txt -M ftp -t 5`

- Acessar a máquina pela porta 21 ftp usando o nome e senha encontrados usando o comando anterior. \
  `ftp 192.168.56.102` \
  Esse comando acessa a máquina que pede o nome de usuário e senha para conceder acesso.

- Após obter acesso, o invasor pode resumidamente fazer o que desejar na máquina invadida, em meu exemplo eu simulei um roubo de dados, onde uma cópia do arquivo "segredo.txt" contendo dados confidenciais foi passada para a máquina do invasor. 
