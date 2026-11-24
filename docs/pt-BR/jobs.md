[← SailorBridge](README.md)

# Tarefas

Uma tarefa é uma execução de um fluxo. Cada equipe tem uma fila compartilhada por suas máquinas. Você pode passar uma tarefa à equipe na conversa, consultar o andamento pelo número e abrir o relatório de entrega para ver o que foi produzido e o que ainda exige sua atenção.

## Coloque trabalho na fila

Na conversa da equipe, envie o nome de um fluxo e uma tarefa, por exemplo `/agent Count the files at the top level of this project and report the count.` A tarefa entra na fila e uma máquina elegível a pega quando tem capacidade. A máquina executa a tarefa na própria cópia de trabalho.

Se o **Líder** propuser trabalho na conversa, leia a proposta e selecione **Sim, Faça** para colocá-lo na fila. Para um plano com várias tarefas, leia a lista antes de selecionar **Colocar Todas na Fila**. A opção **Revisar Plano** permite descrever uma alteração. A opção **Agora Não** deixa o lote fora da fila. Depois de aceito o lote, cada tarefa recebe seu próprio número. [Escolha um fluxo](flows-and-scheduled-events.md)

## Encontre uma tarefa e leia seu estado

Abra o menu ⋯ na conversa da equipe e selecione **Lista de tarefas**, ou selecione **Ver detalhes** na tarefa na conversa. A lista começa com **Rodando** e depois lembra o último filtro usado neste navegador. Selecione **Todas** para incluir as tarefas encerradas. Busque pelo texto da tarefa ou pelo nome do fluxo, ou digite o número completo com o sinal de cerquilha, como `#6`, para localizar a tarefa em qualquer filtro.

| O que aparece | O que significa |
| --- | --- |
| **Fila** | A tarefa está esperando uma máquina pegá-la. A linha abaixo informa o motivo. Um número de tarefa citado identifica um pré-requisito que está pendente. |
| **Rodando** | Uma máquina pegou a tarefa. Abra-a para ver a etapa atual e a máquina. |
| **Aguardando o líder** ou **Esperando você** | O líder cuida das perguntas que consegue responder. Se precisar da sua decisão, selecione **Responder** e responda na conversa. O filtro **Você** encontra as tarefas que aguardam você. |
| **Feita** | O fluxo entregou o resultado. **Concluído, verificações falharam** indica que há uma entrega com uma verificação que falhou. Leia a verificação antes de usar o resultado. |
| **Incompleto** | O fluxo parou antes de entregar tudo o que foi solicitado. Leia onde ele parou e o que falta. O trabalho já produzido é mantido. |
| **Falhou** | Um erro encerrou a execução. Abra o relatório e **Nota da máquina** para ver o motivo. |
| **Cancelada** | A tarefa foi parada. Seu registro continua disponível na lista. |

**Pausada** e **Cota** também podem explicar por que uma tarefa está parada. Abra **Por que não está em andamento** para ver o que ela aguarda e qual ação está disponível, se houver.

## Leia os detalhes da tarefa, o relatório de entrega e o uso

Selecione a linha numerada. **Detalhes da tarefa** mostra o estado, **Em execução** e **Rodadas**. **Informações da tarefa** inclui a máquina, quem iniciou a tarefa e **Na fila**. Expanda **Etapas** para ver qual etapa rodou, quanto tempo levou e quais motor e modelo foram usados. Quando aparece, **Problemas de qualidade** reúne os problemas encontrados na autorrevisão, na revisão por pares e na última rodada dessa revisão.

Quando a tarefa terminar, abra **Relatório de entrega**. Leia **Alterações**, **Verificações**, **Observações da revisão**, **Não conferido** e **Precisa da sua decisão**. Quando uma tarefa concluída tem uma verificação que falhou, ela aparece primeiro. Em uma tarefa que gerou commits, veja para onde eles foram. Se a máquina não conseguiu enviá-los, o relatório mostra o branch local, o commit, o motivo e um comando que você pode executar. Uma tarefa que só gera um relatório pode entregar a resposta sem um commit.

Abra **Uso** e expanda **Por rodada** para ver a contagem de tokens e os modelos efetivamente usados. O uso é registrado por provedor, conta e modelo. Os totais da entrega correspondem à última vez que uma máquina pegou a tarefa. O tempo na fila é registrado separadamente do tempo de execução.

## Pause, altere, pare ou continue uma tarefa

- Em uma tarefa na fila, selecione **Pausar** para evitar que uma máquina a pegue, depois **Retomar** quando ela puder rodar. Selecione **Começar agora** para mover uma tarefa para o início da fila. Se uma vaga estiver ocupada, continue esperando ou pare explicitamente uma tarefa em andamento para liberar a vaga.
- Para alterar uma tarefa aberta, selecione **Ir para o Chat** na própria tarefa. Isso preenche o número da tarefa. Acrescente os novos requisitos e envie a mensagem. Se o líder propuser uma alteração, selecione **Sim, Alterar**. Em uma tarefa na fila, a descrição é trocada no mesmo registro. Uma tentativa em execução para e a tarefa volta à fila com o mesmo número.
- Para encerrar uma tarefa, selecione **Parar** e confirme. Uma tarefa que você parou explicitamente precisa de sua instrução para continuar. Se uma tarefa encerrada tiver um ponto de retomada salvo e trabalho aproveitável, abra ⋯ e selecione **Continuar**. Ela usa o mesmo número e a cópia de trabalho mantida ou o branch enviado. Se você alterar os requisitos antes de continuar, ela começa do início.
- Selecione **Refazer** para colocar na fila uma nova tarefa com o fluxo, a descrição, o repositório e as opções originais. Ela recebe um novo número e você ainda pode ler a tarefa anterior. Use isso quando **Continuar** estiver indisponível. A opção **Excluir** remove permanentemente o registro de uma tarefa encerrada após a confirmação.

## Se algo der errado

- Se o despacho estiver pausado para toda a equipe, selecione **Retomar distribuição** quando quiser que as máquinas peguem novas tarefas. Se a equipe ou sua conta tiver atingido o limite de simultaneidade, a tarefa começa quando uma vaga é liberada. [Configurações de despacho da equipe](teams.md)
- Se uma tarefa espera sua resposta, você pode responder mesmo depois dos primeiros cinco minutos. Após cinco minutos, a máquina libera a vaga. Depois que você responder, a mesma máquina retoma a tarefa assim que estiver livre.
- Se uma tarefa precisar de escritor ou revisor, selecione **Ir para contas**. Uma única máquina deve ter as contas necessárias para toda a tarefa. Se todas as máquinas candidatas recusarem, a tarefa falha e suas notas informam o motivo de cada máquina. Se a espera for por cota ou ritmo, confira o horário estimado. O trabalho é retomado quando houver cota ou capacidade disponível. [Contas de motor e ritmo de trabalho](engine-accounts-and-pacing.md)
- Se uma máquina perder contato, ela pode retomar o trabalho ao se reconectar. Após 30 minutos sem renovar sua reserva da tarefa, outra máquina da equipe pode pegá-la e recomeçar. Três perdas de contato na mesma tarefa encerram a tarefa como **Falhou**. Confira a máquina antes de continuar ou refazer a tarefa. [Confira a máquina](machines.md)
- Após uma falha recuperável do sistema, a tarefa pode continuar automaticamente até 10 vezes durante sua vida útil. Se continuar encerrada, leia o último relatório, resolva a causa e use **Continuar** se estiver disponível.
