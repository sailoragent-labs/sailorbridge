[← SailorBridge](README.md)

# Contas de motor e ritmo de trabalho

Seus agents usam contas de motor com sessão iniciada nas suas máquinas. Você pode ver quais contas uma equipe pode usar, quanta cota resta e quando o trabalho vai continuar. O plano do SailorBridge define quantos agents podem rodar ao mesmo tempo. O acesso aos modelos e a cota vêm do provedor do motor.

## Encontre ou adicione uma conta

1. Entre no Claude Code ou no Codex na máquina em que você quer usar o motor. Execute `sail account list`. O login padrão é detectado automaticamente. Em geral, o nome é o do motor seguido de `@` e do nome da máquina.
2. Para adicionar outro login, entre no motor usando um diretório de conta separado. Execute `sail account add <name> <directory>` com esse diretório e um nome de 1–64 caracteres, único na máquina, sem espaços nem barras. Por exemplo, se seu segundo login estiver nesse diretório, execute `sail account add work "$HOME/codex-work"`. A próxima leitura de cota detecta a conta sem precisar reiniciar.
3. Abra **Recursos** e depois **Contas**. Selecione a conta para ver suas máquinas, a cota e os modelos disponíveis. Contas informadas com o mesmo nome pelo mesmo motor em máquinas diferentes aparecem em uma única linha. O diretório de login, o e-mail e as credenciais ficam na máquina.

O Codex aceita login por assinatura. O Claude Code aceita login por assinatura ou chave de API. Gemini CLI, Copilot CLI, OpenCode, Qwen Code e Pi oferecem apenas cadastro de contas e verificações locais. Desses cinco, Gemini CLI e OpenCode reconhecem diretórios separados com nomes próprios.

## Use um endpoint compatível com Claude

Para um provedor como DeepSeek ou GLM, configure um diretório separado para a conta do Claude Code na sua máquina. No `settings.json` desse diretório, informe a URL base do provedor em `env.ANTHROPIC_BASE_URL` e a credencial em `env.ANTHROPIC_API_KEY` ou `env.ANTHROPIC_AUTH_TOKEN`. No mesmo objeto `env`, defina `ANTHROPIC_MODEL` com o nome do modelo do provedor. Você pode mapear separadamente as famílias Opus, Sonnet e Haiku com `ANTHROPIC_DEFAULT_OPUS_MODEL`, `ANTHROPIC_DEFAULT_SONNET_MODEL` e `ANTHROPIC_DEFAULT_HAIKU_MODEL`.

Execute `sail account add <name> <directory>` com o nome e o caminho que você escolheu. A conta funciona por meio do Claude Code. Abra **Modelos disponíveis** para ver os nomes de modelo lidos no diretório. Os modelos do endpoint usam esses mapeamentos e não têm ajuste de esforço. Os detalhes da tarefa mostram o modelo que realmente foi usado.

## Configure uma conta GLM, DeepSeek ou Kimi usando um modelo

`sail account create` grava um arquivo local de configuração do Claude Code com o endpoint do provedor, sugestões de modelos para os níveis alto, médio e baixo, e um valor provisório para a chave. O comando não pede, lê nem envia sua chave e não cadastra a conta.

Para configurar o GLM, execute o comando a seguir na máquina em que quer usar a conta.

```sh
sail account create glm
```

O comando imprime três linhas. Aqui, `~` representa seu diretório pessoal.

```text
Modelos propostos (Opus/Fable, Sonnet, Haiku/subagente): glm-5.3, glm-5.2, glm-5.3-flash.
Há três IDs de modelo distintos. O modelo de Sonnet é a proposta para o nível intermediário.
Edite ~/.sailorbridge/account-templates/glm/settings.json, substitua o marcador pela sua chave de API e execute sail account add <name> ~/.sailorbridge/account-templates/glm.
```

