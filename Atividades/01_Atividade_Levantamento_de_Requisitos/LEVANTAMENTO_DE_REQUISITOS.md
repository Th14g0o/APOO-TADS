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
|RF01|Monitorar sensores de invasão|Permitir que o usuário monitore sensores de invasão|Evidente|Alta|
|RF02|Monitorar sensores de incêndio|Permitir que o usuário monitore sensores de incêndio|Evidente|Alta|
|RF03|Monitorar sensores de inundação|Permitir que o usuário monitore sensores de inundação|Evidente|Alta|
|RF04|Monitorar sensores de níveis de monóxido de carbono|Permitir que o usuário monitore sensores de níveis de monóxido de carbono|Evidente|Alta|
|RF05|Verificar o estado do alarme|O usuário pode verificar o estado do alarme|Evidente|Alta|
|RF06|Armar ou desarmar o sistema|O usuário pode armar ou desarmar o sistema|Evidente|Alta|
|RF07|Reconfigurar zonas de segurança|O usuário pode reconfigurar zonas de segurança|Evidente|Média|
|RF08|Visualizar imagens de câmeras instaladas na casa|Visualizar câmeras e controlar pan/zoom remotamente|Evidente|Alta|
|RF09|Controle de dispositivos eletrônicos|Controlar luzes, ar-condicionado e simular presença|Evidente|Média|
|RF10|Montar a planta da casa|Montar planta com objetos e sensores|Evidente|Média|
|RF11|Abertura automática de portão|Detectar aproximação via GPS e abrir portão automaticamente|Oculto|Média|
|RF12|Desarmamento automático por proximidade|Desarmar automaticamente ao detectar chegada do proprietário|Oculto|Alta|
|RF13|Recuperação de senha|Fluxo de recuperação de senha com autenticação em duas etapas|Evidente|Alta|

## Requisitos Não Funcionais

Codigo   | Nome | Descrição | Categoria | Classificação | Permanência |
:------  | :--- | :-------- | :-------- | :------------ | :---------- |
|RNF01|Protocolo 802.11n|Utilizar protocolo 802.11n para comunicação de hardware|Implementação|Obrigatório|Permanente|
|RNF02|Acesso via Internet|O usuário deve conseguir acessar o sistema pela sua casa|Interface|Obrigatório|Permanente|
|RNF03|Alerta imediato contra invasões|Contatar automaticamente órgão de vigilância ou usuário em situação crítica|Confiabilidade|Obrigatório|Permanente|
|RNF04|Criptografia|Sistema seguro e criptografado contra invasões via Internet|Segurança|Obrigatório|Permanente|
|RNF05|Responsivo|O site pode ser acessado pelo celular|Interface|Desejável|Permanente|
|RNF06|Ativação de sensor|Ativação de sensor deve ser reconhecida em menos de 1 segundo|Desempenho|Obrigatório|Permanente|
|RNF07|Priorização de Eventos|Sistema deve priorizar eventos detectados|Facilidade de Suporte|Desejável|Permanente|
|RNF08|Economia de Energia|Sistema deve ser eficiente no uso de energia|Eficiência|Desejável|Permanente|
|RNF09|Gerenciar membros da família|Suporte a múltiplos usuários com permissões diferentes|Facilidade de Suporte|Obrigatório|Permanente|
|RNF10|Monitoramento ininterrupto|Sistema deve operar continuamente|Confiabilidade|Obrigatório|Permanente|
|RNF11|Detecção de Falhas de comunicação|Falhas devem ser detectadas e reportadas imediatamente|Confiabilidade|Obrigatório|Permanente|
|RNF12|Detecção de Perda de energia|Perda de energia deve ser detectada e reportada|Confiabilidade|Obrigatório|Permanente|
|RNF13|Objetos de montagem|Interface simples para montagem da planta da casa|Usabilidade|Desejável|Permanente|
|RNF14|Interação remota|Permitir acesso remoto ao sistema|Interface|Obrigatório|Permanente|
|RNF15|Acessos simultâneos|Suporte a múltiplos acessos simultâneos|Desempenho|Obrigatório|Permanente|
|RNF16|Níveis de permissão|Controle de permissões entre usuários|Segurança|Obrigatório|Permanente|
|RNF17|Autenticação em duas etapas|Sistema deve exigir dupla autenticação|Segurança|Obrigatório|Permanente|