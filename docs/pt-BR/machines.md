[← SailorBridge](README.md)

# Máquinas

Uma máquina é um computador que você conecta à sua conta para executar o líder de uma equipe ou pegar tarefas. Instale `sail` em cada máquina e aprove o pareamento no navegador. O serviço em segundo plano mantém a conexão depois que você fecha o terminal.

## Instale e pareie uma máquina

1. Use uma máquina que você controla com Linux x64 ou macOS arm64 ou x64. Instale o Git. Para conversar e executar tarefas, instale Claude Code ou Codex e entre nesse computador com sua própria conta do motor. Você pode terminar o pareamento antes de entrar no motor.
2. No aplicativo, abra **Máquinas** e depois **Parear nova máquina**. Copie o comando de instalação mostrado ali para um terminal na máquina que quer conectar. Você pode executá-lo de qualquer diretório. Ele instala `sail`, inicia o pareamento e exibe um código de oito caracteres válido por 10 minutos.
3. Digite o código em **Código de emparelhamento** no navegador e selecione **Parear**. Compare o nome da máquina e o **Código da chave** com o terminal. No primeiro pareamento, leia o aviso antes de aceitá-lo. Os agents podem ler, alterar e excluir arquivos, usar credenciais e acessar a rede com as permissões do usuário do sistema operacional que executa `sail`. Use uma máquina ou um contêiner dedicado se precisar de isolamento.
4. Selecione **Aprovar máquina**. Mantenha a máquina conectada enquanto ela recebe as credenciais e inicia o serviço. Quando **Máquinas** mostrar **On-line** e o terminal confirmar a conexão, você pode selecionar **Configurar Contas** ou **Criar uma Equipe**. [Crie uma equipe](teams.md)

## Confira a conexão ou pareie mais máquinas

Abra uma máquina em **Máquinas** para ver nome, plataforma, **Última conexão**, **Pareada em** e **Versão do cliente**. Você pode editar o nome nessa tela para facilitar a identificação das máquinas. Na própria máquina, execute `sail host status` para conferir o pareamento, a conexão e o estado do serviço e localizar o log local.

Para usar outro computador, abra **Parear nova máquina** novamente e execute nele o comando exibido. Quando ele ficar on-line, adicione-o à equipe e configure a pasta do projeto nessa máquina. Uma máquina pode servir a várias equipes. Cada tarefa roda em uma máquina elegível da equipe. [Gerencie as máquinas de uma equipe](teams.md)

## Atualize ou repare a instalação

As atualizações automáticas vêm ativadas. Depois de verificar uma atualização, o serviço reinicia e retoma o trabalho local. As etapas concluídas são mantidas. Uma etapa local interrompida pode ser executada novamente. Para atualizar manualmente, execute `sail upgrade` na máquina. O comando informa se instalou uma atualização, se a versão já era a atual ou se ocorreu um erro. Execute `sail --version` para conferir a versão instalada.

Se precisar restaurar o serviço, execute `sail login`. No mesmo endereço, ele reinstala e reinicia o serviço com as credenciais existentes. Se essas credenciais forem recusadas e a máquina ainda estiver cadastrada, o comando inicia um pareamento de reparo. O navegador mostra **Parear novamente uma máquina existente** e identifica a máquina que será substituída. Confira os detalhes e aprove o novo código. A máquina mantém suas equipes. Para a recuperação de senha, a data de pareamento passa a contar do recebimento das novas credenciais.

## Desative ou desinstale uma máquina

Para parar de usar uma máquina em toda a conta, abra o menu da linha da máquina em **Máquinas**, selecione **Excluir** e confirme. As credenciais da máquina são revogadas. Ela sai de suas equipes e para de trabalhar ao receber o aviso, imediatamente se estiver conectada ou na próxima conexão. As cópias de trabalho locais são mantidas. Para voltar a usá-la, execute `sail login` nela, aprove o novo pareamento e adicione-a às equipes que precisam dela.

Para remover a instalação do computador, salve primeiro o trabalho que precisa manter das cópias de trabalho do SailorBridge. Execute `sail uninstall` nessa máquina. O comando para o serviço e remove `sail`, a definição do serviço, a entrada de caminho no shell criada pelo instalador e todo o diretório `~/.sailorbridge/`. Isso inclui credenciais, cadastros de contas, logs, registros de conversas locais, cópias de trabalho e a cópia de segurança de `sail`. Seus diretórios de projeto e de login do motor são mantidos. Para instalar novamente, use o comando em **Parear nova máquina**.

## Se algo der errado

- Se o pareamento indicar que o Git não está instalado, instale o Git e execute `sail login` para continuar. Você pode resolver um login de motor ausente separadamente com `claude login` ou `codex login` antes de iniciar uma conversa ou tarefa.
- Se o código expirar, execute `sail login` para gerar outro. Se o nome da máquina ou o **Código da chave** for diferente, selecione **Cancelar pareamento** e confira o terminal na máquina certa. Se o pareamento foi aprovado mas a máquina não se conectou em 10 minutos, execute `sail host status` e depois `sail login` para se reconectar.
- Se uma máquina ficar off-line inesperadamente, confira a rede e o serviço com `sail host status`. O prazo padrão para considerar a máquina off-line é de 90 segundos. A notificação aparece somente depois de 10 minutos off-line e desaparece quando a máquina volta.
- Se uma atualização falhar, abra a máquina para ler o motivo e execute o comando de reparo exibido como o usuário que instalou `sail`. Se a cópia de segurança local não puder ser usada, use o comando de instalação da página de pareamento.
- Se a máquina informar que a identidade do servidor mudou, ela recusa a conexão. Use `sail host status --trust` para consultar a impressão digital salva na máquina. Se a mudança de identidade era esperada, execute `sail login`, confira a nova impressão digital no terminal e aprove um novo pareamento.
- Se `sail login` informar `origin_mismatch`, siga o procedimento de desinstalação acima antes de trocar de endereço. Depois, copie o comando de instalação da página **Máquinas** do aplicativo que você quer usar. Credenciais locais de pareamento ilegíveis também exigem desinstalação e novo pareamento.
- Se `sail uninstall` informar que o serviço não conseguiu confirmar a desativação, os arquivos locais já foram removidos. Abra **Máquinas** e desative a máquina na lista.
