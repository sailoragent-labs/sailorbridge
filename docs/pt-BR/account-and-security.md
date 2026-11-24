[← SailorBridge](README.md)

# Conta e segurança

Seu **ID do capitão** numérico é o nome que você usa para entrar. Ele permanece associado à conta quando você muda de apelido, senha ou navegador. Pareie uma máquina que você controla enquanto ainda consegue entrar. Você precisará de uma máquina pareada se esquecer a senha.

## Crie sua conta

1. Abra o [aplicativo](https://app.sailorbridge.com) e selecione **Cadastrar**. Digite o número que você quer, de 3 a 11 dígitos. Se aparecer **Já reivindicado**, altere o número e consulte outro.
2. Confira o que a página mostra para esse número. IDs comuns de 6–8 dígitos e todos os IDs de 9–11 dígitos são grátis. IDs mais curtos e padrões especiais de até 8 dígitos têm uma cobrança única. Se o número for pago, salve o **Link de resgate** na página de pagamento para poder concluir o cadastro em outro dispositivo. [Preços](https://www.sailorbridge.com/#pricing)
3. Defina e confirme sua senha. Você pode escolher um avatar da galeria ou manter sua inicial. Confirme sua idade e aceite os **Termos de Serviço**. Depois, selecione **Cadastrar**. O aplicativo inicia sua sessão. [Pareie sua primeira máquina](machines.md)

## Entre e confirme um novo navegador

Selecione **Entrar** e preencha **ID do capitão** e **Senha**. Um novo navegador pede confirmação se você tem uma máquina pareada ou usa verificação em duas etapas. Com a verificação em duas etapas ativada, você precisa confirmar cada acesso, mesmo em um navegador conhecido.

Na tela **Confirme que é você**, use um dos métodos oferecidos.

- Para **Código do autenticador**, digite o código atual do seu aplicativo autenticador.
- Para **Código da máquina**, execute `sail confirm` no terminal de uma máquina pareada. Digite o código de oito caracteres na página de login.
- Se a página mostrar um número de dois dígitos, abra outro navegador em que você já tenha uma sessão iniciada. Confira se o **Código da chave** é igual nas duas telas e toque no número de dois dígitos da página de login. Se outra pessoa iniciou a solicitação, selecione **Não fui eu**.

## Configure seu perfil e proteja seu acesso

Abra **Eu**. Você pode definir um **Apelido** e escolher um **Avatar** da galeria. A opção **Idioma** define o idioma da interface e das respostas a partir do próximo turno de conversa ou da próxima tarefa. Em **Estilo de resposta**, selecione **Iniciante** para receber mais explicações ou **Especialista** para receber respostas mais curtas.

Abra **Segurança** e depois **Verificação em duas etapas**. Selecione **Ativar**, confirme sua senha e leia o código QR com seu aplicativo autenticador. Digite o código atual do aplicativo e selecione **Confirmar e ativar**. Para desativar o recurso, selecione **Desativar a verificação em duas etapas**, informe sua senha e digite um novo código.

Para alterar a senha, preencha **Senha atual**, **Nova senha** e **Confirme a nova senha** em **Segurança**. Digite um código do autenticador se a verificação em duas etapas estiver ativa. Depois da alteração, este navegador fica conectado e as outras sessões são encerradas.

## Confira a atividade e as chaves dos dispositivos

Abra **Eu**, depois **Segurança** e **Registros de segurança recentes**. A lista abrange os últimos 90 dias. Quando há um login bem-sucedido em um novo navegador, o aplicativo pergunta se foi você. Selecione **Fui eu** ou **Não fui eu**. Cada navegador registra suas próprias confirmações. Tentativas de login malsucedidas aparecem na lista sem pedido de confirmação.

Se vir um login que você não fez, altere a senha. A opção **Sair das outras sessões** encerra as sessões nos outros navegadores. Se precisar desconectar apenas uma máquina, desative-a em **Máquinas**. A opção **Revogar todas as máquinas** desconecta todas as máquinas pareadas. Você terá de parear cada uma novamente para que possa trabalhar ou fornecer um código de recuperação. Você também pode excluir um registro de segurança após confirmar. Os outros navegadores continuam recebendo seus próprios alertas até confirmar o evento.

Em **Segurança**, abra **Chaves** para ver os navegadores e as máquinas que assinam operações em seu nome. Para adicionar um navegador, abra **Aguardando entrada** em um navegador que já esteja na lista. Compare o código curto de 12 caracteres nos dois navegadores e selecione **Adicionar** somente se os códigos forem iguais. Use **Remover** para uma chave que você não usa mais ou **Marcar como roubada** para um dispositivo perdido. A remoção da chave de uma máquina desativa essa máquina. Se você iniciou uma redefinição da lista de chaves em uma máquina, só confirme no navegador depois de conferir o nome da máquina.

## Recupere uma senha esquecida

1. Em um terminal de uma máquina pareada, execute `sail recover`. O comando mostra seu ID do capitão e um código de recuperação de oito caracteres, de uso único e válido por 10 minutos. Gerar outro código na mesma máquina substitui o primeiro.
2. Na página de login, selecione **Esqueceu a senha?**. Digite o ID e o **Código de recuperação** exibidos no terminal. Confira o nome da máquina e a data de pareamento na página antes de digitar a nova senha.
3. Siga o procedimento de recuperação exibido. A idade do pareamento é contada desde o último pareamento ou reparo das credenciais.

| Máquina usada na recuperação | Verificação em duas etapas | O que acontece |
| --- | --- | --- |
| Pareada há menos de 72 horas | Qualquer configuração | Envie uma solicitação de recuperação de 72 horas, mesmo se você tiver um código do autenticador. |
| Pareada há pelo menos 72 horas | Desativada ou ativada há menos de 72 horas | Redefina a senha imediatamente com o código de recuperação. A recuperação desativa a verificação em duas etapas se ela tiver sido ativada recentemente. |
| Pareada há pelo menos 72 horas | Ativada há pelo menos 72 horas | Digite um código do autenticador para redefinir a senha imediatamente e manter a verificação em duas etapas. Sem esse código, envie uma solicitação de recuperação de 72 horas. |

Se precisar esperar, selecione **Solicitar recuperação com espera de 72 horas** e siga o prazo exibido na página de recuperação. Os dispositivos com sessão iniciada recebem uma notificação. Você pode selecionar **Cancelar esta recuperação** em um deles. Um login bem-sucedido também cancela a solicitação. Quando a redefinição entrar em vigor, entre com a nova senha. A recuperação com espera redefine a verificação em duas etapas.

Depois da recuperação, confira **Pareada em** em **Máquinas** e desative as máquinas que você não reconhecer. Você pode reativar a verificação em duas etapas em **Segurança**.

## Saia ou exclua sua conta

Use **Sair** em **Eu** para encerrar a sessão deste navegador. Para fechar a conta, selecione **Excluir conta**, confira as equipes e máquinas afetadas e confirme com sua senha e, se a verificação em duas etapas estiver ativa, com um código do autenticador. A exclusão encerra as sessões nos seus dispositivos, revoga suas máquinas e cancela sua assinatura. Entre novamente em até sete dias para desfazer a solicitação. A recuperação de senha fica indisponível durante esse período porque as máquinas foram revogadas. Após o prazo, a conta é excluída e seu número permanece desativado.

## Se algo der errado

- Após cinco tentativas de login malsucedidas em 15 minutos, o bloqueio padrão dura 15 minutos. Aguarde o tempo exibido. Cada código do autenticador pode ser usado uma vez. Se acabou de usá-lo, espere o próximo.
- Se a confirmação do navegador expirou ou você tocou no número errado, inicie o login novamente. Você também pode usar um dos métodos por código oferecidos. Execute `sail confirm` para obter um novo código de login e `sail recover` para obter um novo código de recuperação de senha.
- Se uma máquina não conseguir emitir um código de recuperação, tente outra máquina pareada com sua conta. Se nenhuma tiver credenciais válidas, a conta não poderá ser recuperada. Cadastre um novo ID.
