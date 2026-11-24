[← SailorBridge](README.md)

# Equipes

Uma equipe dá a um projeto uma conversa própria com o **Líder**, uma fila de tarefas, uma memória de equipe e uma ou mais máquinas. Você pode ter várias equipes e usar a mesma máquina em mais de uma. Só você pode ver e alterar as configurações da sua equipe.

## Crie uma equipe para seu projeto

1. Pareie a máquina que vai executar o líder. Quando ela mostrar **On-line**, selecione **Criar uma Equipe** na página de pareamento. Você também pode começar em **Equipes** selecionando **Criar equipe**. [Pareie uma máquina](machines.md)
2. Digite um **Nome da equipe** e selecione a máquina. Você pode escolher um **Avatar** e uma conta, um modelo e um nível de esforço para o líder entre as opções disponíveis nessa máquina, ou usar os padrões.
3. Em **Diretório do projeto**, digite o caminho absoluto na máquina selecionada, começando com `/`. Se já trabalha em um repositório, use o diretório local dele. Para trabalhar em um repositório remoto existente, clone-o primeiro nessa máquina e configure ali as credenciais do Git. O SailorBridge detecta o branch principal do repositório.
4. Escolha um **Destino** e selecione **Criar equipe**. A máquina aparece na lista da equipe. Abra **Conversa** para falar com o líder. [Use a conversa da equipe](chat.md)

Na primeira vez em que a equipe usa o caminho, ela abre a pasta existente ou a cria. Para uma pasta comum com arquivos, ela inicializa o Git e registra um instantâneo inicial. Se houver vários repositórios Git diretamente dentro da pasta, diga ao líder a qual você se refere. Cada tarefa trabalha em um repositório. O trabalho em vários repositórios é dividido em tarefas separadas.

## Escolha para onde vão as alterações

Abra sua equipe em **Equipes** para acessar **Detalhes da equipe**. Altere **Diretório do projeto** ou **Destino** nessa tela. As alterações valem a partir da próxima tarefa que uma máquina pegar.

| Destino | Onde encontrar os commits de uma tarefa |
| --- | --- |
| **Mescla automática** (padrão) | A máquina tenta enviar os commits ao branch principal remoto e depois avança o branch principal local por fast-forward. Confira o relatório de entrega se o branch principal tiver avançado ou se o remoto exigir revisão. Se o relatório listar um branch da tarefa, faça o merge desse branch no remoto. |
| **Branch** | Cada tarefa envia seu próprio branch `sb/<job>` para você revisar e mesclar. As outras tarefas começam no branch principal do projeto. |

Cada máquina usa o remoto Git e as credenciais do próprio repositório. Ela busca o branch principal remoto antes de iniciar uma tarefa e avança sua cópia local por fast-forward quando possível. Se o envio falhar, abra o **Relatório de entrega** da tarefa para ver o motivo, o branch local, o commit e o comando de push. [Encontre o relatório de entrega de uma tarefa](jobs.md)

## Adicione, mova ou remova uma máquina

Em **Detalhes da equipe**, abra **Lista de máquinas** e use o botão de mais para **Adicionar uma máquina**. Selecione uma máquina pareada e escolha **Igual à pasta da equipe** ou digite o caminho absoluto próprio dela em **Pasta do projeto**. Você pode editar esse caminho depois. Uma máquina elegível com capacidade pode então pegar uma tarefa da mesma fila.

Para remover uma máquina desta equipe, selecione-a e confirme **Remover da equipe**. Ela deixa de pegar novas tarefas dessa fila. Se você remover ou desativar a máquina marcada como **O líder é executado aqui**, a máquina restante que entrou primeiro na equipe assume como líder. A remoção da última máquina de uma equipe é bloqueada. Adicione a substituta primeiro.

## Configure como a equipe pega tarefas

Volte a **Detalhes da equipe** para mudar como a equipe executa trabalho.

- Em **Configurações de tarefas**, **Distribuição** controla o trabalho novo. Selecione **Pausada** para reter as tarefas na fila enquanto as tarefas em andamento continuam. Selecione **Normal** para que as máquinas voltem a pegar tarefas da fila.
- **Trabalhos simultâneos** usa **Sem limite** como padrão, portanto vale o limite de simultaneidade da sua conta. Selecione **Definir um número** para limitar quantas tarefas desta equipe podem rodar. A redução do número entra em vigor à medida que as tarefas em execução terminam.
- Em **Modelo do Líder**, selecione a conta, o modelo e o nível de esforço, se disponível. As contas aparecem com suas máquinas. Selecionar uma conta em outra máquina da equipe move o líder para lá na próxima mensagem. Ele usa o mesmo resumo da conversa e a mesma memória da equipe. As tarefas em andamento ficam em suas máquinas.
- Para os trabalhadores, escolha um modelo preferido e, quando disponível, o nível de esforço para cada nível de dificuldade e provedor. **Restaurar padrão** volta a opção ao padrão da equipe. Em **Lista de contas**, você pode restringir uma conta à escrita, à revisão ou ao líder. [Contas de motor e ritmo de trabalho](engine-accounts-and-pacing.md)

## Dissolva uma equipe

Abra **Detalhes da equipe**, selecione **Dissolver equipe**, confira quantas sessões de agents vão terminar e digite o nome da equipe para confirmar. A dissolução é permanente. Ela cancela tarefas abertas, exclui eventos agendados e remove a equipe da sua lista e dos pontos de acesso à conversa. As solicitações pendentes e as sessões de agents ativas da equipe são encerradas. Cada participante mantém seu histórico de sessão. As máquinas continuam pareadas com sua conta.

## Se algo der errado

- Se não houver máquina para selecionar, escolha **Parear máquina** ao criar uma equipe ou **Parear nova máquina** ao adicionar uma máquina. Se a máquina foi desativada, pareie-a novamente antes de adicioná-la.
- Se uma tarefa ou conversa informar que o diretório não pode ser criado, confira o caminho na máquina que tentou usá-lo. Um arquivo nesse caminho, falta de permissão de escrita ou um disco somente de leitura podem impedir a criação. Selecione **Alterar o diretório nas configurações da equipe** e informe um diretório gravável para essa máquina.
- Se a conta ou o modelo do líder deixar de estar disponível durante a criação, escolha novamente na lista atualizada. Se houver trabalho aguardando na fila depois da criação, leia **Por que não está em andamento** nos detalhes da tarefa para ver se o despacho, um limite ou uma conta está impedindo a execução.
