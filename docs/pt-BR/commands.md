[← SailorBridge](README.md)

# Comandos

Use a conversa da equipe para fazer um pedido ao **Líder** ou iniciar um fluxo. Use `sail` no terminal para gerenciar a máquina onde está instalado, consultar o trabalho da equipe ou executar um comando em outra máquina da mesma equipe.

## Escolha um comando na conversa da equipe

Abra **Conversa** para sua equipe e digite `/`. O menu lista quatro atalhos, os fluxos ativos da equipe e, por último, `/clear`. Selecione um item, acrescente seu pedido no próprio idioma e envie. Os nomes dos comandos continuam em inglês. A seleção de `/clear` tem efeito imediato.

| O que digitar | O que acontece |
| --- | --- |
| `/job #12 What is this waiting for?` | O **Líder** recebe a tarefa 12 e sua pergunta. |
| `/event #6 Move this to weekdays.` | O **Líder** recebe o evento agendado 6 e a alteração solicitada. |
| `/memory #3 When does this apply?` | O **Líder** recebe o registro de memória 3 e sua pergunta. |
| `/do Check the current branch.` | O **Líder** executa o trabalho neste turno da conversa e relata o resultado, incluindo o que não conseguiu fazer. |
| `/clear` | Oculta as mensagens anteriores da equipe e inicia uma nova conversa. |

Use o número da lista correspondente da equipe. Tarefas, eventos e registros de memória têm numerações próprias. O botão **Ir para o Chat** em uma página de detalhes preenche o atalho e o número corretos. Para mencionar uma máquina, digite `@` e selecione-a na lista da equipe.

## Execute um fluxo pelo nome

| Comando | O que você recebe |
| --- | --- |
| `/ask` | Uma pergunta por vez, seguida de uma descrição dos requisitos na conversa. |
| `/plan` | Uma tarefa de planejamento. Leia o plano e decida se quer colocar as tarefas propostas na fila. |
| `/agent` | Um trabalhador executa a tarefa e relata o resultado. |
| `/write-review` | Um escritor faz o trabalho, executa as verificações e revisa o trabalho de acordo com as configurações de revisão do fluxo. |
| `/memory-tidy` | Uma tarefa que verifica, combina ou remove registros da memória da equipe. |
| `/docs-tidy` | Uma tarefa que verifica documentos do projeto e relata problemas que exigem sua avaliação. |
| `/code-sweep` | Uma inspeção somente de leitura com tarefas numeradas de limpeza que você pode escolher executar. |
| `/write-flow` | Descreva uma tarefa que se repete. Se a tarefa for concluída com sucesso, o novo fluxo será salvo nesta equipe. |
| `/edit-flow` | Informe o nome do fluxo e a alteração. Uma edição bem-sucedida substitui um fluxo personalizado. A edição de um fluxo integrado cria um fluxo personalizado com outro nome. |

Por exemplo, envie `/agent Count the top-level files in this project.` Enviar um fluxo em segundo plano por conta própria autoriza a tarefa. O **Líder** redige a tarefa com base na conversa ou, se **Iniciar direto** estiver ativado, seu texto vai direto para a fila. Abra **Ver detalhes** na linha da tarefa na conversa para acompanhá-la. Se o **Líder** propuser um fluxo em segundo plano em resposta a uma mensagem comum, leia o cartão e selecione **Sim, Faça** para iniciá-lo. [Fluxos e eventos agendados](flows-and-scheduled-events.md)

## Pareie, verifique ou remova uma máquina

| Comando de terminal | Quando usar |
| --- | --- |
| `sail login` | O comando de instalação o executa para você. Execute-o de novo para obter um novo código de pareamento ou restaurar o serviço no mesmo endereço com as credenciais existentes. |
| `sail host status` | Confira o pareamento, a conexão, o serviço, a versão e o local do log. Adicione `--trust` para ver a impressão digital da chave do servidor salva na máquina. |
| `sail --version` | Mostre a versão instalada. |
| `sail upgrade` | Verifique agora se há uma atualização. O resultado informa se uma nova versão foi instalada, se a versão já era a atual ou se a atualização falhou. |
| `sail host service status` | Confira o serviço em segundo plano. Use `sail host service install`, `sail host service restart` ou `sail host service stop` para instalar, reiniciar ou parar o serviço. |
| `sail host run` | Execute o serviço da máquina em primeiro plano quando não houver outra instância em execução. |
| `sail confirm` | Em **Confirme que é você**, obtenha um código de login de uso único no terminal de uma máquina pareada. |
| `sail recover` | Em **Esqueceu a senha?**, obtenha o ID do capitão e um código de recuperação de senha de uso único no terminal de uma máquina pareada. |
| `sail uninstall` | Remova o SailorBridge e seus dados locais, incluindo cópias de trabalho e logs. Seus diretórios de projeto e logins de motores são mantidos. |

