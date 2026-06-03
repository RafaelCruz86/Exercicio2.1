❯ Quero produzir um mapa de atores da jornada "Balcão Virtual TRT18". Considere como contexto o artefato @B_relatorio_assistente_v3.md. Siga a metodologia do service blueprint com camadas de atores.

Read B_relatorio_assistente_v3.md (139 lines)

O relatório confirma: jornada multi-canal (WhatsApp/Celeste → Zoom → PJe), 3 hipóteses de fricção explícitas (rigidez algorítmica, opacidade da fila, atrito no handoff), 4 perfis de usuário vulneráveis mencionados (trabalhador sem advogado, usuário excluído digital, surdo/Balcão Visual, empregador sem advogado). Governança em 3 camadas: CNJ/CSJT/TST + ANPD + Zoom Inc.

---

Q1/10: Qual metodologia deve estruturar o mapa de atores?

As opções principais são: (A) stakeholder map simples — lista atores por influência/interesse; (B) service blueprint com camadas — separa usuário / frontstage / backstage / sistemas; (C) ecosystem map — foco em dependências entre entidades sem ancorar na jornada.

Recommended answer: (B) Service blueprint com camadas. O relatório já diagnostica fricções em pontos específicos da jornada (handoff WhatsApp→Zoom, opacidade da fila no Zoom, rigidez da Celeste). O blueprint ancora cada hipótese na camada certa — se usarmos stakeholder map ou ecosystem map, essas fricções ficam flutuando sem posição diagnóstica.

✻ Worked for 12s

❯ b

Service blueprint confirmado.

---

Q2/10: Quantas fases da jornada devem compor o eixo horizontal do blueprint?

O relatório descreve um fluxo natural em 5 etapas: pré-atendimento → agendamento → atendimento → pós-atendimento → encaminhamentos. Mas as três hipóteses de fricção do relatório (H1 rigidez algorítmica, H3 atrito no handoff) se concentram num momento específico — o contato inicial via Celeste/WhatsApp — que hoje está colapsado dentro de "pré-atendimento".

Opções: (A) 5 fases como estão — pré-atendimento já implica o contato via Celeste; (B) 6 fases — desdobrar pré-atendimento em "pré-atendimento" + "triagem via Celeste", tornando H1 e H3 visíveis como coluna própria.

Recommended answer: (B) 6 fases. A Celeste é onde a maioria dos usuários tem o primeiro ponto de falha. Torná-la fase explícita no blueprint permite ancorar os atores Celeste e Servidor do Balcão nas colunas corretas — sem isso, o mapa não distingue onde começa o frontstage humano e onde termina o bot.

✻ Worked for 14s

❯ 6

6 fases confirmadas: pré-atendimento → triagem via Celeste → agendamento → atendimento → pós-atendimento → encaminhamentos.

---

Q3/10: A camada de usuários deve mostrar um perfil genérico ou tracks paralelos?

O relatório descreve perfis com jornadas estruturalmente distintas: trabalhador sem advogado (jus postulandi, letramento digital baixo), advogado/procurador (acesso técnico ao PJe, menor fricção), usuário excluído digital (acessa via PID, mediado por servidor), e usuário surdo (Balcão Visual, mediado por intérprete de Libras). O empregador sem advogado segue a mesma jornada técnica do trabalhador, mas com papel processual inverso.

Opções: (A) um "usuário genérico" único — mais limpo, mas achata as diferenças; (B) 3 tracks — trabalhador, advogado, excluído digital; (C) 4 tracks — os 3 anteriores + Balcão Visual como track próprio, com o empregador como variante do track do trabalhador.

Recommended answer: (C) 4 tracks. O Balcão Visual tem um ator exclusivo no frontstage (intérprete de Libras) que nenhum outro track tem — sem track próprio, esse ator fica solto sem jornada de usuário que o justifique. O empregador sem advogado tem a mesma infraestrutura de atendimento do trabalhador, então fundir os dois como Track 1a/1b mantém a distinção sem explodir o diagrama.

✻ Worked for 16s

❯ c

4 tracks confirmados: Track 1a (trabalhador) / 1b (empregador) · Track 2 (advogado/procurador) · Track 3 (excluído digital via PID) · Track 4 (surdo / Balcão Visual).

---

Q4/10: A Celeste deve ser classificada como ator frontstage ou como sistema de suporte?

A Celeste é simultaneamente um canal com o qual o usuário interage diretamente (o bot responde, faz perguntas, agenda) e uma tecnologia que roteia para o atendimento humano. No service blueprint a "linha de visibilidade" separa o que o usuário vê (frontstage) do que opera nos bastidores (backstage/sistemas).

