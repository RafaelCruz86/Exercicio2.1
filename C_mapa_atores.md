# Mapa de Atores — Balcão Virtual TRT18
## Service Blueprint com Camada de Governança

---

## Decisões Estruturais

| Dimensão | Decisão |
|---|---|
| Metodologia | Service blueprint (camadas de atores) |
| Fases da jornada | Pré-atendimento → Triagem via Celeste → Agendamento → Atendimento → Pós-atendimento → Encaminhamentos |
| Tracks de usuário | Track 1a (trabalhador sem advogado), Track 1b (empregador sem advogado), Track 2 (advogado/procurador), Track 3 (usuário excluído digital/PID), Track 4 (usuário surdo/Balcão Visual) |
| Celeste | Ator frontstage (não sistema de suporte) |
| Atores sistêmicos | Camada de governança dedicada abaixo dos sistemas de suporte |
| Formato | Híbrido: tabela por camada + anotações analíticas com hipóteses de fricção |

---

## Camada 0 — Evidência Física
*O que o usuário vê, toca ou recebe em cada fase.*

| Fase | Evidência |
|---|---|
| Pré-atendimento | Portal trt18.jus.br; resultados de busca; cartazes nos PIDs |
| Triagem via Celeste | Interface WhatsApp; mensagens e menus da Celeste |
| Agendamento | Mensagem de confirmação via WhatsApp ou e-mail; link da sala Zoom |
| Atendimento | Sala Zoom (interface visual); indicador de fila ou ausência dele |
| Pós-atendimento | Mensagem de encerramento via WhatsApp ou e-mail; orientações escritas |
| Encaminhamentos | Interface PJe/eProc; formulários de atermação verbal; e-mail sgj@trt18.jus.br |

---

## Camada 1 — Ações dos Usuários
*Cinco tracks paralelos. Linha de Interação separa esta camada do frontstage.*

### Track 1a — Trabalhador sem advogado (reclamante, jus postulandi)

| Fase | Ação |
|---|---|
| Pré-atendimento | Pesquisa o serviço por indicação ou busca; acessa portal; pode não identificar o canal correto |
| Triagem via Celeste | Inicia conversa no WhatsApp (62 3222-5000); navega menus; risco de loops se a demanda não se encaixa nas opções disponíveis |
| Agendamento | Recebe confirmação de data/hora e link Zoom via Celeste |
| Atendimento | Acessa sala Zoom; aguarda na fila sem feedback de tempo estimado; é atendido pelo servidor |
| Pós-atendimento | Recebe orientações por WhatsApp ou e-mail; pode não ter suporte para interpretar os encaminhamentos |
| Encaminhamentos | É direcionado para atermação verbal (WhatsApp 62 3222-5570) se precisar formalizar demanda sem advogado |

### Track 1b — Empregador sem advogado (reclamado, jus postulandi)
*Jornada técnica idêntica ao Track 1a. Diferenças: papel processual oposto (defesa, não demanda); pode ter maior capacidade financeira mas mesma limitação de letramento digital; encaminhamentos focam em apresentação de defesa e documentação.*

### Track 2 — Advogado / procurador

| Fase | Ação |
|---|---|
| Pré-atendimento | Acessa portal diretamente; familiaridade alta com o serviço |
| Triagem via Celeste | Navega menus eficientemente; menor risco de loops; pode preferir contato direto |
| Agendamento | Agenda e integra ao calendário do escritório; pode usar múltiplos canais |
| Atendimento | Consulta técnica e processual via Zoom; interação mais diretiva com o servidor |
| Pós-atendimento | Integra informações recebidas ao workflow do escritório e ao PJe |
| Encaminhamentos | Peticiona diretamente no PJe/eProc; menor dependência do servidor para encaminhamentos |

### Track 3 — Usuário excluído digital (acesso via PID)

| Fase | Ação |
|---|---|
| Pré-atendimento | Desloca-se fisicamente ao Ponto de Inclusão Digital (PID); agendamento prévio com SGJ via e-mail sgj@trt18.jus.br ou telefone |
| Triagem via Celeste | Mediada integralmente pelo servidor do PID |
| Agendamento | Executado pelo servidor do PID em nome do usuário |
| Atendimento | Acessa sala Zoom via computador do PID; auxiliado pelo servidor do PID durante toda a sessão |
| Pós-atendimento | Recebe orientações presencialmente via servidor do PID |
| Encaminhamentos | Servidor do PID auxilia na compreensão e execução dos próximos passos |

### Track 4 — Usuário surdo / Balcão Visual