O `settings.json` gerado contém este modelo.

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "REPLACE_WITH_YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "ANTHROPIC_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-5.3-flash",
    "ANTHROPIC_DEFAULT_FABLE_MODEL": "glm-5.3",
    "CLAUDE_CODE_SUBAGENT_MODEL": "glm-5.3-flash"
  }
}
```

Abra o arquivo em um editor de texto como `nano`.

```sh
nano ~/.sailorbridge/account-templates/glm/settings.json
```

Substitua `REPLACE_WITH_YOUR_API_KEY` pela sua chave do GLM, mantenha as aspas e salve o arquivo. Cadastre o diretório com um nome à sua escolha. Neste exemplo, o nome é `glm`. Ele deve ser único nesta máquina, ter 1–64 caracteres e não conter espaços em branco nem `/`.

```sh
sail account add glm ~/.sailorbridge/account-templates/glm
sail account list
```

Procure `glm` na lista do terminal. Quando a máquina informar a conta, abra **Recursos** e depois **Contas** no aplicativo. Selecione `glm` para ver os **Modelos disponíveis** da conta.

Para DeepSeek ou Kimi, comece com o comando do provedor. Abra o arquivo `settings.json` no caminho exibido e substitua o valor provisório pela sua chave do provedor. Use o comando `sail account add` exibido com o nome escolhido e confira com `sail account list`.

| Comando do modelo | Endpoint no arquivo | Modelos propostos na saída |
| --- | --- | --- |
| `sail account create deepseek` | `https://api.deepseek.com/anthropic` | O nível alto usa `deepseek-v4-pro`. Os níveis médio e baixo compartilham `deepseek-flash`. |
| `sail account create kimi` | `https://api.kimi.com/coding/` | Use uma chave do Kimi Coding Plan. Os três níveis usam `k3.1-pro[1m]`. |

MiniMax exige `--region international` ou `--region china`. GLM, DeepSeek e Kimi recusam `--region`.

## Consulte a cota e reserve uma parte para você

Abra a conta em **Contas**. Confira **Cota**, **Redefinição** e **Leitura** em conjunto. A leitura de uma assinatura pode mostrar uma janela de cinco horas, uma janela semanal ou uma cota semanal para um modelo específico. O Codex informa sua cota semanal padrão. Ler a cota não consome tokens do modelo. Se uma nova leitura falhar, a última leitura bem-sucedida pode continuar aparecendo por até uma hora, marcada como antiga. A ausência de leitura tem um motivo e ainda pode permitir que a conta receba trabalho.

- **Habilitada** controla novas atribuições para esta conta em todas as suas equipes. Ao desativar a opção, o trabalho em andamento pode terminar.
- **Limite de reserva** reserva uma porcentagem para seu uso. Defina um valor de 0% a 100% em incrementos de 5. Se, em uma janela de mais de um dia, restar apenas essa porcentagem ou menos, os trabalhadores e o **Líder** deixam de usar a conta. Janelas curtas usam toda a cota.
- Para uma conta medida por gastos, defina em **Limite mensal** o máximo que a máquina pode gastar em um mês civil. Isso se aplica ao DeepSeek, por exemplo. O GLM fornece sua própria leitura de cota. Ao atingir o limite, novos trabalhos aguardam até a meia-noite UTC do primeiro dia do mês seguinte, a menos que você aumente o limite. Uma etapa em andamento pode terminar acima dele. Se você cadastrar a mesma conta em várias máquinas, cada uma mede seus próprios gastos. Se aparecer **Custo indisponível**, a contagem de tokens é exibida e o limite não pode ser aplicado.
- **Créditos de Reset** aparecem quando o Claude ou o Codex os informa. Abra um crédito, confira o que ele redefine e quando expira, selecione **Resgatar** e confirme. A opção **Resgatar Reset** na lista de contas usa o crédito elegível que expira primeiro. A máquina onde está a conta realiza a redefinição. Confira o resultado antes de usar outro crédito.

## Escolha contas e modelos para uma equipe

Abra **Lista de contas** no menu da conversa da equipe. As contas nas máquinas da equipe são incluídas por padrão. Em **Função**, selecione **Ambos**, **Só escrever** ou **Só revisar** para controlar quais etapas dos trabalhadores podem usar uma conta. Use **Só líder** para reservá-la para a conversa desta equipe. Use **Remover da equipe** e **Adicionar conta à equipe** para alterar a disponibilidade da conta nesta equipe.

Em **Detalhes da equipe**, abra as configurações de despacho. Em **Modelo do Líder**, selecione uma conta habilitada em uma máquina da equipe, um dos modelos detectados e um nível de esforço, se disponível. Ao escolher a conta em outra máquina, o **Líder** passa para ela para a próxima mensagem. Se a conta escolhida não puder rodar, a resposta identifica o motor e o modelo usados como alternativa.

