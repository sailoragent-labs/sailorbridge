[← SailorBridge](README.md)

# Memória da equipe

A memória da equipe guarda decisões, convenções e correções que o **Líder** e os trabalhadores podem usar em tarefas futuras. Cada registro tem um título, um corpo, uma origem e um número como `#6`. Um registro pertence a uma única equipe. Outras equipes e amigos não podem consultá-lo.

## Registre algo que vale a pena lembrar

Na conversa da equipe, diga o que lembrar e quando isso se aplica. Por exemplo, “Lembre que os exemplos de instalação devem ficar no guia de configuração. Use essa regra ao alterar um comando de instalação.” O **Líder** informa o que registrou. Abra o menu **Mais ações** na conversa da equipe e selecione **Memória da equipe** para ver o registro. Abra o título para ler o texto completo e ver quem o alterou por último.

## Encontre um registro e use-o na conversa

Abra **Pesquisar** em **Memória da equipe**. Digite palavras do título ou do corpo. Todas as palavras precisam corresponder para que haja um resultado de texto, e a primeira página também pode mostrar até três registros com sentidos parecidos. Registros fixados aparecem primeiro na lista normal.

Se souber o número, procure `#6` para obter somente o registro 6. A busca por `6` também encontra correspondências de texto. Abra o registro e selecione **Ir para o Chat**. O campo de mensagem agora contém `/memory #6`. Acrescente uma pergunta ou correção e envie.

## Edite, fixe, bloqueie ou exclua um registro

- Abra o registro, altere **Conteúdo** e selecione **Salvar**. A seção **History** mostra as últimas 10 versões. Confira **Observed** e **Expires** para fatos que podem mudar. Um registro marcado como **Expired** continua legível, então confira se a orientação ainda se aplica.
- Ative **Fixado** para incluir uma instrução no material fornecido ao **Líder** e aos trabalhadores. O registro mostra quanto do espaço de fixação a equipe está usando. Juntos, todos os títulos e corpos fixados podem usar até 8 KiB.
- Ative **Bloqueado** se só você deve poder alterar ou excluir o registro. Fixar um registro ainda permite que os agents o editem. Você pode editar um registro bloqueado pela web.
- Selecione **Excluir** e confirme para remover um registro permanentemente. Seu número não será reutilizado.

## Organize os registros da equipe

Envie `/memory-tidy` na conversa da equipe. A tarefa verifica os registros, marca os que vale a pena guardar, combina registros relacionados e exclui os que não terão utilidade futura. Abra o **Relatório de entrega** para ver o que foi feito e o que ainda exige sua decisão. Registros bloqueados ficam como estão se a tarefa propuser excluí-los ou combiná-los.

A organização automática roda no máximo uma vez por equipe em um período móvel de 24 horas quando há registros a verificar. Para executá-la somente a pedido ou por agendamento, abra **Fluxos da equipe**, selecione `memory-tidy` e desative **Organizar automaticamente**.

## Se algo der errado

- Uma fixação que ultrapassaria 8 KiB é recusada. Desfixe outro registro ou encurte o texto fixado e tente novamente.
- Se alguém tiver editado o registro enquanto você trabalhava, o corpo mais recente será exibido. Leia-o antes de reaplicar sua correção.
- Se duas atualizações usarem o mesmo título, uma correção do mesmo autor pode entrar em vigor diretamente. Caso contrário, um nível de confirmação mais alto ou uma observação mais recente no mesmo nível pode resolver. Se as atualizações exigirem uma decisão, o registro mostra **Conflito não resolvido** e mantém o texto atual. Abra-o, confira o fato e salve o texto correto. Um registro bloqueado exige sua decisão.
- Se o **Líder** informar que uma memória não foi salva, repita o que quer que ele lembre. Se um agent tiver sido impedido de alterar um registro bloqueado, faça a alteração em **Memória da equipe**.
