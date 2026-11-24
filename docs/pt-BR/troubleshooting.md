[← SailorBridge](README.md)

# Solução de problemas

Comece onde o trabalho parou. Para login ou pagamento, leia a mensagem na página em questão. Para um problema de máquina, confira o terminal nessa máquina. Para uma tarefa, abra **Lista de tarefas**, selecione a tarefa e leia **Por que não está em andamento**. A seção informa se a tarefa precisa de uma ação sua ou se será retomada automaticamente.

## Recupere o acesso à conta

| O que aparece | O que fazer |
| --- | --- |
| Seu ID do capitão já está em uso ou o limite de cadastros de hoje foi atingido | Tente outro ID disponível. Se o limite diário de cadastros grátis tiver sido atingido, volte amanhã. Para um ID pago, use o **Link de resgate** original para concluir o cadastro. |
| **Confirme que é você** depois de digitar a senha | Use seu autenticador, execute `sail confirm` em uma máquina pareada e digite o código, ou, quando essa opção aparecer, selecione o número exibido em um navegador reconhecido. Use a solicitação de login mais recente. Se ela expirar, entre novamente. |
| Muitas tentativas de login malsucedidas ou um código do autenticador reutilizado | Após 5 falhas em 15 minutos, o bloqueio padrão é de 15 minutos. Aguarde o tempo exibido. Se um código do autenticador já foi usado, espere o próximo. |
| Você esqueceu a senha ou o código de recuperação expirou | Execute `sail recover` no terminal de uma máquina pareada. Selecione **Esqueceu a senha?** e digite o ID do capitão e o código de 8 caracteres que o comando mostra. O código dura 10 minutos e funciona uma vez. Um novo código daquela máquina substitui o anterior. Se as credenciais da máquina forem recusadas, tente outra máquina pareada. Sem uma máquina pareada utilizável, cadastre um novo ID. |
| **Recuperação da conta aguardando aplicação** | Uma máquina pareada há menos de 72 horas exige uma espera de 72 horas, inclusive após um reparo que substituiu suas credenciais. Em um pareamento mais antigo, a verificação em duas etapas ativada há pelo menos 72 horas exige o código do autenticador para recuperação imediata. Sem esse código, envie a solicitação de 72 horas. Aguarde até o horário exibido. Se você não solicitou a recuperação, selecione **Cancelar esta recuperação** em um dispositivo com sessão iniciada. |

## Faça uma máquina ou equipe voltar a funcionar

- Se a instalação parar por falta do Git, instale o Git e execute novamente o comando de **Parear nova máquina**. Se o Claude Code ou o Codex estiver desconectado, ainda é possível concluir o pareamento. Execute `claude login` ou `codex login` na máquina antes de pedir à equipe que trabalhe.
- Se o código de pareamento expirar, execute `sail login` para gerar outro. Digite-o em **Parear nova máquina**, selecione **Parear** e compare o nome da máquina e o **Código da chave** com o terminal antes de selecionar **Aprovar máquina**. Se os códigos forem diferentes, cancele o pareamento e comece de novo. Após a aprovação, aguarde a conexão da máquina.
- Se a máquina não se conectar em 10 minutos, execute `sail host status`. Ele mostra o estado do serviço e o caminho do log. No mesmo endereço, execute `sail login` para restaurar o serviço. Para `origin_mismatch`, se você pretende trocar de endereço, `sail uninstall` remove os dados locais do SailorBridge, incluindo as cópias de trabalho das tarefas. Depois, execute o comando de instalação na página **Máquinas** do aplicativo que você quer usar e pareie novamente.
- Se uma atualização falhar, abra a máquina em **Máquinas** e siga a orientação e o comando de reparo exibidos. Se o download falhar, tente mais tarde com `sail upgrade`. Se a gravação falhar, confira o espaço em disco e use a conta que instalou `sail`.
- Se a criação da equipe pedir uma máquina, pareie uma e aguarde **On-line**. Se não conseguir remover a última máquina da equipe, use **Adicionar uma máquina** primeiro. Se o diretório da equipe não puder ser criado, selecione **Alterar o diretório nas configurações da equipe**. Use um caminho absoluto de diretório na máquina onde ocorreu o erro. Um arquivo nesse caminho, falta de permissão de escrita ou um disco somente de leitura podem impedir a criação. [Máquinas](machines.md) · [Equipes](teams.md)

## Obtenha uma resposta na conversa

- Se a máquina do **Líder** estiver off-line, a conversa da equipe guarda sua mensagem e a entrega quando a máquina se reconectar. Se a equipe não tiver uma máquina utilizável, adicione uma e envie a mensagem de novo.
- Se o motor exigir login, entre na máquina indicada. Se todas as contas utilizáveis pelo **Líder** estiverem sem cota, envie novamente depois do horário de renovação. Se um modelo for recusado, siga a instrução de atualização do motor e tente novamente, ou selecione uma conta e um modelo disponíveis. [Contas de motor e ritmo de trabalho](engine-accounts-and-pacing.md)
- Se sua mensagem tiver sido enviada como resposta a uma pergunta em vez de ir para o **Líder**, responda à pergunta aberta ou selecione **Parar** no cartão dela. Depois, envie a mensagem. Se um cartão de confirmação foi substituído ou já recebeu resposta, confira o cartão ou a tarefa mais recente antes de agir.
- Se um arquivo for recusado, use a conversa da equipe e envie no máximo 4 anexos por mensagem, de até 5 MiB cada. Os tipos aceitos são PNG, JPEG, WebP, PDF, texto simples e Markdown. Se um anexo estiver indisponível, selecione-o novamente. Um arquivo carregado e não enviado expira após 24 horas. Ao atingir o limite de 1 GiB da conta, espere liberar espaço à medida que os arquivos enviados expirarem após 30 dias. Se a mensagem for grande demais, divida o texto em mensagens de até 64 KiB.
- Em uma sessão de agents, se a conta precisar de login ou cota, resolva isso antes de selecionar **Retomar**. Se uma sessão entre equipes atingir o limite de rodadas, o destinatário pode estendê-la por 10 ou 20 rodadas ou selecionar **Rodadas ilimitadas**. Quem iniciou a sessão aguarda o destinatário. [Conversas](chat.md)