Opções: (A) sistema de suporte — a Celeste é infraestrutura; o atendimento "real" começa no servidor humano; (B) frontstage — a Celeste é o primeiro ator com quem os usuários dos Tracks 1a, 1b e 2 interagem; suas falhas (H1 rigidez algorítmica, H3 atrito no handoff) são falhas de experiência do usuário, não de infraestrutura.

Recommended answer: (B) Frontstage. Se a Celeste for sistema de suporte, as hipóteses H1 e H3 ficam mapeadas na camada errada — o blueprint sugeriria que o problema é técnico/operacional quando na verdade é de interação. Colocar a Celeste no frontstage torna os pontos de falha legíveis para quem for redesenhar a jornada.

✻ Worked for 18s

❯ b

Celeste como ator frontstage confirmado.

---

Q5/10: Atores regulatórios e de governança (CNJ, CSJT, ANPD, Zoom Inc.) devem aparecer no mapa ou ficam fora do blueprint?

O service blueprint clássico termina nos sistemas de suporte — CNJ, CSJT e ANPD nunca aparecem numa sessão de atendimento. Mas o relatório mostra que várias decisões de redesenho batem em tetos regulatórios concretos: a migração Google Meet → Zoom foi mandatada pelo CSJT (Res. 425/2025); expansão de IA na Celeste exige parecer ANPD/LGPD; indicadores do DataJud são auditados pelo CNJ (Res. 372/2021).

Opções: (A) excluir — governança é contexto do relatório, não ator da jornada; (B) incluir numa camada de governança dedicada abaixo dos sistemas de suporte — torna visível que certas recomendações de redesenho precisam de aprovação regulatória antes de serem implementáveis.

Recommended answer: (B) Camada de governança dedicada. Sem ela, recomendações como "trocar de plataforma de vídeo" ou "expandir a Celeste com IA generativa" aparecem no mapa como decisões internas do TRT18, quando na prática dependem de CSJT e ANPD. A camada torna os gargalos políticos e legais explícitos.

✻ Worked for 19s

❯ b

Camada de governança confirmada como Camada 5, abaixo dos sistemas de suporte.

---

Q6/10: O Servidor de Atermação deve aparecer como ator frontstage separado ou ser tratado como função do Servidor do Balcão?

O relatório menciona explicitamente o serviço de Atermação Verbal (art. 791 da CLT) com canal próprio — WhatsApp 62 3222-5570 — distinto do número da Celeste (62 3222-5000). O fluxo é ativado apenas nos encaminhamentos dos Tracks 1a, 1b e 3 (trabalhadores sem advogado que formalizam demanda verbal). O Servidor do Balcão opera nas fases de atendimento e pós-atendimento via Zoom; a atermação é um encaminhamento posterior, fora da sessão Zoom.

Opções: (A) fundir com o Servidor do Balcão — simplifica o diagrama, mas oculta que é um canal separado com número diferente e fase distinta; (B) ator frontstage próprio — torna visível que o usuário precisa de um segundo contato após o balcão para formalizar a demanda, o que é em si uma fricção não mapeada nas hipóteses existentes.

Recommended answer: (B) Ator separado. O fluxo pós-balcão para atermação é pouco sinalizado ao usuário — isso é uma hipótese de fricção nova que o mapa deve explicitar. Fundir os dois atores apagaria esse ponto diagnóstico.

✻ Worked for 15s

❯ b

Servidor de Atermação confirmado como ator frontstage separado, ativo na fase de encaminhamentos para Tracks 1a, 1b e 3.

---

Q7/10: Gestores das Varas / Secretarias devem aparecer no backstage como ator próprio ou seu papel fica absorvido pela Presidência/Corregedoria?

O relatório diferencia dois tipos de controle interno: a Presidência/Corregedoria exerce compliance e aprovação de mudanças de protocolo (nível estratégico/disciplinar), enquanto os Gestores das Varas definem escalas de atendimento e protocolos operacionais do dia a dia — quem atende qual fila, em qual horário, com qual cobertura. O relatório aponta que esses gestores não têm visibilidade em tempo real sobre a carga cognitiva dos servidores do balcão, o que conecta diretamente à hipótese H4 (Fadiga do Zoom).

Opções: (A) absorver na Presidência/Corregedoria — um ator "gestão interna" genérico cobre os dois; (B) ator backstage próprio — torna visível a lacuna de visibilidade operacional em tempo real, que é uma das alavancas para mitigar H4.

