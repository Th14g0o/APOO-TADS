# Sistema de Gestão de Condomínios "CondoFácil"

## Casos de Usos

**Contexto**:A empresa de tecnologia SmartLiving foi contratada para desenvolver o "CondoFácil", um aplicativo voltado para a administração de condomínios residenciais. O analista de requisitos fez o levantamento com o cliente e documentou as seguintes necessidades de interação com o sistema:

**Requisitos e Funcionalidades:**

- Acesso ao Sistema:
- Para acessar qualquer funcionalidade interna do sistema (reservas, pagamentos, emissão de avisos), é estritamente necessário que o usuário realize a Autenticação (Login).

**Ações do Morador:**

- O Morador utiliza o aplicativo para Reservar Áreas Comuns (como churrasqueira ou salão de festas).
- Sempre que uma reserva de área comum for efetuada, o sistema deve obrigatoriamente Verificar a Disponibilidade da data no calendário central.
- O Morador também pode Pagar a Taxa de Condomínio diretamente pelo aplicativo. Para que o pagamento seja processado, o CondoFácil se comunica automaticamente com um Sistema Bancário Externo (API do Banco), que é responsável por validar e autorizar a transação.

**Ações do Síndico:**

- O Síndico é, antes de tudo, um morador do condomínio. Portanto, ele herda todas as permissões de um Morador comum no sistema.
- Além disso, o Síndico possui funções administrativas exclusivas: ele pode Emitir Comunicados Oficiais para o mural digital e Aplicar Multas aos moradores que descumprirem as regras.

**Ações do Porteiro:**

- O Porteiro utiliza o sistema em uma interface própria na guarita para Registrar a Entrada de Visitantes.
- Durante o registro de entrada, caso o visitante tente acessar o condomínio fora do horário comercial (após as 18h), o sistema permite que o porteiro, de forma opcional e dependendo da situação, acione a função de Notificar Morador por SMS para pedir uma autorização extra.

## Modelo Conceitual

Dando continuidade ao desenvolvimento do sistema "CondoFácil", a equipe de engenharia de software precisa agora compreender a estrutura de dados e as regras de negócio associadas ao sistema. Para isso, o analista de requisitos detalhou os fluxos de eventos dos seguintes casos de uso: Reservar Área Comum (CDU02) e Registrar Entrada de Visitante (CDU04).

**Detalhamento do Caso de Uso:** CDU02 - Reservar Área Comum

**Ator Principal:** Morador

**Pré-condição:** O Morador deve estar logado no sistema.

**Fluxo Principal (Narrativa):**

1. O Morador acessa o módulo de reservas e solicita a visualização das Áreas Comuns disponíveis no condomínio. Para facilitar a comunicação, o sistema sabe que cada morador possui um nome, CPF, telefone, número do apartamento e bloco em que reside.
2. O sistema lista as Áreas Comuns cadastradas. Cada área comum possui um nome (ex: Salão de Festas, Churrasqueira), uma capacidade máxima de pessoas, um horário de abertura, um horário de fechamento e o valor da taxa de uso.
3. O morador seleciona a Área Comum desejada e informa a data pretendida, bem como o horário de início e o horário de término do seu evento.
4. O sistema verifica a disponibilidade. Se o espaço estiver livre na data e horário solicitados, o sistema permite que o morador avance.
5. O morador pode, opcionalmente, cadastrar os Convidados que comparecerão ao evento, informando o nome completo e o documento de identidade (RG) de cada um deles. Uma reserva pode não ter convidados cadastrados inicialmente, mas a área comum não pode exceder sua capacidade máxima.
6. O sistema gera a Reserva, vinculando-a ao morador solicitante e à área comum escolhida. A reserva é registrada com a data da solicitação, a data do evento, os horários definidos e um status inicial definido como "Aguardando Pagamento".
7. O sistema calcula automaticamente o valor total com base na taxa de uso da área comum e o exibe para o morador confirmar a operação.

**Detalhamento do Caso de Uso: CDU04 - Registrar Entrada de Visitante**

**Ator Principal**: Porteiro

**Pré-condição**: O Porteiro deve estar logado no terminal da guarita.

**Fluxo Principal (Narrativa):**

1. O Porteiro recebe uma pessoa na portaria e solicita seus dados de identificação para acessar o módulo de Portaria. Para o sistema, o porteiro é um funcionário que possui um nome, matrícula e turno de trabalho.
2. O sistema busca na base de dados se a pessoa já possui cadastro como Visitante. Se não possuir, o Porteiro cadastra o Visitante informando o nome completo, CPF, telefone e, opcionalmente, capturando uma foto do rosto.
3. O Porteiro pergunta qual apartamento será visitado e seleciona o Morador anfitrião no sistema.
4. Após a confirmação da autorização (feita fora do sistema, por interfone), o Porteiro gera um Registro de Acesso.
5. O Registro de Acesso é salvo contendo a data e hora de entrada. Ele deve obrigatoriamente registrar qual Porteiro realizou o lançamento, qual Visitante está entrando e qual Morador autorizou a visita.
6. Quando o visitante deixa o condomínio, o Porteiro localiza o registro em aberto e o atualiza, inserindo a data e hora de saída.
