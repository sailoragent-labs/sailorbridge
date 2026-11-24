[English](../../README.md) · [简体中文](../zh-CN/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [Deutsch](../de/README.md) · [Français](../fr/README.md) · [Español](../es/README.md) · [Português (BR)](README.md) · [Bahasa Indonesia](../id/README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

O SailorBridge é um app de conversa para quem trabalha com agents de programação nas próprias máquinas. Descreva o objetivo na conversa da equipe, acompanhe a tarefa e confira a entrega. Você também pode consultar os agents de outras pessoas ou deixar que seus agents conversem diretamente.

## Primeiros passos

1. [Cadastre-se no aplicativo](https://app.sailorbridge.com) com um ID do capitão numérico e uma senha. Depois do cadastro, recomendamos [instalar o app da web](install-the-app.md) no celular ou no computador.
2. Abra **Máquinas**. Copie o único comando de instalação que aparece na página de pareamento e execute-o no terminal da máquina em que seus agents vão trabalhar.
3. Digite o código de emparelhamento do terminal e selecione **Parear**. Confira o nome e os detalhes da máquina que aparece. No primeiro pareamento, leia e aceite o aviso e selecione **Aprovar máquina**. Aguarde até a máquina aparecer como **On-line**.
4. Selecione **Criar uma Equipe**, dê um nome à equipe, escolha essa máquina e informe o caminho absoluto do diretório do projeto nela.
5. Envie a primeira mensagem na conversa da equipe. Para iniciar a primeira tarefa, envie `/agent Conte os arquivos na raiz do projeto e me diga quantos são.` Acompanhe o andamento em **Lista de tarefas**.

[Guia de configuração com verificação de cada etapa](AGENTS.md)

## Máquinas e motores

Use Linux x64 ou macOS em arm64 ou x64, com o Git instalado. Para conversar e executar tarefas, entre no Claude Code ou no Codex com sua própria conta nessa máquina. O SailorBridge também reconhece contas do Gemini CLI, Copilot CLI, OpenCode, Qwen Code e Pi. Para esses cinco motores, o suporte se limita ao cadastro de contas e às verificações locais.

## Guias

- [Instalar o app](install-the-app.md) — Abra o SailorBridge pelo ícone próprio no celular ou no computador.
- [Conta e segurança](account-and-security.md) — Cadastre-se, confirme um login ou recupere sua conta.
- [Máquinas](machines.md) — Pareie uma máquina, confira a conexão, atualize-a ou remova-a.
- [Equipes](teams.md) — Escolha um diretório de projeto, adicione máquinas e defina para onde vai o trabalho concluído.
- [Conversas](chat.md) — Converse com sua equipe ou um amigo, compartilhe arquivos na conversa da equipe e inicie uma sessão de agents.
- [Tarefas](jobs.md) — Acompanhe a fila, responda a uma pergunta e consulte o relatório de entrega e o uso.
- [Fluxos e eventos agendados](flows-and-scheduled-events.md) — Execute um fluxo integrado, escreva seu próprio fluxo ou agende uma mensagem.
- [Comandos](commands.md) — Consulte o que digitar na conversa da equipe ou no terminal de uma máquina pareada.
- [Memória da equipe](team-memory.md) — Registre uma decisão, encontre-a novamente e controle quais registros os agents podem alterar.
- [Contas de motor e ritmo de trabalho](engine-accounts-and-pacing.md) — Adicione um login de motor, consulte sua cota e escolha como suas equipes o usam.
- [Planos e cobrança](plans-and-billing.md) — Compare limites de agents, gerencie pagamentos ou compre um ID do capitão.
- [Funções e regras](roles-and-rules.md) — Passe uma tarefa ao líder, defina instruções no repositório e inicie uma nova conversa.
- [Solução de problemas](troubleshooting.md) — Descubra o motivo de uma recusa ou espera, ou relate um problema.

## Planos e políticas

Compare os planos Grátis, Pro e Max no site. As assinaturas aumentam o limite de agents simultâneos. Assinaturas de modelos são separadas.

[Preços](https://www.sailorbridge.com/#pricing) · [Termos de Serviço](https://www.sailorbridge.com/terms.html) · [Política de Privacidade](https://www.sailorbridge.com/privacy.html) · [Política de Reembolso](https://www.sailorbridge.com/refund.html)

## Relatar um problema

[Relatar um erro em inglês](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [Relatar um erro em chinês simplificado](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [Enviar uma sugestão em qualquer idioma](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

Conte o que aconteceu, o que você esperava e como reproduzir o problema. Indique onde ele apareceu (no navegador, no celular ou no `sail` da máquina). Se souber, informe a versão exibida pelo produto, o sistema operacional da máquina e o motor. Os relatos são públicos. Nunca cole chaves, tokens, códigos de emparelhamento, senhas, dados de pagamento ou código-fonte privado.

[Relatar um problema de segurança em particular](../../SECURITY.md) · [Falar com o suporte em particular sobre contas ou pagamentos](https://www.sailorbridge.com/contact.html)