Recommended answer: (B) Ator próprio. A distinção importa para o redesenho: a Corregedoria aprova mudanças estruturais, mas quem pode ajustar escalas em resposta à carga cognitiva diária são os Gestores das Varas. Fundir os dois obscurece onde está a alavanca operacional.

✻ Worked for 17s

❯ b

Gestores das Varas / Secretarias confirmados como ator backstage próprio, com responsabilidade sobre escalas operacionais e conexão à hipótese H4.

---

Q8/10: DataJud deve ser classificado como sistema de suporte (Camada 4) ou como elemento da camada de governança (Camada 5)?

O DataJud é tecnicamente uma plataforma de coleta de metadados (tempo de espera, taxa de abandono, categorização de demanda) instituída pela Resolução CNJ nº 331/2020. Ele aparece em dois papéis distintos no relatório: como infraestrutura que registra dados do atendimento (papel de sistema), e como instrumento de auditoria do CNJ sobre as varas trabalhistas (papel de controle regulatório).

Opções: (A) Camada 4 — sistemas de suporte — o DataJud é uma plataforma tecnológica que processa dados gerados pelo serviço, análogo ao PJe e ao Motor da Celeste; (B) Camada 5 — governança — o DataJud é o braço de fiscalização do CNJ, e sua presença no mapa deve sinalizar que os dados do atendimento alimentam auditorias regulatórias externas.

Recommended answer: (A) Camada 4 — sistemas de suporte. O DataJud é operado como plataforma tecnológica pela Ouvidoria e pela TI do tribunal; o CNJ consome os dados, mas não opera o sistema. Colocá-lo em governança confundiria o ator regulatório (CNJ) com o instrumento tecnológico (DataJud). A relação correta é: DataJud (Camada 4) alimenta CNJ (Camada 5).

✻ Worked for 13s

❯ 4

DataJud confirmado na Camada 4 — sistemas de suporte. Relação explícita: DataJud (C4) → CNJ (C5).

---

Q9/10: As hipóteses de fricção (H1–H6) devem aparecer no próprio mapa de atores ou apenas no relatório?

O relatório formula 6 hipóteses de fricção, cada uma associada a atores e fases específicos: H1 (rigidez algorítmica) e H3 (atrito no handoff) ligadas à Celeste; H2 (opacidade da fila) e H4 (fadiga do Zoom) ligadas ao Servidor do Balcão; H5 (barreira PID) ao Track 3; H6 (fragilidade Balcão Visual) ao Track 4. O mapa de atores é o artefato que espacializa essas hipóteses na jornada.

Opções: (A) excluir do mapa — o mapa registra apenas estrutura; hipóteses ficam no relatório; (B) incluir como anotações nos atores relevantes — cada hipótese aparece vinculada ao ator e à fase onde se manifesta, tornando o mapa um instrumento diagnóstico além de descritivo.

Recommended answer: (B) Incluir no mapa. O valor do service blueprint para redesenho está exatamente em localizar onde estão os problemas. Um mapa sem hipóteses de fricção é um organograma — útil para descrever, inútil para intervir. Ancorar H1–H6 nos atores certos transforma o mapa num roteiro de pesquisa.

✻ Worked for 16s

❯ b

Hipóteses H1–H6 confirmadas como anotações ancoradas nos atores e fases correspondentes.

---

Q10/10: Qual formato deve ter o artefato final em C_mapa_atores.md?

Com 5 camadas + governança, 6 fases, 4 tracks e 6 hipóteses, o mapa tem densidade alta. As opções de formato em markdown são: (A) tabela matricial — linhas = camadas, colunas = fases, células = atores + ações; (B) narrativa por camada — uma seção por layer descrevendo atores e fases em prosa; (C) híbrido — diagrama Mermaid de ecossistema + tabela de atores com colunas (camada, tracks, fases ativas, responsabilidade, hipótese associada) + seção de decisões estruturais.

Recommended answer: (C) Híbrido. A tabela matricial com 6 colunas de fase e 20+ atores fica ilegível em markdown. O Mermaid dá a visão de ecossistema; a tabela de atores permite filtrar por camada ou hipótese; a seção de decisões estruturais registra as escolhas deste grill, tornando o artefato auditável. Os três componentes juntos servem tanto para workshop de redesenho quanto para avaliação.

✻ Worked for 12s

❯ c

Shared understanding reached. 10 decisões travadas — construindo C_mapa_atores.md agora.

● Write(C_mapa_atores.md)
