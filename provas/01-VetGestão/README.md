# Enunciado Para CDU:
A Clínica Veterinária e Pet Shop "Animed" contratou sua equipe para desenvolver um novo sistema de gerenciamento chamado VetGestão. Após algumas reuniões de levantamento de requisitos com os proprietários e funcionários da clínica, o analista de sistemas documentou a seguinte narrativa sobre o funcionamento desejado do software:

"O VetGestão será o sistema central da clínica. O Recepcionista utilizará o sistema para cadastrar novos clientes e seus respectivos pets. Ele também é o responsável por realizar o agendamento de consultas clínicas e de serviços de banho e tosa. Sempre que o Recepcionista iniciar um agendamento, o sistema deve, de forma automática e obrigatória, verificar a situação cadastral do cliente.

Durante o agendamento de serviços estéticos (banho e tosa), caso o cliente faça parte do programa de fidelidade da clínica, o sistema deve permitir que o recepcionista, opcionalmente, aplique um desconto de assinante.

O Veterinário acessa o sistema exclusivamente para consultar a agenda do dia e registrar o prontuário médico do animal após o atendimento.

No momento do acerto de contas, o Recepcionista realiza o fechamento da fatura e o sistema processa o pagamento. Para pagamentos via cartão de crédito ou PIX, o VetGestão precisa se comunicar em tempo real com o Gateway PagueCerto (um sistema externo).

A gerência estipulou algumas políticas estritas: o sistema deve bloquear o agendamento de qualquer serviço estético ou clínico se a carteira de vacinação do animal não constar como atualizada no sistema. Além disso, clientes que possuam boletos em aberto há mais de 30 dias estão impedidos de agendar novos serviços até a quitação da dívida.

Por fim, a administração exige que o sistema possua uma interface web responsiva. Para garantir a agilidade no balcão, o tempo de resposta na busca de prontuários não pode ultrapassar 2 segundos. Devido ao manuseio de dados pessoais dos clientes, todo o banco de dados deve possuir criptografia de ponta a ponta para estar em estrita conformidade com a LGPD (Lei Geral de Proteção de Dados)."

# Detalhamento para Classe de Dominio:
**CDU05 - Registrar Atendimento Clínico**

**Ator Principal**: Veterinário

**Pré-condição**: O Veterinário deve estar autenticado no sistema e o paciente (pet) deve possuir um agendamento prévio para o dia atual.

**Fluxo Principal (Narrativa)**:
1. O Veterinário acessa a agenda do dia e seleciona um Agendamento. O sistema sabe que o veterinário possui um nome, um telefone e um número de registro no CRMV (Conselho Regional de Medicina Veterinária).
2. Ao abrir o agendamento, o sistema exibe os dados do Paciente (Pet). O sistema armazena do paciente o seu nome, espécie (ex: canina, felina), raça, data de nascimento e peso atual.
3. Para fins de contato, o sistema também exibe os dados do Tutor (Cliente) responsável por aquele paciente, contendo nome completo, CPF e telefone. Um tutor pode ter vários pets cadastrados, mas um pet pertence a apenas um tutor.
4. O Veterinário inicia o atendimento criando um novo Prontuário. O prontuário registra a data da consulta, o horário, a queixa principal relatada pelo tutor e as observações clínicas gerais feitas pelo médico. Todo prontuário está obrigatoriamente vinculado ao paciente atendido e ao veterinário responsável.
5. Durante o preenchimento, o Veterinário pode registrar um ou mais Diagnósticos no prontuário. Cada diagnóstico possui um código da doença e uma descrição detalhada.
6. Caso seja necessário medicar o animal em casa, o Veterinário pode gerar uma Receita Médica vinculada àquele prontuário (um prontuário pode ter no máximo uma receita gerada, ou nenhuma).
7. Na Receita Médica, o Veterinário adiciona os Itens Prescritos. Cada item prescrito refere-se a um medicamento e deve conter o nome do remédio, a dosagem (ex: 20mg) e a frequência de uso (ex: de 8 em 8 horas). Uma receita deve conter, no mínimo, um item prescrito.
8. O sistema salva o prontuário e encerra o atendimento, alterando o status do agendamento para "Concluído".