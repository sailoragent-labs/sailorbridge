[← SailorBridge](README.md)

# Fluxos e eventos agendados

Um fluxo dá à sua equipe uma forma de repetir uma tarefa. Ele tem um nome que você pode digitar na conversa, além de etapas e opções salvas para a equipe. Um evento agendado envia uma mensagem à conversa da equipe no horário que você escolher. A mensagem pode fazer uma pergunta ao líder ou iniciar um fluxo.

## Encontre e execute um fluxo

Na conversa da equipe, digite `/` para ver os fluxos ativos e suas descrições. Escolha um fluxo, acrescente o que você quer que ele faça e envie. Por exemplo, `/ask What should the export include?` inicia uma conversa sobre o que a exportação deve incluir. Um fluxo interativo faz perguntas na conversa. Um fluxo em segundo plano entra em **Lista de tarefas**.

Quando você envia um comando de fluxo em segundo plano, o **Líder** normalmente usa a conversa para redigir a descrição da tarefa e colocá-la na fila. Se **Iniciar direto** estiver ativado nesse fluxo, suas palavras passam a ser a descrição e a tarefa entra na fila imediatamente. A opção vem desativada nos fluxos integrados em segundo plano. Se o líder propuser uma tarefa por conta própria, selecione **Sim, Faça** para iniciá-la.

| Fluxo integrado | Quando usar e o que você recebe |
| --- | --- |
| `/ask` | Esclareça uma decisão. Responda a uma pergunta por vez para receber uma descrição dos requisitos. |
| `/plan` | Planeje um trabalho que exige várias tarefas. Leia o plano e o lote proposto, depois selecione **Colocar Todas na Fila**, **Revisar Plano** ou **Agora Não**. O planejamento é uma tarefa que você pode acompanhar. |
| `/agent` | Passe a um trabalhador uma tarefa mecânica ou demorada. Um trabalhador a executa e relata o resultado sem rodada de revisão. |
| `/write-review` | Passe à equipe uma tarefa de implementação e diga como verificá-la. Um escritor faz o trabalho, as verificações são executadas e o escritor e o revisor examinam o resultado. |
| `/memory-tidy` | Revise a memória da equipe, remova registros que perderam a utilidade e combine duplicatas. O relatório de entrega lista ações e sugestões que exigem sua decisão. A equipe também pode fazer isso automaticamente quando houver registros para verificar, no máximo uma vez em 24 horas. |
| `/docs-tidy` | Confira novamente a documentação afetada pelas mudanças e verifique amostras do restante em rodízio. O relatório de entrega distingue correções mecânicas de perguntas para você. |
| `/code-sweep` | Inspecione o código para encontrar oportunidades de limpeza. Leia as propostas numeradas no relatório de entrega e diga ao líder quais executar. A inspeção é somente de leitura. |
| `/write-flow` e `/edit-flow` | Descreva uma tarefa repetível para criar um fluxo ou diga como um fluxo existente deve mudar. O resultado é salvo para sua equipe. |

## Escolha quem escreve e quem revisa

Abra ⋯ na conversa da equipe, selecione **Fluxos da equipe** e abra `/write-review`. A página mostra as etapas e as opções que serão usadas nas próximas tarefas desta equipe.

| Opção | Como usar |
| --- | --- |
| **Quem escreve** | Mantenha **Automático** para selecionar um provedor de acordo com a dificuldade da tarefa ou selecione um motor para as etapas de escrita. |
| **Quem revisa** | Mantenha **Automático** para buscar um revisor independente de outra família de modelos ou selecione um motor para revisão. O escritor faz a própria autorrevisão. Os modelos efetivamente usados vêm das configurações da equipe. |
| **Passadas de autorrevisão** | Escolha de 0–10, com padrão 3. Em cada rodada, o escritor confere o trabalho, corrige o que encontrou e verifica novamente, até que uma rodada não encontre problemas ou o limite seja atingido. Use 0 para pular a autorrevisão. |
| **Quantas rodadas no máximo** | Escolha de 0–10, com padrão 6. Use 0 para Solo, que pula a revisão independente e mantém sua configuração de autorrevisão. |

Um problema P1 exige outra revisão da mudança inteira. Problemas menores exigem revisão das correções. A partir da terceira rodada, se não houver P1, o escritor pode concluir as correções restantes e entregar sem outra revisão. Se ainda houver problemas P1 no limite de rodadas, abra **Relatório de entrega** para ver o que impediu a conclusão da tarefa.

