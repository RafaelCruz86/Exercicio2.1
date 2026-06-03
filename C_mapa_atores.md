# Mapa de Atores — Balcão Virtual TRT18
*Service Blueprint · Metodologia: camadas de atores com camada de governança*

---

## Diagrama de Ecossistema

```mermaid
graph TB
    classDef usuario    fill:#dbeafe,stroke:#2563eb,color:#1e3a8a
    classDef frontstage fill:#dcfce7,stroke:#16a34a,color:#14532d
    classDef backstage  fill:#fef9c3,stroke:#ca8a04,color:#713f12
    classDef sistema    fill:#f3e8ff,stroke:#9333ea,color:#3b0764
    classDef gov        fill:#fee2e2,stroke:#dc2626,color:#7f1d1d

    subgraph C1["Camada 1 - Usuarios"]
        T1A("Track 1a - Trabalhador s/ advogado"):::usuario
        T1B("Track 1b - Empregador s/ advogado"):::usuario
        T2("Track 2 - Advogado / Procurador"):::usuario
        T3("Track 3 - Usuario PID"):::usuario
        T4("Track 4 - Surdo / Balcao Visual"):::usuario
    end

    subgraph C2["Camada 2 - Frontstage"]
        CEL("Celeste - WhatsApp"):::frontstage
        SVR("Servidor Balcao - Zoom"):::frontstage
        INT("Interprete de Libras"):::frontstage
        SPID("Servidor do PID"):::frontstage
        ATER("Servidor de Atermacao"):::frontstage
    end

    subgraph C3["Camada 3 - Backstage"]
        GEST("Gestores das Varas"):::backstage
        TI("Equipe de TI"):::backstage
        OUV("Ouvidoria"):::backstage
        MAG("Magistrados"):::backstage
        CORR("Presidencia e Corregedoria"):::backstage
    end

    subgraph C4["Camada 4 - Sistemas de Suporte"]
        PJE("PJe / eProc"):::sistema
        ZOOMP("Zoom Platform"):::sistema
        CELM("Motor Celeste"):::sistema
        DJ("DataJud"):::sistema
    end

    subgraph C5["Camada 5 - Governanca"]
        CNJ("CNJ"):::gov
        TST("TST"):::gov
        CSJT("CSJT"):::gov
        ANPD("ANPD"):::gov
        PROV("Zoom Inc."):::gov
    end

    T1A -->|triagem| CEL
    T1B -->|triagem| CEL
    T2  -->|triagem| CEL
    T3  -->|mediado| SPID
    T4  -->|mediado| INT
    CEL -->|handoff| SVR
    SPID -->|acessa| SVR
    INT  -->|interpreta| SVR
    T1A -->|encaminha| ATER
    T1B -->|encaminha| ATER
    T3  -->|encaminha| ATER
    SVR -->|consulta| PJE

    GEST -->|protocolo| SVR
    MAG  -->|escopo| SVR
    TI   -->|mantem| CELM
    TI   -->|mantem| ZOOMP
    OUV  -->|monitora| DJ
    CORR -->|compliance| SVR

    CEL   -.-> CELM
    SVR   -.-> ZOOMP
    DJ    -.-> CNJ
    TI    -.-> CSJT
    CNJ   -.-> CSJT
    TST   -.-> CSJT
    CELM  -.-> ANPD
    DJ    -.-> ANPD
    ZOOMP -.-> PROV
```

> **Legenda de cores:**
> Azul — Usuários · Verde — Frontstage · Amarelo — Backstage · Roxo — Sistemas · Vermelho — Governança
>
> Setas sólidas = interações diretas na jornada · Setas tracejadas = dependências tecnológicas e regulatórias

---

## Fases da Jornada

| # | Fase | Descrição |
|---|---|---|
| 1 | **Pré-atendimento** | Descoberta do serviço; acesso ao portal trt18.jus.br; orientação inicial |
| 2 | **Triagem via Celeste** | Contato via WhatsApp (62 3222-5000); navegação nos menus do chatbot |
| 3 | **Agendamento** | Confirmação de data/hora e link Zoom via Celeste ou canal alternativo |
| 4 | **Atendimento** | Sessão síncrona via Zoom com servidor do balcão |
| 5 | **Pós-atendimento** | Encaminhamentos por WhatsApp ou e-mail; orientações escritas |
| 6 | **Encaminhamentos** | Ações derivadas: atermação verbal, peticionamento no PJe, acesso a PID |

---

## Tabela de Atores