## Descubra por que uma tarefa está esperando

Abra a tarefa em **Lista de tarefas**. Leia **Por que não está em andamento** antes de decidir se precisa reiniciar algo.

| O que impede a tarefa de rodar | O que fazer |
| --- | --- |
| O despacho está pausado ou esta tarefa está pausada | Use **Retomar distribuição** para a equipe ou **Retomar** para a tarefa individual. |
| As máquinas estão ocupadas, a equipe atingiu seu limite de tarefas ou o plano atingiu seu limite de agents | O trabalho começa quando uma vaga é liberada. Confira **Trabalhos simultâneos** para a equipe ou **Limite de simultaneidade** em **Assinatura** para sua conta. |
| A tarefa precisa de um escritor e um revisor | Selecione **Ir para contas**. Confirme que uma máquina da equipe tem as contas necessárias habilitadas para as duas etapas. Um escritor em uma máquina e um revisor em outra não podem executar juntos a mesma tarefa. |
| A máquina atingiu o limite de ritmo ou esgotou a cota | Aguarde o horário estimado. Para uma espera por ritmo, **Mudar para Sem Limite** altera o ritmo de todas as equipes após a confirmação. Se a cota acabou, a tarefa verifica novamente e continua na mesma máquina quando a cota voltar. |
| A tarefa precisa de uma resposta ou de um pré-requisito | Se a pergunta for para você, selecione **Responder**. Depois de 5 minutos esperando uma resposta, a tarefa libera a vaga. Quando você responder, ela continua assim que a máquina original estiver livre. Se houver um pré-requisito, abra o número de tarefa mostrado e confira o resultado. |
| Uma máquina recusou a tarefa ou deixou de se comunicar | Leia o motivo abaixo da tarefa. Outra máquina elegível pode pegar uma tarefa recusada. Se todas as candidatas recusaram, abra **Nota da máquina** para ver os motivos. Se a máquina em execução perdeu a conexão, ela pode retomar a tarefa se voltar primeiro. Após 30 minutos sem renovar a reserva, outra máquina pode começar do início. |
| **Incompleto** ou **Falhou** | Abra **Relatório de entrega** para ver a última etapa, o motivo e o trabalho mantido. Corrija o problema informado. Use **Continuar**, se disponível, para retomar a mesma tarefa com o trabalho mantido, ou **Refazer** para recomeçar. Se um push falhou, o relatório informa o branch, o commit e o comando de push do trabalho mantido localmente. |

## Corrija um comando, agendamento ou registro de memória

- Se o terminal disser “Execute este comando dentro de um trabalho ou de uma sessão do líder da equipe.” (`local_team_context_missing`), o comando exige uma sessão ativa mesmo no diretório da equipe. Peça ao **Líder** na conversa da equipe ou abra **Lista de tarefas**, **Eventos agendados** ou **Memória da equipe** para trabalhar com um item existente. [Comandos para itens numerados da equipe](commands.md#trabalhe-com-os-itens-numerados-da-equipe)
- Se um comando de barra for desconhecido, digite `/` para ver os fluxos ativos. Se faltar uma referência numerada, confira a equipe e o tipo de item e digite `#` antes do número na conversa. Se `sail exec` informar que a máquina de destino está off-line, o comando não começou. Se o resultado se perdeu *depois* que o comando começou, confira a máquina de destino antes de tentar novamente. [Comandos](commands.md)
- Se um evento agendado for recusado, escolha um horário futuro para um evento único ou um intervalo de 5–720 minutos para um evento recorrente. Uma equipe pode ter até 20 eventos. Exclua um evento desnecessário para liberar espaço. Para que um evento único já concluído rode novamente, crie-o de novo. Se um evento mencionar um fluxo desativado ou um número inexistente, corrija a mensagem para a próxima execução. [Fluxos e eventos agendados](flows-and-scheduled-events.md)
- Se uma alteração de memória for recusada, abra **Memória da equipe**. Você pode alterar um registro bloqueado nessa tela. Se outra pessoa o alterou antes, leia o corpo mais recente antes de salvar. Se o espaço para itens fixados estiver cheio, desfixe ou encurte um registro antes de fixar outro. [Memória da equipe](team-memory.md)

## Confira um pagamento que não foi concluído

Se o pagamento estiver pendente, volte à compra original e confira o status antes de pagar novamente. Se a assinatura mostrar **Pagamento falhou**, **Atualizar Forma de Pagamento e Pagar Saldo** abre a página de pagamento para quitar o saldo pendente. [Planos e cobrança](plans-and-billing.md)

## Se algo der errado

Se o problema persistir, anote as etapas, a mensagem exata, o que esperava e onde aconteceu. Inclua a versão, o sistema operacional da máquina e o motor, se souber. Para problema de conta ou pagamento, use o contato privado indicado no README. Para problema de segurança, use o link privado de segurança. Mantenha credenciais, códigos de pareamento, dados de pagamento e código-fonte privado fora de relatos públicos. [Relatar um problema](README.md#relatar-um-problema)
