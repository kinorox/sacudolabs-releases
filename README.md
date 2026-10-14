# SacudoLabs

O SacudoLabs abre até 4 contas do [Huntera](https://huntera.com.br) numa janela só e
lê o que o jogo já mostra para montar a ficha do personagem, conferir a barra de ações,
guardar o diário de hunts e avisar quando algo precisa da sua atenção. Com uma chave de
IA sua, ele também explica as hunts, conversa sobre o personagem e sugere barras.

Esta é uma versão de **early access** (0.x), só para convidados: pode ter bugs, e é
justamente para encontrá-los. Quando algo der errado, veja
[Relatar um problema](#relatar-um-problema).

O SacudoLabs é um projeto independente, sem vínculo com o Huntera.

## Do que precisa

- Windows 10 ou 11, 64 bits.
- Uma conta no Huntera.
- O Microsoft Edge WebView2, que já vem na maioria dos Windows. Se faltar, o instalador
  oferece o instalador oficial da Microsoft.
- Opcional: uma chave de API de IA (OpenAI, Anthropic, OpenRouter, OpenCode ou outra
  compatível) para os relatórios, o Sacudo e o otimizador. Sem ela, o resto funciona.

## Instalar

1. Em [**Releases**](https://github.com/kinorox/sacudolabs-releases/releases/latest),
   baixe o `SacudoLabs-setup-0.x.y.exe` da versão mais nova.
2. Se o navegador disser que o arquivo "não é baixado com frequência", escolha
   **Manter** (no Edge: **…** → **Manter** → **Mostrar mais** → **Manter mesmo assim**).
3. Abra o instalador. Se aparecer **"O Windows protegeu o computador"**, clique em
   **Mais informações** e depois em **Executar assim mesmo**. O aviso aparece porque o
   instalador ainda não tem assinatura digital (um certificado pago, que fica para perto
   da versão 1.0), não porque algo foi encontrado nele. Para conferir que o arquivo é o
   publicado, veja [Conferir o instalador](#conferir-o-instalador).
4. Se aparecer **"O controle inteligente de aplicativos bloqueou um aplicativo"** (Windows 11
   com esse controle ligado), não há "Executar assim mesmo": abra **Segurança do Windows →
   Controle de aplicativos e do navegador → Configurações do Controle Inteligente de
   Aplicativos**, escolha **Desativado** e abra o instalador de novo. Esse controle barra
   todo programa sem assinatura digital, o SacudoLabs instalado também, então ele precisa
   ficar desativado enquanto você usar o app. Antes da atualização de abril de 2026 do
   Windows (KB5083769), desativar é definitivo: só volta reinstalando o Windows.
5. O instalador não pede senha de administrador: ele instala só para o seu usuário, em
   `%LOCALAPPDATA%\Programs\SacudoLabs`, e cria o atalho no Menu Iniciar. No fim, deixe
   marcado **Abrir o SacudoLabs**.

### Conferir o instalador

Cada release traz, junto do instalador, um arquivo `.sha256` com a impressão digital
dele. No PowerShell, na pasta do download:

```powershell
Get-FileHash .\SacudoLabs-setup-0.x.y.exe -Algorithm SHA256
```

O código que aparece em `Hash` tem que ser o mesmo do `.sha256` (letras maiúsculas ou
minúsculas não importam). Se for diferente, não abra o arquivo e avise quem te convidou.

## Primeiros passos

1. O app abre com uma conta. Entre no Huntera na própria página do jogo, como no
   navegador: o login fica salvo no seu PC.
2. Para mais contas (até 4), use o **+** embaixo dos cards, à esquerda. Cada conta tem
   o próprio login.
3. No card de uma conta, a seta **›** abre a página do personagem: a ficha, a barra e as
   hunts dele.
4. Opcional: em **Configurações → IA**, escolha o provedor e cole a sua chave. Em
   **Configurações → Alertas** e **Telegram**, escolha o que avisar e onde.

## Atualizar

Ao abrir, o app procura versão nova. Quando houver, aparece uma faixa no topo do painel
esquerdo com o que mudou e o botão **Instalar e reiniciar**: o app baixa o instalador,
confere a impressão digital, fecha, instala e abre de novo, com as contas logadas.
Nada é instalado sem o seu clique. Dá para desligar a procura em **Configurações →
Geral → Atualizações**, e o botão **Verificar atualizações** procura na hora.

## Relatar um problema

Em **Configurações → Geral → Relatar um problema**, o app junta os registros (logs) dos
últimos 3 dias num `.zip` e abre a pasta dele. Mande esse arquivo para quem te convidou,
pelo meio que preferir, contando o que aconteceu. O `.zip` não leva gravações do jogo,
chaves nem login, e o app não envia nada sozinho.

## O que o app faz e o que não faz

O SacudoLabs **só observa e recomenda**. Ele:

- **Nunca joga por você:** não clica, não digita, não manda nada ao servidor do jogo e
  não altera a página do jogo. Os termos do Huntera proíbem bots, macros e clientes
  modificados, e o app foi feito para ficar fora disso. O que você aplica, como o código
  de uma barra, vai para a área de transferência, e você cola no jogo.
- **Guarda tudo no seu PC**, em `%LOCALAPPDATA%\SacudoLabs`: os logins das contas, o
  diário de hunts, as configurações e as gravações do que o jogo recebeu (para o diário
  e as análises). As chaves de IA e do Telegram ficam no Gerenciador de Credenciais do
  Windows.
- **Não tem telemetria.** Só três coisas saem do PC, e cada uma por escolha sua:
  - as perguntas à IA, com a sua chave, para o provedor que você escolheu, levando os
    dados do jogo que a pergunta precisa (nunca o seu login ou cookies);
  - os alertas pelo Telegram, se você ligar, pelo seu próprio bot;
  - a procura de versão nova, uma consulta ao GitHub que não leva nada sobre você (o
    GitHub vê o seu IP, como em qualquer site). Dá para desligar.

## Desinstalar

Em **Configurações do Windows → Aplicativos**, procure **SacudoLabs** e escolha
**Desinstalar**. O desinstalador pergunta se apaga também os seus dados (contas
logadas, diário, configurações e chaves salvas). Se pretende instalar de novo, responda
**Não**: tudo volta como estava.
