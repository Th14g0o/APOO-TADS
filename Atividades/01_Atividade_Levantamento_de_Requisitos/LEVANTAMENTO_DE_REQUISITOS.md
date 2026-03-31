# Levantamento de Requisitos - Projeto Casa Segura

## Regras de Negócio

Código    | Regra |
| :------ | :-------- |
| RN01 | Situações críticas devem gerar notificação imediata ao proprietário ou vigilância
| RN02 | Controle por PCs, tablets e/ou smartphones do usuário 
| RN04 | Contato automático com órgãos de vigilância ao detectar situação crítica
| RN05 | Menos de um segundo para ativação dos sensores
| RN06 | Sistema totalmente seguro e criptografado
| RN07 | Em dispositivos móveis se exige otimização para manter o poder computacional e conservar a vida útil da bateria
| RN08 | Níveis de permissão para membros da família
| RN09 | Sensores funcionam ininterruptamente
| RN10 | Os eventos detectados devem seguir uma ordem de priorização
| RN11 | O sistema deve comutar automaticamente para bateria reserva em caso de queda de energia
| RN12 | Acesso via internet deve exigir autenticação em duas etapas (duas senhas)
| RN13 | O sistema deve reconhecer a identidade do usuário pelo celular e ajustar permissões conforme quem está presente
|RN14|Filhos/adolescentes não podem alterar configurações críticas como senha do alarme central



## Requisitos Funcionais

Codigo | Nome | Descrição | Categoria | Prioridade |
:----- | :--- | :-------- | :-------- | :--------- |
|RF01|Monitorar sensores de invasão|Permitir que o usuário monitore sensores de invasão|Funcionais||
|RF02|Monitorar sensores de incêndio|Permitir que o usuário monitore sensores de incêndio|Funcionais||
|RF03|Monitorar sensores de inundação|Permitir que o usuário monitore sensores de inundação|Funcionais||
|RF04|Monitorar sensores de níveis de monóxido de carbono|Permitir que o usuário monitore sensores de níveis de monóxido de carbono|Funcionais||
|RF05|Verificar o estado do alarme|O usuário pode verificar o estado do alarme|Funcionais||
|RF06|Armar ou desarmar o sistema|O usuário pode armar ou desarmar o sistema|Funcionais||
|RF07|Reconfigurar zonas de segurança|o usuário pode reconfigurar zonas de segurança|Facilidade e Suporte||
|RF08|Visualizar imagens de câmeras instaladas na casa | "Miniaturas" de todas as câmeras simultaneamente e escolher uma para ampliar, controlando remotamente o deslocamento e a aproximação da lente (pan e zoom) através do navegador|Funcionais||
|RF09|Controle de dispositivos eletrônicos, como luzes e eletrodomésticos|O usuário deve ser capaz de ajustar a temperatura do ar-condicionado enquanto volta para casa ou programar o sistema para acender e apagar luzes em intervalos aleatórios durante uma viagem para simular presença humana|Funcionais||
|RF10|Montar a planta da casa|O usuário pode montar sua planta com base em seção de objetos e redimensionamento dele|Funcionais|| 
|RF11| Abertura automática de portão | O sistema deve detectar a aproximação do proprietário via GPS e abrir o portão automaticamente
|RF12|Desarmamento automático por proximidade|O sistema deve desarmar o alarme automaticamente ao detectar a chegada do proprietário
|RF13|Recuperação de senha| O sistema deve oferecer um fluxo de recuperação de senha para autenticação em duas etapas


## Requisitos Não Funcionais

Codigo   | Nome | Descrição | Categoria | Classificação | Permanência |
:------  | :--- | :-------- | :-------- | :--------     | :---------- |
|RNF01|Protocolo 802.11n|Utilizar protocolo 802.11n para comunicação de hardware|Implementação|||
|RNF02|Acesso via Internet| O Usuario deve conseguir acessar o sistema pela sua casa|Funcionais|||
|RNF03|Alerta imediato contra invasões|O sistema deve ser capaz de contatar automaticamente um órgão de vigilância ou o telefone celular do proprietário quando uma situação crítica for detectada|Confiabilidade|||
|RNF04|Criptografia|site totalmente seguro e criptografado, garantir que o sistema seja invulnerável a intrusos que tentem desarmá-lo via Internet|Implementação|||
|RNF05|Responsivo|O site pode ser acessado pelo celular|Funcionais|||
|RNF06|Ativação de sensor|ativação de um sensor deve ser reconhecida em menos de um segundo|Desempenho|||
|RNF07|Priorização de Eventos|O sistema deve implementar uma priorização para os eventos detectados|Facilidade e Suporte|||
|RNF08|Economia de Energia|Equilibrar o poder computacional com a vida útil da bateria, garantindo que o aplicativo seja eficiente em termos de energia|Implementação|||
|RNF09|Gerenciar membros da familila|Sistema suporte o acesso simultâneo de múltiplos membros da família, possivelmente com diferentes níveis de permissão (ex: nem todos podem reconfigurar o sistema).|Facilidade e Suporte||
|RNF10|Monitoramento ininterrupto|O sistema de monitoramento de sensores deve operar ininterruptamente|Funcionais||
|RNF11|Detecção de Falhas de comunicação|Falhas de comunicação devem ser detectadas e reportadas imediatamente|Confiabilidade||
|RNF12|Detecção de Perda de energia |Perda de energia devem ser detectadas e reportadas imediatamente|Confiabilidade||
|RNF13|Objetos de montagem| O sistema deve possuir uma interface com ícones representando paredes, janelas e portas seriam "esticados" e posicionados sobre uma grade. Sensores e câmeras seriam então arrastados e soltos sobre essa planta para definir sua localização física no ambiente. Vinod e Jamie, da equipe de engenharia, ressaltam que a interface precisa ser consistente e simples o suficiente para que o proprietário não precise ler extensos manuais para operá-la|Interface|||
| RNF14 | Interação remota | Deve permitir que o usuário acesse certas funcionalidades via remoto |
| RNF15 | Acessos simultâneos | Deve permitir que vários usuários da mesma família acessem o sistema simultaneamente |
| RNF16 | Níveis de permissão entre membros da família | Deve permitir que usuários realizem ou não ações no sistema, dependendo do seu nível de permissão |
| RNF17 | Autenticação em duas etapas | Deve exigir duas senhas ao tentar se conectar
