# SacudoLabs

![Early Access](https://img.shields.io/badge/-Early%20Access-e8590c)

**O gerenciador de idle que entende o seu jogo.** Várias contas. Uma janela.

O SacudoLabs é um app para Windows que abre as suas contas do
[Huntera](https://huntera.com.br) numa janela só e entende o que o jogo mostra: monta a
ficha do personagem, confere a barra de ações, guarda o diário de hunts e avisa quando algo precisa da sua atenção, no app, no Windows ou
no Telegram. Com a conta SacudoLabs (o login com o Discord), ele também explica cada
hunt (o que rendeu, o que gastou e onde melhorar) e conversa sobre o personagem com o
Sacudo.

Esta é uma versão de **Early Access** (0.x): pode ter bugs, e é justamente para
encontrá-los. Quando algo der errado, veja
[Relatar problema ou sugestão](#relatar-problema-ou-sugestão).

- **[Guia do jogador](https://docs.sacudo.net)**: como cada parte do app funciona.
- **[Perguntas frequentes](https://docs.sacudo.net/perguntas-frequentes/)**: o aviso do
  Windows, o login que vence toda semana, quanta memória precisa, se é permitido.
- **[O site do SacudoLabs](https://sacudo.net/labs)**: o que o app faz, num vídeo e em
  prints.
- **[Termos do serviço](https://docs.sacudo.net/termos/)**: o mesmo texto que o app
  mostra ao entrar na conta SacudoLabs. A política de privacidade em página pública
  está a caminho.

O SacudoLabs é um projeto independente, sem vínculo com o Huntera.

## Do que precisa

- Windows 10 ou 11, 64 bits.
- Memória: para 4 contas abertas, **16 GB de RAM** recomendados. Cada conta é uma página
  do jogo; com menos memória, abra menos contas.
- Uma conta no Huntera.
- O Microsoft Edge WebView2, que já vem na maioria dos Windows. Se faltar, o instalador
  oferece o instalador oficial da Microsoft.
- Opcional: uma conta no Discord, para entrar na conta SacudoLabs e ter os relatórios das
  hunts e o Sacudo. Eles estão em acesso antecipado por convite: a conta nova fica
  aguardando até ser liberada. Sem ela, o resto do app funciona.

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
4. Se aparecer **"O controle inteligente de aplicativos bloqueou um aplicativo"** (Windows
   11 com o Controle Inteligente de Aplicativos ligado), não há "Executar assim mesmo":
   esse controle barra todo programa sem assinatura digital. **Se o seu Windows usa
   isso, ainda não dá para usar o SacudoLabs.** Não desligue o controle por causa do app:
   em muitos Windows, desligado, ele não volta a ligar sem reinstalar o sistema. Quando o
   instalador tiver assinatura, o app passa a abrir com ele ligado.
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
minúsculas não importam). Se for diferente, não abra o arquivo: apague-o e baixe de novo
desta página.

## Primeiros passos

1. O app abre com uma conta. Entre no Huntera na própria página do jogo, como no
   navegador: o login fica salvo no seu PC. É o login do próprio jogo, que vence a cada
   7 dias; o card da conta avisa nas últimas 48 horas.
2. Para mais contas (até 4), use o **+** embaixo dos cards, à esquerda. Cada conta tem
   o próprio login.
3. No card de uma conta, a seta **›** abre a página do personagem: a ficha, a barra e as
   hunts dele.
4. Opcional: em **Configurações → Conta**, entre com o Discord para ter os relatórios das hunts e o Sacudo. Em
   **Configurações → Alertas**, escolha o que avisar e onde, até no Telegram.

Para entender como cada parte do app funciona, veja o
**[guia do jogador](https://docs.sacudo.net)**.

## Atualizar

O app procura versão nova ao abrir e a cada 30 minutos. Quando acha, baixa em segundo
plano, confere a impressão digital e avisa numa faixa no topo do painel esquerdo, com
o que mudou:

- **Atualizar agora**: o app fecha, instala e abre de novo em cerca de 1 minuto. As
  contas logadas, o diário e as configurações continuam lá.
- **Não instalar esta**: a faixa some até sair uma versão mais nova.
- Sem clicar em nada: quando você fechar o app, ele pergunta se atualiza naquela hora
  (**Atualizar e reabrir**) ou não (**Só fechar**), e pergunta de novo no próximo
  fechamento.

Antes de abrir uma versão nova pela primeira vez, o app guarda uma cópia do diário e
das contas. Nada é instalado sem o seu clique. Dá para desligar a procura em
**Configurações → Geral → Atualizações**, e o botão **Verificar atualizações**, em
**Configurações → Ajuda**, procura na hora.

**Para atualizar na mão**, baixe o instalador mais novo desta página e rode por cima,
com o app fechado. **Não desinstale antes**: o instalador troca só o programa, e os
seus dados ficam onde estão.

## Relatar problema ou sugestão

Em **Configurações → Ajuda → Relatar problema ou sugestão** (ou **☰ → Ajuda**), escolha
**Problema** ou **Sugestão**, escreva e clique em **Enviar**.

- **Com a conta SacudoLabs** (o login com o Discord, em **Configurações → Conta**), vai
  direto pelo seu login e o app mostra o número (**Relatório #N enviado**, **Sugestão #N
  enviada**): cite o número quando for falar do problema com o SacudoLabs.
- **Sem a conta**, nada sai do PC: um problema vira um `.zip` e o app abre a pasta dele,
  para você guardar ou mandar por onde fala com o SacudoLabs. Uma sugestão pede o login.

O relatório leva os registros (logs) dos últimos 3 dias, com chaves e logins trocados
por `[masked]`, e um resumo de diagnóstico: as versões do app e do banco de dados, o
tamanho do banco, quantas hunts há por id de conta, os ids do `accounts.json` e os
arquivos `*.broken-*`. Os logs podem ter nomes de personagem e os nomes que você deu às
contas. Não leva o conteúdo das hunts, gravações do jogo, senha, chave nem login. Uma
sugestão leva só o texto, a versão do app e a sua conta.

Com a conta SacudoLabs, erros graves (o app travar, o diário não abrir, uma atualização
falhar) mandam um relatório sozinhos, como os termos do serviço dizem. No máximo 3 por
dia; para não mandar, desligue **Enviar relatórios de erro automaticamente** em
**Configurações → Geral**, e os relatórios das hunts e o Sacudo continuam funcionando.

O serviço do SacudoLabs **guarda cada relatório e cada sugestão por 30 dias** e depois
apaga; apagar a conta apaga os dela junto. Mais detalhes no
[guia](https://docs.sacudo.net/relatar-um-problema/).

## O que o app faz e o que não faz

O SacudoLabs **só observa e avisa**. Ele:

- **Nunca joga por você:** não clica, não digita, não manda nada ao servidor do jogo e
  não altera a página do jogo. As regras do Huntera proíbem bots, macros e clientes
  modificados, e o app foi feito para ficar fora disso. O que você aplica, como o código
  de uma barra, vai para a área de transferência, e você cola no jogo.
- **Guarda tudo no seu PC**, em `%LOCALAPPDATA%\SacudoLabs`: os logins das contas, o
  diário de hunts, as configurações e as gravações do que o jogo recebeu (para o diário
  e as análises). A sessão da conta SacudoLabs fica no Gerenciador de Credenciais do
  Windows.
- **Sem rastreamento de uso. O que sai do PC é isto:**
  - no login da conta SacudoLabs, o ID e o nome do Discord;
  - as conversas com o Sacudo e os relatórios das hunts, pelo serviço do SacudoLabs,
    levando os dados do jogo que cada um precisa (nunca o seu login do jogo ou cookies).
    O serviço não guarda esse conteúdo; guarda só quanto cada conta usou, para os
    limites de uso;
  - os alertas pelo Telegram, se você ligar, pelo bot do SacudoLabs;
  - a procura de versão nova, uma consulta ao GitHub que não leva nada sobre você (o
    GitHub vê o seu IP, como em qualquer site). Dá para desligar;
  - os relatórios de problema e as sugestões que você manda, e, com a conta SacudoLabs,
    os automáticos de erros graves (dá para desligar), que o serviço guarda por 30 dias.

## Desinstalar

Em **Configurações do Windows → Aplicativos**, procure **SacudoLabs** e escolha
**Desinstalar**. O desinstalador pergunta se manda também os seus dados (contas
logadas, diário e configurações) para a Lixeira; as chaves salvas no Windows são
apagadas. Se pretende instalar de novo, responda **Não**: tudo volta como estava. Se
respondeu Sim por engano, restaure a pasta `SacudoLabs` da Lixeira antes de abrir o
app de novo.