| Ator | Camada | Tipo | Tracks | Fases ativas | Responsabilidade principal | Fricção / hipótese associada |
|---|---|---|---|---|---|---|
| Trabalhador sem advogado | ① Usuário | Externo | 1a | Todas | Obtém informações processuais sem representação legal | Letramento digital limitado; risco de loop na Celeste |
| Empregador sem advogado | ① Usuário | Externo | 1b | Todas | Defende-se ou busca informações sem advogado | Idem Track 1a; papel processual oposto |
| Advogado / Procurador | ① Usuário | Externo | 2 | Todas | Consulta técnica em nome de clientes; integra ao PJe | Menor fricção; pode preferir acesso direto ao PJe |
| Usuário excluído digital | ① Usuário | Externo | 3 | Todas (mediadas) | Acessa o serviço via PID com auxílio de servidor | Barreira de agendamento com SGJ (sgj@trt18.jus.br); dependência de deslocamento físico |
| Usuário surdo (Balcão Visual) | ① Usuário | Externo | 4 | Atend., Pós, Encam. | Atendimento mediado por intérprete de Libras | Horário restrito 12h–16h; barreira linguística na Celeste; dependência de intérprete |
| **Celeste** (chatbot WhatsApp) | ② Frontstage | Tecnológico | 1a, 1b, 2 | Triagem, Agend. | Triagem automatizada e agendamento via WhatsApp (62 3222-5000) | **H1 Rigidez Algorítmica** · **H3 Atrito no Handoff** |
| **Servidor do Balcão** | ② Frontstage | Interno | Todos | Atend., Pós | Atendimento síncrono via Zoom; consulta PJe; orienta encaminhamentos | **H2 Opacidade da Fila** · **H4 Fadiga do Zoom** (Bailenson, 2021) |
| **Intérprete de Libras** | ② Frontstage | Externo/Parceiro | 4 | Atend., Pós | Mediação linguística entre usuário surdo e servidor | Disponibilidade limitada; parceria TRT15 é estruturalmente frágil |
| **Servidor do PID** | ② Frontstage | Interno | 3 | Todas | Mediação completa da jornada do usuário excluído digital | Cobertura geográfica dos PIDs no interior de Goiás |
| **Servidor de Atermação** | ② Frontstage | Interno | 1a, 1b, 3 | Encam. | Formaliza demanda trabalhista verbal sem advogado (WhatsApp 62 3222-5570) | Fluxo de encaminhamento pós-balcão pouco sinalizado ao usuário |
| Gestores das Varas / Secretarias | ③ Backstage | Interno | — | Pré-atend., Atend. | Escalas de atendimento; protocolos operacionais | Sem visibilidade em tempo real sobre carga cognitiva dos servidores |
| Equipe de TI e Infraestrutura | ③ Backstage | Interno | — | Todas | Manutenção de Celeste, Zoom e PJe; suporte em tempo real | Ponto único de falha para todos os canais digitais simultâneos |
| Ouvidoria | ③ Backstage | Interno | — | Pós, Encam. | Gestão de reclamações; alimentação do DataJud | Canal de feedback subutilizado para validação empírica das hipóteses |
| Magistrados | ③ Backstage | Interno | — | Atend. | Definem o escopo informacional dos servidores do balcão | Restrição de informação pode escalar insatisfação do usuário |
| **Presidência e Corregedoria** | ③ Backstage | Interno | — | Transversal | Governança interna do TRT18; compliance; aprovação de mudanças de protocolo | Aprovações internas podem ser gargalo para implementar redesenhos |
| PJe / eProc | ④ Sistemas | Tecnológico | — | Atend., Encam. | Sistema processual central; consulta e peticionamento | Complexidade de interface para usuários sem letramento digital |
| Zoom Platform | ④ Sistemas | Tecnológico | — | Atend. | Plataforma de videoconferência para atendimento síncrono | Migração obrigatória do Google Meet por decisão CSJT |
| Motor Celeste + Logs | ④ Sistemas | Tecnológico | — | Triagem, Agend. | Engine do chatbot; gera logs para análise de qualidade | Logs necessários para validar **H1**; dados pessoais sob risco LGPD |
| DataJud | ④ Sistemas | Tecnológico | — | Transversal | Coleta metadados de atendimento para auditoria CNJ | Dado crítico para validação de todas as hipóteses de fricção |
| **CNJ** | ⑤ Governança | Regulatório | — | — | Obrigatoriedade e métricas do Balcão Virtual; auditorias via DataJud | Redesenho deve alinhar indicadores às metas CNJ (Res. 372/2021) |
| **TST** | ⑤ Governança | Regulatório | — | — | Instância superior da Justiça do Trabalho; emite normas que vinculam todos os TRTs via CSJT | Decisões sobre digitalização no TST têm efeito cascata imediato no TRT18 |
| **CSJT** | ⑤ Governança | Regulatório | — | — | Governa TI da Justiça do Trabalho; mandatou migração para Zoom | Mudanças de plataforma requerem aprovação via PGTIC-JT (Res. CSJT 425/2025) |
| **ANPD** | ⑤ Governança | Regulatório | — | — | Conformidade LGPD para dados dos atendimentos | Expansão de IA na Celeste requer parecer de conformidade prévia |
| **Zoom Inc.** | ⑤ Governança | Fornecedor | — | — | Fornecedor da plataforma de videoconferência | Dependência de fornecedor privado único; risco de variação de SLA |

---

## Hipóteses de Fricção Mapeadas

| ID | Hipótese | Camada | Ator principal | Dado para validar |
|---|---|---|---|---|
| H1 | Rigidez Algorítmica (URA vs. fluidez) | ② Frontstage | Celeste | Logs da Celeste: taxa de abandono por fluxo |
| H2 | Opacidade da Fila e Hostilidade | ② Frontstage | Servidor do Balcão | DataJud: tempo de espera vs. avaliação do atendimento; registros de ouvidoria |
| H3 | Atrito no Handoff WhatsApp → Zoom | ② Frontstage | Celeste → Servidor | Taxa de não-comparecimento após agendamento confirmado |
| H4 | Fadiga do Zoom (Bailenson, 2021) | ③ Backstage | Servidor do Balcão | Escala ZEF aplicada periodicamente; correlação com qualidade do atendimento |
| H5 | Barreira de acesso ao PID | ① Usuário / ② Frontstage | Usuário excluído digital / Servidor PID | Tempo entre contato inicial e uso efetivo do PID |
| H6 | Fragilidade estrutural do Balcão Visual | ① Usuário / ② Frontstage | Usuário surdo / Intérprete | Demanda reprimida fora do horário 12h–16h; cobertura de intérpretes |
