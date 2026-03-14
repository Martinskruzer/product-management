# kruzer-pm

Plugin de Product Management para o time da Kruzer. Contém todas as skills de PM — o Claude identifica automaticamente qual usar com base na task descrita, sem necessidade de invocar manualmente.

## Como funciona

Basta descrever o que você precisa em linguagem natural. O Claude lê a descrição da task e ativa a skill mais adequada. Por exemplo:

- "quero escrever o PRD do novo módulo de Convênios" → ativa `prd`
- "me ajuda a priorizar o backlog do squad OMS" → ativa `priorizacao`
- "preciso criar as user stories para essa feature" → ativa `user-stories`
- "vamos planejar o discovery do problema X" → ativa `discovery-brief`

## Skills incluídas

| Skill | Quando usar |
|-------|-------------|
| `prd` | Iniciativas novas/complexas pós-discovery |
| `feature-brief` | Features com escopo claro, sem discovery |
| `priorizacao` | Sessões de priorização de backlog ou iniciativas |
| `product-roadmap` | Criar ou atualizar o roadmap trimestral/semestral |
| `user-stories` | Quebrar PRD/Feature Brief em tasks para ClickUp |
| `discovery-brief` | Planejar a etapa de discovery |
| `discovery-report` | Consolidar aprendizados do discovery |
| `decision-record` | Registrar uma decisão no momento em que é tomada |
| `decision-log` | Retrospectiva de decisões pós-entrega |
| `assumption-map` | Mapear e priorizar premissas (Impacto × Confiança) |
| `experiment-design` | Desenhar experimento lean para validar hipótese |
| `problem-brief` | Qualificar um problema antes de alocar recursos |
| `strategic-bet` | Formalizar uma aposta estratégica |
| `north-star-metric` | Definir North Star e árvore de métricas |
| `outcome-review` | Avaliar se a iniciativa entregou o resultado prometido |
| `changelog` | Documentar o que foi entregue após deploy/sprint |
| `gtm-brief` | Planejar o lançamento de produto ou feature |
| `competitive-battlecard` | Criar battlecard para o time comercial |
| `figma-handoff` | Checklist de handoff de Figma para dev |
| `tech-spec` | Documentar decisões técnicas com impacto em produto |
| `kruzer-product-decision` | Skill mestra — usada para qualquer decisão de produto da Kruzer |

## Instalação no Claude Code

```bash
claude plugin install kruzer-pm.plugin
```

Após instalar, as skills ficam disponíveis em todos os projetos automaticamente.
