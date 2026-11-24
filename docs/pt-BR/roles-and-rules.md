[← SailorBridge](README.md)

# Funções e regras

Cada equipe tem um **Líder**. Você fala com ele na conversa da equipe. Ele responde a perguntas, executa comandos rápidos e encaminha trabalhos mais longos para um fluxo. Um trabalhador executa uma etapa do fluxo em uma máquina da equipe. Você fornece instruções permanentes ao motor no repositório do projeto. Não há editor de funções nem biblioteca de regras.

## Passe o trabalho adequado à equipe

Abra **Conversa** para sua equipe. Pergunte “Em qual branch estamos?” O **Líder** pode conferir o diretório da equipe e responder na conversa. Para uma verificação rápida em outra máquina da equipe, digite `@`, selecione a máquina e diga o que verificar. Você recebe um resumo do resultado.

Para receber um trabalho concluído e revisado, envie um pedido como “Atualize as instruções de configuração e peça uma revisão.” Quando o **Líder** propuser um fluxo em segundo plano, leia a tarefa no cartão. Selecione **Sim, Faça** para colocá-la na fila ou **Não É Isso** para explicar o que precisa mudar. Abra **Lista de tarefas** para acompanhar as etapas dos trabalhadores. Se um trabalhador precisar de uma decisão, o **Líder** verifica o que a equipe já sabe e pergunta na conversa quando precisar da sua resposta.

## Dê uma instrução permanente ao motor

Coloque as instruções para todo o projeto no `AGENTS.md` do repositório para o Codex ou no `CLAUDE.md` para o Claude Code. Por exemplo, registre qual comando deve ser executado antes de entregar uma mudança. O motor lê seu arquivo de instruções quando trabalha nesse repositório. Se a equipe precisar lembrar um fato em várias tarefas, você também pode pedir na conversa que ela o registre. [Memória da equipe](team-memory.md)

## Retome uma conversa depois de uma pausa

Envie a próxima mensagem na mesma conversa da equipe. O **Líder** pode iniciar uma nova sessão do motor após uma pausa longa, uma troca de motor ou uma mudança para outra máquina. Ele recupera o resumo salvo da equipe, as mensagens recentes, a memória da equipe e as tarefas inacabadas. Se aparecer **Organizando a conversa…**, você ainda pode enviar uma mensagem. O **Líder** responde depois de terminar o resumo.

## Se algo der errado

- Se um detalhe antigo estiver faltando, informe o número da tarefa, a decisão ou o arquivo relevante na próxima mensagem. Uma nova sessão recebe as 20 mensagens mais recentes e um resumo, quando disponível.
- Se uma instrução incorreta de uma conversa anterior continuar aparecendo, selecione **Limpar conversa**, confira o nome da equipe e confirme. As mensagens anteriores saem da visualização, e a sessão seguinte começa sem o resumo antigo. Se a instrução veio de um arquivo do repositório ou da memória da equipe, corrija-a na origem.
- Se o **Líder** ficar sem tempo, faça o pedido novamente em partes menores ou envie o trabalho mais longo como tarefa. [Comandos](commands.md)