Para logins de motores, `sail account list` mostra o que a máquina reconhece. Use `sail account add <name> <directory>` para cadastrar um diretório de login, `sail account remove <name>` para remover um cadastro ou ignorar um login padrão e `sail account restore <provider>` para voltar a reconhecer um login padrão ignorado. Para um endpoint compatível, `sail account create <provider>` grava um modelo de configuração em `~/.sailorbridge/`, que `sail uninstall` remove. [Configure uma conta GLM, DeepSeek ou Kimi usando um modelo](engine-accounts-and-pacing.md#configure-uma-conta-glm-deepseek-ou-kimi-usando-um-modelo)

## Trabalhe com os itens numerados da equipe

No terminal, execute os comandos a seguir no diretório de projeto configurado para a equipe em uma máquina pareada. Use os números de item da equipe. Por exemplo, uma tarefa exibida como `#12` na conversa fica como `12` no comando de terminal.

| Tarefa | Comandos que você pode executar no terminal |
| --- | --- |
| Encontre uma tarefa | `sail job list` lista as tarefas abertas. Adicione `--all` para incluir tarefas encerradas. `sail job get 12` mostra a tarefa 12. Adicione `--json` para ver todos os detalhes. |
| Pare ou exclua uma tarefa | `sail job stop 12` para a tarefa. `sail job delete 12` exclui o registro de uma tarefa encerrada. |
| Encontre um evento | `sail event list` lista os eventos ativos que ainda precisam ser executados. Adicione `--all` para incluir os eventos desativados ou concluídos. `sail event get 6` mostra a mensagem e o agendamento. |
| Exclua um evento | `sail event delete 6` remove o evento agendado. |
| Exclua um registro de memória | `sail memory delete 3` exclui permanentemente um registro. Para excluir um registro bloqueado, use **Memória da equipe** no aplicativo. |

Os comandos abaixo exigem uma sessão ativa do **Líder** ou uma tarefa em execução. Ao executá-los no terminal, você recebe `local_team_context_missing` mesmo no diretório da equipe. Peça ao **Líder** o que você precisa na conversa da equipe. Para trabalhar diretamente com um item existente, abra **Lista de tarefas**, **Eventos agendados** ou **Memória da equipe** no aplicativo. Os trabalhadores têm acesso somente de leitura a tarefas e eventos.

| Quem executa | Tarefa e comandos |
| --- | --- |
| **Líder** | `sail job create <flow> "<task>"` coloca um fluxo em segundo plano na fila. `sail job edit 12 "<revised task>"` altera uma tarefa aberta. `sail job retry 12` continua o trabalho elegível com o mesmo número. |
| **Líder** | `sail event create "Check the queue" --weekdays 09:00` agenda uma mensagem para a conversa da equipe no fuso horário da máquina. Outros tipos de agendamento usam `--once`, `--daily` ou `--every`. Use `--tz` para especificar um fuso horário. `sail event edit 6 --disable` pausa o evento. |
| **Líder** ou trabalhador | `sail memory list` lista os registros. `sail memory titles` lista os títulos. `sail memory search "release checklist"` retorna até 10 resultados. `sail memory get 3` lê o registro. |
| **Líder** ou trabalhador | `sail memory create "<title>" "<body>"` registra um fato ou propõe uma correção com o mesmo título. `sail memory edit 3 "<body>"` altera um registro. `sail memory conflicts` lista conflitos não resolvidos. |
| **Líder** | `sail memory resolve <id> --value "<correct text>"` resolve um conflito. O comando recebe o ID do conflito. Um registro bloqueado exige sua decisão em **Memória da equipe**. |
| **Líder** ou trabalhador | `sail memory list --tidy` lista os candidatos e as versões. `sail memory review 3 --rev <version>` marca um registro que vale a pena manter. `sail memory merge` aceita argumentos `--entry <id>:<version>` repetidos, além de `--title` e `--body`. Entre as tarefas de trabalhador, apenas `/memory-tidy` pode excluir registros. |

Se um comando indicar uma decisão pendente, confira o valor atual na resposta antes de presumir que a alteração entrou em vigor.

## Execute um comando localmente ou em outra máquina da equipe

Para um comando local, `sail run git status` envia a saída ao terminal. Para um comando longo e não interativo, adicione `--fold` antes do comando. Você recebe o resultado, as últimas linhas da saída e o caminho do log completo. Para uma janela local do tmux, `sail tmux read <window>` mostra o texto. `sail tmux send <window> "<text>"` preenche o campo de entrada. Envie `sail tmux send <window> --key Enter` quando quiser enviar o texto digitado.

Para executar um comando em outra máquina sua na mesma equipe, comece no diretório da equipe e substitua `build-machine` pelo nome da máquina de destino. Por exemplo, `sail exec build-machine git status --short` roda no diretório da equipe na máquina de destino. O código de saída e as últimas 40 linhas da saída combinada, até 16 KiB, retornam ao seu terminal. Use `--json` antes do nome da máquina para obter um único resultado em JSON.

O limite de tempo padrão é de 5 minutos. Para alterá-lo, coloque `--timeout` e um número positivo de segundos antes do nome da máquina. Uma máquina de origem pode ter até 8 comandos aguardando resultados. Pressionar Ctrl-C faz seu terminal parar de esperar. O comando remoto ainda pode estar em execução.

## Se algo der errado

- Se um comando de conversa for desconhecido, digite `/` e escolha um fluxo ativo. Se um cartão de confirmação antigo apontar para um fluxo desativado, ative-o em **Fluxos da equipe** ou escolha um fluxo disponível e envie uma nova solicitação.
- Se um atalho numerado não for encontrado, abra **Lista de tarefas**, **Eventos agendados** ou **Memória da equipe** da equipe. Confira o número e inclua o `#` na conversa.
- Se `sail exec` não identificar a equipe, mude para um dos diretórios de equipe listados. Se a máquina de destino estiver off-line ou tiver parado de aceitar trabalho, tente novamente quando ela estiver on-line e aceitando trabalho. Uma máquina de destino on-line tem até 10 minutos para pegar um comando da fila. Se ela ficar off-line antes de pegar o comando, o comando espera 60 segundos pela reconexão. Se a máquina se desconectar depois de começar, confira o que o comando fez antes de executá-lo novamente.
