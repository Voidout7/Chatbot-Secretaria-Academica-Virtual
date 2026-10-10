# Chatbot de Triagem do SAV

Sistema inteligente de triagem e atendimento para a Secretaria Virtual Acadêmica (SAV) da FATEC Barueri, baseado em um agente de IA integrado ao SAV via API.

## Problema

O SAV é o principal canal entre alunos e secretaria acadêmica, mas funciona com uma fila estritamente sequencial (FIFO): dúvidas simples e recorrentes (limite de faltas, notas, calendário, grade) competem com casos graves (problemas de matrícula, contestações). Como resultado, chamados previstos para 3 a 5 dias chegam a levar de 7 a 9 dias, principalmente em períodos de pico, como início de semestre, provas e rematrícula.

## Solução

Um chatbot posicionado antes da abertura do ticket, funcionando 24/7 como primeira linha de atendimento:

- Identifica a intenção do aluno e responde de imediato às dúvidas recorrentes, com base em informações oficiais da instituição.
- Encaminha ao atendimento humano (handoff) quando:
  - a confiança da resposta é baixa (Confidence Threshold);
  - há gatilhos de urgência institucional;
  - detecta frustração do usuário (ex.: loop de perguntas).
- No encaminhamento, o ticket já chega com o contexto da conversa e uma prioridade sugerida.

O chatbot não substitui a equipe do SAV: ele filtra o que é repetitivo e entrega uma fila menor e mais organizada.

## Benefícios

- **Alunos:** respostas imediatas, sem depender de expediente ou posição na fila.
- **Equipe do SAV:** menos tickets repetitivos e atendimento priorizado por urgência.
- **Instituição:** ganho de eficiência sem ampliar a equipe e respostas padronizadas.

## Objetivos

**Geral:** desenvolver e prototipar um sistema de triagem e atendimento para o SAV, com agente de IA integrado via API, que automatize dúvidas recorrentes e escale chamados críticos para a equipe administrativa.

**Específicos:**

1. **Mapeamento e classificação:** levantar requisitos funcionais e não funcionais do fluxo atual e classificar as intenções mais frequentes (notas, calendário, faltas) para compor a base de conhecimento.
2. **Integração de sistemas:** definir a arquitetura de integração via API entre a interface de conversação e a base de dados do SAV, de forma automatizada e segura.
3. **Engenharia de escalonamento:** configurar regras de transferência de contexto ao suporte humano (confiança mínima, gatilhos de criticidade e detecção de frustração).
4. **Painel administrativo:** prototipar um painel que organize a fila de tickets escalados por prioridade, com resumo da intenção e histórico da conversa com a IA.
5. **Validação do MVP:** avaliar a eficácia por meio de testes funcionais, medindo a redução no tempo de atendimento e a capacidade do bot de resolver chamados sem intervenção humana.

## Equipe

| Integrante | Frente principal | Papel no Scrum |
|---|---|---|
| David | Back-end e integração | Scrum Master |
| Gabriel | Inteligência / PLN | Desenvolvedor |
| Ian | Front-end e UX | Desenvolvedor |
| Indaiá | Requisitos, qualidade e documentação | Product Owner |

## Cronograma

Método: Scrum adaptado, 6 sprints, de 05/10/2026 a 11/12/2026. Detalhes completos em [`docs/Cronograma.pdf`](docs/Cronograma.pdf).

| Sprint | Período | Foco |
|---|---|---|
| 0 | 05/10 a 11/10 | Planejamento |
| 1 | 12/10 a 25/10 | Levantamento e prototipação |
| 2 | 26/10 a 08/11 | Base do sistema (MVP em 08/11) |
| 3 | 09/11 a 22/11 | Triagem e encaminhamento |
| 4 | 23/11 a 06/12 | Testes com usuários e ajustes |
| 5 | 07/12 a 11/12 | Entrega e defesa |

## Estrutura do repositório

```
.
├── README.md
├── docs/
│   └── Cronograma.pdf
├── src/          # código-fonte (back-end, front-end, módulo de IA)
└── .gitignore
```

## Links

- [Formulário de Avaliação](https://docs.google.com/forms/d/e/1FAIpQLSdplX-vxtJQnkJo8aCcxSn-VV-2HvkT6UrDKd3g3WWMSBYGYw/viewform)