| Fase | Ação |
|---|---|
| Pré-atendimento | Acessa portal; verifica disponibilidade do Balcão Visual (horário: 12h–16h); pode encontrar barreira na ausência de conteúdo em Libras no portal |
| Triagem via Celeste | Canal de texto pode apresentar barreira linguística para usuários cuja primeira língua é a Libras |
| Agendamento | Agenda atendimento com intérprete de Libras disponível |
| Atendimento | Sessão Zoom com intérprete de Libras mediando a comunicação com o servidor |
| Pós-atendimento | Encaminhamentos recebidos via intérprete; risco de perda de informação na interpretação escrita |
| Encaminhamentos | Mediados pelo intérprete; dependência estrutural do serviço de interpretação |

---

**— LINHA DE INTERAÇÃO —**
*Separa as ações dos usuários do frontstage visível.*

---

## Camada 2 — Frontstage
*Atores visíveis ao usuário durante a jornada.*

| Ator | Fases ativas | Tracks atendidos |
|---|---|---|
| **Celeste** (chatbot WhatsApp) | Triagem via Celeste, Agendamento | 1a, 1b, 2 (Track 3 mediado; Track 4 com barreira) |
| **Servidor do balcão** (Zoom) | Atendimento, Pós-atendimento | Todos |
| **Intérprete de Libras** | Atendimento, Pós-atendimento | Track 4 exclusivamente |
| **Servidor do PID** | Todas as fases | Track 3 exclusivamente |
| **Servidor de atermação verbal** | Encaminhamentos | Tracks 1a, 1b, 3 |

### Anotações analíticas — Frontstage

**Hipótese da Rigidez Algorítmica (Celeste):** A Celeste opera como URA conversacional. A hipótese é que demandas fora dos fluxos pré-definidos levem o usuário a loops sem saída, gerando abandono ou escalada hostil. Camada de validação necessária: análise dos logs da Celeste no TRT18. Impacto concentrado nos Tracks 1a, 1b e 3 (menor letramento digital).

**Hipótese do Atrito no Handoff WhatsApp→Zoom:** A transição do canal assíncrono (texto, Celeste) para o síncrono (vídeo, Zoom) representa uma descontinuidade de modalidade. O usuário que termina o fluxo da Celeste precisa abrir um novo aplicativo, acessar um link e entrar em uma sala — sem confirmação de que o atendimento será imediato. Camada de validação: taxa de abandono entre confirmação de agendamento e entrada efetiva na sala Zoom.

**Hipótese da Opacidade da Fila:** O usuário dentro da sala Zoom não recebe feedback sobre posição na fila nem tempo estimado de espera. A hipótese é que essa opacidade gere ansiedade e hostilidade direcionada ao servidor quando o atendimento finalmente ocorre. Camada de validação: dados de ouvidoria e registros de interações adversas do DataJud.

---

**— LINHA DE VISIBILIDADE —**
*Separa o frontstage (visível ao usuário) do backstage (invisível).*

---

## Camada 3 — Backstage
*Atores internos que sustentam o frontstage sem interagir diretamente com o usuário.*

| Ator | Papel na jornada | Fases de maior influência |
|---|---|---|
| **Gestores das varas e secretarias** | Organizam escalas de atendimento; definem protocolos operacionais; gerenciam a distribuição de servidores entre balcão e atividades cartoriais | Pré-atendimento, Atendimento |
| **Equipe de TI e infraestrutura** | Mantém a Celeste, a integração WhatsApp–Zoom e o acesso ao PJe; suporte técnico em tempo real durante atendimentos | Todas as fases |
| **Equipe de comunicação e ouvidoria** | Gerencia reclamações; monitora qualidade do serviço; alimenta o DataJud com categorizações qualitativas | Pós-atendimento, Encaminhamentos |
| **Magistrados** | Definem o escopo informacional dos servidores (o que pode e não pode ser informado no balcão); impacto indireto mas estrutural na qualidade das respostas | Atendimento |
| **Presidência e Corregedoria** | Governança interna; compliance; aprovação de mudanças de protocolo | Transversal |

### Anotações analíticas — Backstage

**Burocracia de Nível de Rua (Lipsky, 1980):** Os servidores do balcão exercem vasta discricionariedade individual sob supervisão remota e escassa. O backstage (gestores e magistrados) define o protocolo, mas o servidor decide, em tempo real e sozinho, como enquadrar cada demanda. Esse gap entre protocolo e execução é a zona de risco para inconsistência no atendimento.