Para os trabalhadores, defina o modelo e o esforço preferidos para cada nível de dificuldade e motor nas configurações de modelos da equipe. As opções de escrita e revisão do fluxo selecionam o motor. Na revisão automática, o revisor evita a família de modelo usada de fato na escrita, quando possível. Se um fluxo solicitar um motor para o qual a equipe não tem conta nessa função, a tarefa pode usar a seleção automática nessa execução. Os detalhes da tarefa explicam a mudança.

Uma tarefa precisa de uma máquina capaz de executar todas as etapas. Nessa máquina, cada etapa usa uma conta habilitada e permitida para o motor e a função. Entre as contas elegíveis, a prioridade é um login que aguarda renovação. Em seguida vêm as contas cuja cota será renovada em até um dia, começando pela renovação mais próxima. Para renovações mais distantes, a seleção considera a cota utilizável, a capacidade do plano e o tempo até a renovação. Contas sem leitura ficam por último. Uma revisão incremental ou uma primeira revisão com até 120 linhas alteradas dá preferência a um plano menor com capacidade disponível.

## Defina o ritmo de novos trabalhos

Abra **Recursos** e depois **Modo de Ritmo**. A opção padrão, **Conforme a Cota**, distribui o trabalho pela janela da cota. Uma conta está adiantada quando a porcentagem usada supera a porcentagem do tempo decorrido em mais de 100/7 pontos percentuais (cerca de 14.3) e resta mais de um sétimo da janela. Se todas as contas elegíveis estiverem adiantadas, a máquina espera antes de pegar uma nova tarefa. Uma tarefa em andamento pode continuar. A conversa com o **Líder** também pode continuar.

Selecione **Sem Limite** para permitir que todas as equipes peguem novas tarefas sem esperar por esse limite de ritmo. As reservas da conta e o esgotamento das janelas continuam valendo. Se uma conta estiver selecionada para o **Líder** em qualquer equipe e restar menos de 10% em uma janela que abrange a conta inteira, os trabalhadores deixam a conta para as conversas. Você pode voltar a **Conforme a Cota** na mesma página.

## Se algo der errado

- Se o arquivo de modelo já existir, o comando não o sobrescreve e exibe o caminho. Edite esse arquivo e cadastre o diretório.
- Se o comando recusar um diretório, confira o caminho exibido. O diretório deve pertencer ao seu usuário e ter modo `0700` para que somente você possa acessá-lo. Depois de corrigir o proprietário e as permissões, execute novamente o comando do modelo.
- `sail uninstall` remove `~/.sailorbridge/`, incluindo esses arquivos de configuração. Mantenha também uma cópia da sua chave em outro lugar.
- Se o cadastro falhar, siga o comando de login que o terminal mostra para o diretório informado. O diretório deve identificar um único motor. Use `sail account list` para conferir o nome. Para remover um cadastro ou ignorar um login padrão, execute `sail account remove <name>`. As credenciais locais são mantidas. Para voltar a reconhecer um login padrão, execute `sail account restore claude` ou `sail account restore codex`, ou abra **Logins ignorados** na máquina e selecione **Restaurar**.
- Para **Sessão expirada**, entre novamente na máquina indicada. Para **Renovar sessão**, a máquina tenta renovar o login. Para **Rede indisponível**, confira a conexão da máquina. Se o provedor limitar a frequência de solicitações ou estiver indisponível, o sistema tenta novamente após uma espera. Se a conta mostrar **Modelos Ainda Não Lidos** no seletor de modelos, aguarde uma leitura ou escolha uma conta com um modelo detectado.
- Se uma equipe recusar a remoção da conta do **Líder**, primeiro selecione outra conta em **Modelo do Líder**. Se uma tarefa não tiver um escritor ou revisor, selecione **Ir para contas** nos detalhes e habilite a função que falta em uma máquina capaz de executar a tarefa inteira.
- Abra **Lista de tarefas** e leia **Por que não está em andamento**. A espera por ritmo mostra um horário estimado. Você pode esperar ou confirmar **Mudar para Sem Limite** para todas as equipes. Uma tarefa que esgotou suas contas utilizáveis espera na mesma máquina e verifica novamente no horário exibido. Entrar na conta ou recuperar cota permite que ela continue automaticamente.
