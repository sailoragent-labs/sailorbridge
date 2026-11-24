[English](../../AGENTS.md) · [简体中文](../zh-CN/AGENTS.md) · [日本語](../ja/AGENTS.md) · [한국어](../ko/AGENTS.md) · [Deutsch](../de/AGENTS.md) · [Français](../fr/AGENTS.md) · [Español](../es/AGENTS.md) · [Português (BR)](AGENTS.md) · [Bahasa Indonesia](../id/AGENTS.md) · [हिन्दी](../hi/AGENTS.md)

# Guia de configuração do SailorBridge

## 1. Preparar a máquina

Use uma máquina que você controla com Linux x64 ou macOS em arm64 ou x64. Instale o Git e escolha entre Claude Code e Codex. Instale o motor escolhido, entre com sua própria conta e escolha o diretório do projeto no qual a equipe vai trabalhar.

**Verificação** — Tanto `git --version` quanto `claude --version` ou `codex --version`, conforme o motor, exibem uma versão. Se já instalou o motor, mas ainda não entrou na conta, execute `claude login` ou `codex login` nessa máquina. O pareamento pode ser feito antes. Entre na conta antes de conversar ou iniciar uma tarefa.

## 2. Fazer o cadastro no navegador

Abra o [aplicativo](https://app.sailorbridge.com) e selecione **Cadastrar**. Para seguir este guia, digite um ID do capitão numérico que apareça como disponível e gratuito, defina uma senha, confirme sua idade e aceite os termos de serviço.

**Verificação** — O aplicativo abre e você pode acessar **Máquinas**.

## 3. Executar o comando de instalação

Em **Máquinas**, abra **Parear nova máquina**. Copie o único comando de instalação exibido e execute-o na máquina da etapa 1. Ele instala o `sail` e inicia o pareamento automaticamente.

**Verificação** — O terminal exibe um código de emparelhamento de oito caracteres e o tempo restante. Se o código expirar, execute `sail login` para obter outro.

- **A máquina já está pareada com esse endereço?** Execute `sail host status`. Se estiver conectada, vá para a etapa 5. Para restaurar o serviço no mesmo endereço, execute `sail login`. O serviço reinicia com as credenciais existentes.
- **Endereço incorreto (`origin_mismatch`)?** Para trocar de endereço, execute `sail uninstall`. Depois, copie e execute o comando de instalação da página Máquinas do aplicativo ao qual deseja se conectar. A desinstalação exclui os dados locais do SailorBridge, inclusive suas cópias de trabalho.

## 4. Aprovar a máquina

Digite o código de emparelhamento na página de pareamento do navegador e selecione **Parear**. Confira o nome e os detalhes da máquina que aparece. No primeiro pareamento, leia e aceite o aviso sobre as permissões do usuário que executa o `sail` e selecione **Aprovar máquina**.

**Verificação** — Aguarde o estado **On-line** em **Máquinas**. O terminal também confirma que a máquina está pareada e on-line.

## 5. Criar uma equipe

Selecione **Criar uma Equipe**. Dê um nome à equipe, escolha a máquina on-line e informe o caminho absoluto nessa máquina em **Diretório do projeto**. Se o diretório ainda não existir, o SailorBridge vai criá-lo no primeiro uso. Em **Destino**, mantenha **Mescla automática** para mesclar as alterações na branch principal remota, ou escolha **Branch** para enviar cada tarefa a uma branch própria para revisão. Crie a equipe.

**Verificação** — A máquina selecionada aparece na nova equipe com o estado **Online**.

## 6. Enviar a primeira mensagem

Abra a **Conversa** da equipe e pergunte “Em qual diretório do projeto estamos trabalhando?”.

**Verificação** — O **Líder** responde na mesma conversa.

## 7. Concluir a primeira tarefa

Envie `/agent Conte os arquivos na raiz do projeto e me diga quantos são.` na conversa da equipe. Abra **⋯ → Lista de tarefas** para acompanhar a tarefa.

**Verificação** — A tarefa aparece como **Feita**. Abra o **Relatório de entrega** e confira o número de arquivos.