**Fadiga do Zoom (Bailenson, 2021):** Servidores em regime de teletrabalho (até 30% da unidade, per CNJ) enfrentam acúmulo de atos cartorários + atendimento via Zoom sem separação física. O backstage não tem visibilidade sobre essa carga cognitiva em tempo real. Indicador recomendado: escala ZEF (Zoom Exhaustion & Fatigue) aplicada periodicamente pelos gestores.

---

**— LINHA DE INTERAÇÃO INTERNA —**
*Separa o backstage dos sistemas de suporte.*

---

## Camada 4 — Sistemas de Suporte
*Infraestrutura tecnológica que sustenta todas as camadas acima.*

| Sistema | Função na jornada | Fases críticas |
|---|---|---|
| **PJe / eProc** | Sistema processual central; servidor consulta durante o atendimento; usuário letrado peticiona diretamente | Atendimento, Encaminhamentos |
| **Zoom** | Plataforma de videoconferência para o atendimento síncrono; migração obrigatória do Google Meet por orientação do CSJT | Atendimento |
| **Motor Celeste** | Engine do chatbot; gera logs de interação; integrado ao WhatsApp Business API | Triagem via Celeste, Agendamento |
| **DataJud** | Coleta metadados críticos: tempo de espera, tempo de atendimento, taxa de abandono, categorização da demanda; base para auditoria CNJ | Transversal |
| **Sistema de agendamento** | Gestão de slots de atendimento por vara; integrado à Celeste | Agendamento |

---

**— CAMADA DE GOVERNANÇA —**
*Atores regulatórios e sistêmicos que constrangem o redesenho sem participar da entrega direta.*

---

## Camada 5 — Governança e Regulação

| Ator | Papel regulatório | Resoluções / instrumentos | Implicação para o redesenho |
|---|---|---|---|
| **CNJ** | Obrigatoriedade do Balcão Virtual; métricas de auditoria; políticas de inclusão digital | Res. 372/2021 (BV obrigatório), Res. 345/2020 (Juízo 100% Digital), Res. 385/2021 (Justiça 4.0), Res. 508/2023 (PIDs), Rec. 101/2021 (excluídos digitais), Res. 473/2022 (extensão aos conselhos) | Qualquer mudança de plataforma ou protocolo requer alinhamento com as métricas CNJ/DataJud |
| **CSJT** | Governança da Justiça do Trabalho; TI e segurança da informação; orientou migração Google Meet → Zoom | Res. CSJT 425/2025 (PGTIC-JT: segurança, arquitetura, produtos digitais); horário do BV CSJT: 12h–18h | Mudanças de plataforma tecnológica passam pelo CSJT; novos sistemas devem seguir a PGTIC-JT |
| **ANPD** | Conformidade LGPD para dados pessoais processados nos atendimentos | Lei 13.709/2018 (LGPD) | Logs da Celeste e metadados do DataJud envolvem dados de partes processuais; qualquer expansão de funcionalidades (ex: IA generativa na triagem) requer parecer de conformidade |
| **Provedores de tecnologia** | Zoom Inc. (uptime, privacidade, funcionalidades); operadoras de telecomunicações (conectividade nos PIDs) | Contratos de serviço; SLA | Disponibilidade do serviço depende de SLAs com fornecedores privados; risco de concentração em fornecedor único |

---

## Síntese: Pontos Críticos de Redesenho por Camada

| Camada | Ponto crítico | Hipótese associada | Dado necessário para validar |
|---|---|---|---|
| Frontstage — Celeste | Loops algorítmicos na triagem | Rigidez Algorítmica | Logs da Celeste (taxa de abandono por fluxo) |
| Frontstage — Celeste→Zoom | Descontinuidade de modalidade | Atrito no Handoff | Taxa de não-comparecimento após agendamento confirmado |
| Evidência física — Atendimento | Ausência de feedback de fila | Opacidade da Fila e Hostilidade | Registros de ouvidoria; DataJud (tempo médio de espera vs. avaliação do atendimento) |
| Backstage — Servidores | Carga cognitiva invisível ao gestor | Fadiga do Zoom + Street-Level Bureaucracy | Escala ZEF aplicada nos servidores do balcão |
| Track 4 — Balcão Visual | Horário restrito (12h–16h) e dependência de intérprete externo | Fragilidade estrutural do serviço para surdos | Demanda reprimida fora do horário; cobertura de intérpretes disponíveis |
| Track 3 — PIDs | Agendamento com SGJ como barreira de acesso | Fricção de acesso para excluídos digitais | Tempo médio entre contato inicial e efetivo uso do PID |
| Governança — ANPD | Expansão de IA na Celeste sem conformidade LGPD | Risco regulatório latente | Parecer jurídico sobre o tratamento atual dos logs |