Para mesclar código, a verificação aplicável completa precisa passar no commit final. Se uma mudança apenas de documentação não tiver uma verificação aplicável, um revisor independente precisa aceitar o motivo. No modo Solo, uma mudança sem verificação a executar fica como **Incompleto**. [Leia as verificações e o relatório de entrega da tarefa](jobs.md)

## Crie ou edite um fluxo da equipe

1. Na conversa da equipe, envie `/write-flow` seguido das etapas, dos critérios de conclusão, do que fazer se uma etapa falhar e do que entregar. Por exemplo, `/write-flow List Markdown files changed since the last commit. Report their paths. If none changed, say so.`
2. Se o escritor precisar de uma decisão, responda à pergunta na conversa. Depois que o fluxo for escrito e verificado, a conversa mostra o nome com que ele foi salvo. Selecione **Ver fluxo** para ler a descrição, as etapas e as opções. O nome fica disponível no menu `/`.
3. Para alterar o fluxo, selecione **Editar no chat** ou envie `/edit-flow <name> <change>`. Diga o que deve mudar e o que deve ficar como está. A edição de um fluxo personalizado substitui a versão da equipe. A edição de um fluxo integrado gera um fluxo personalizado com outro nome. Leia o relatório de entrega para saber quais valores de opções entraram em vigor e quais regras de etapa foram descartadas.

Você também pode alterar as opções de um fluxo na página de detalhes. Se o fluxo seguir instruções salvas, você pode editá-las ali para a próxima execução. Desative **Ativado** para tirar o fluxo do menu da equipe para novas execuções. Tarefas na fila ou em andamento podem terminar. Os dois comandos de criação e edição de fluxos continuam disponíveis.

## Agende uma mensagem

1. No menu ⋯ da equipe, abra **Eventos agendados** e use o botão de mais para **Adicionar evento**. Em **O que dizer**, digite a mensagem que quer enviar, com até 16 KiB. Por exemplo, `/docs-tidy Check the project documentation.`
2. Selecione **Frequência**. Escolha **Uma vez** para uma data e um horário locais futuros, **Todo dia** para um horário diário ou **Dias úteis** para segunda a sexta. Com **A cada alguns minutos**, defina **Intervalo (minutos)** entre 5 e 720. Use **De** e **Até** para limitar as execuções a uma parte do dia.
3. Confira **Fuso horário**, que começa com o fuso do navegador, e salve. A lista mostra a primeira linha da sua mensagem e o próximo horário de execução. A criação do evento autoriza a mensagem. No horário marcado, ela aparece na conversa sob seu nome, marcada como **Agendado**. Cada disparo usa um turno completo do líder.

Os horários seguem o fuso selecionado. Se uma mudança para o horário de verão pular o horário agendado, o evento usa o próximo horário válido. Se o relógio repetir o horário, usa a primeira ocorrência. Um evento de intervalo com janela de horário pula as ocorrências fora dessa janela.

Abra o evento para alterar a mensagem ou o horário. Salvar recalcula a próxima execução. Desative o evento para parar as mensagens futuras e ative-o quando quiser retomar. A reativação começa a contar a partir desse ponto. Após uma interrupção do serviço de agendamento, somente a ocorrência perdida mais recente é enviada. Busque um evento pelo texto ou pelo número exato, como `#6`. Use **Concluído** para encontrar um evento único que já terminou.

## Se algo der errado

- Se a conversa não reconhecer um fluxo, digite `/` para ver os nomes ativos para a equipe. Reative o fluxo em **Fluxos da equipe**, se necessário. Se um plano não puder colocar seu lote na fila porque `/write-review` está desativado, ative-o antes de enviar o trabalho novamente.
- Uma equipe pode ter 30 fluxos personalizados. Ao atingir o limite, exclua um fluxo que você não precisa mais antes de criar outro. Se o nome já estiver em uso, edite o fluxo existente ou escolha outro nome. Se uma edição informar que uma regra de etapa descartada é longa demais para o relatório de entrega, encurte ou mova a regra na página do fluxo e tente editar novamente.
- Uma equipe pode ter até 20 eventos agendados. Ao atingir o limite, exclua um evento antes de adicionar outro. Se um evento único já foi executado, crie outro para repeti-lo. Use um horário futuro e um intervalo dentro da faixa indicada acima.
- Se uma mensagem agendada mencionar um fluxo ausente ou desativado, ou um item numerado que não existe, a ocorrência é consumida. Corrija a mensagem ou ative o fluxo antes da próxima ocorrência. Se um fluxo interativo agendado informar que outro está em andamento, ele espera um disparo posterior.
