---
name: kruzer-product-decision
description: >
  This skill should be used whenever Felipe or the Kruzer product team needs to make, document, or structure any product decision. Triggers include: writing a PRD, structuring a feature request, comparing solution options, prioritizing a backlog, running discovery interviews, or documenting trade-offs for any of the squads (OMS, PIM, Balcão, Convênios). Also use when someone asks "how should we approach X", "which option is better", "help me write a spec", or "help me prioritize". Always use this skill for product work at Kruzer — it replaces ad-hoc document formatting with a consistent, team-calibrated structure.
---

# Kruzer Product Decision Skill

Estrutura decisões de produto para os squads da Kruzer (OMS, PIM, Balcão, Convênios) com consistência e foco em contexto de negócio.

---

## Contexto Kruzer

Sempre considerar:
- **Squads ativos**: OMS, PIM, Balcão, Convênios
- **Time leitor**: interno (PMs, devs, designers — não clientes finais)
- **Dois elementos obrigatórios** em qualquer documento de decisão:
  1. **Mapeamento de dependências entre squads**
  2. **Indicadores de negócio impactados**

---

## Modo de Operação

Detecte o que o usuário precisa e use o template correspondente:

| Situação | Template a usar |
|---|---|
| "preciso documentar uma feature" / "escrever um PRD" | → [PRD Template](#prd-template) |
| "qual opção escolher" / "comparar abordagens" | → [Trade-off Template](#trade-off-template) |
| "o que priorizar" / "ordenar backlog" | → [Priorização Template](#priorizacao-template) |
| "quero entrevistar stakeholder" / "fazer discovery" | → [Discovery Template](#discovery-template) |

**Output**: Adapte conforme o contexto:
- Documento estruturado em Markdown → quando o usuário precisa compartilhar ou registrar
- Resposta direta na conversa → para decisões rápidas ou rascunhos
- `.docx` → quando mencionar "enviar para alguém" ou "apresentar"

---

## PRD Template

```markdown
# [Nome da Feature/Iniciativa]
**Squad**: [OMS | PIM | Balcão | Convênios]
**Data**: [YYYY-MM-DD]
**Autor**: [Nome]
**Status**: [Rascunho | Em revisão | Aprovado]

---

## 1. Problema
> Qual dor estamos resolvendo? Para quem?

[Descrever o problema observado, com evidências se disponível]

## 2. Contexto e Motivação
> Por que agora? O que acontece se não fizermos?

## 3. Solução Proposta
> O que vamos construir?

### Escopo (IN)
- ...

### Fora de Escopo (OUT)
- ...

## 4. Indicadores de Negócio Impactados
| Indicador | Situação Atual | Meta | Como Medir |
|---|---|---|---|
| [ex: taxa de conversão] | | | |
| [ex: tempo de processamento de pedidos] | | | |

## 5. Dependências entre Squads
| Squad | Tipo de Dependência | Ação Necessária | Responsável |
|---|---|---|---|
| OMS | [Consome / Fornece / Bloqueia] | | |
| PIM | | | |
| Balcão | | | |
| Convênios | | | |

## 6. Critérios de Aceite
- [ ] ...
- [ ] ...

## 7. Riscos e Mitigações
| Risco | Probabilidade | Impacto | Mitigação |
|---|---|---|---|
| | | | |

## 8. Próximos Passos
| Ação | Responsável | Prazo |
|---|---|---|
| | | |
```

---

## Trade-off Template

Usar quando houver 2+ opções para comparar.

```markdown
# Decisão: [Título da Decisão]
**Squad**: | **Data**: | **Decisor**: 

## Contexto
[Uma frase: qual é a decisão a ser tomada e por quê ela surgiu]

## Opções Avaliadas

### Opção A: [Nome]
- **O que é**: ...
- **Prós**: ...
- **Contras**: ...
- **Esforço estimado**: [P / M / G]
- **Impacto nos indicadores**: ...
- **Dependências de squads**: ...

### Opção B: [Nome]
- **O que é**: ...
- **Prós**: ...
- **Contras**: ...
- **Esforço estimado**: [P / M / G]
- **Impacto nos indicadores**: ...
- **Dependências de squads**: ...

## Critérios de Decisão
| Critério | Peso | Opção A | Opção B |
|---|---|---|---|
| Impacto no negócio | Alto | | |
| Esforço de implementação | Médio | | |
| Dependências críticas | Alto | | |
| Reversibilidade | Médio | | |

## Recomendação
**Opção escolhida**: [A ou B]
**Justificativa**: ...
**Próximo passo**: ...
```

---

## Priorização Template

Usar frameworks conforme o contexto:

### RICE (recomendado para features com dados)
```
Score = (Reach × Impact × Confidence) / Effort

- Reach: quantos usuários/pedidos afeta por período?
- Impact: [0.25=mínimo / 0.5=baixo / 1=médio / 2=alto / 3=massivo]
- Confidence: [100%=alta / 80%=média / 50%=baixa]
- Effort: pessoa-meses estimados
```

### MoSCoW (recomendado para planejamento de sprint/trimestre)
```
Must have   → Bloqueia operação ou cliente se não tiver
Should have → Importante, mas tem workaround
Could have  → Desejável, entra se sobrar capacidade
Won't have  → Fora do escopo atual (registrar para não perder)
```

**Tabela de saída:**
```markdown
| Feature | Squad | RICE Score | MoSCoW | Dependências | Indicador Impactado |
|---|---|---|---|---|---|
| | | | | | |
```

---

## Discovery Template

Perguntas padrão por tipo de entrevista:

### Stakeholder interno (PM / Dev / Designer)
1. Qual é o maior problema que você enfrenta hoje com [contexto]?
2. Com que frequência isso acontece? Qual o impacto quando ocorre?
3. O que você já tentou para resolver? O que funcionou / não funcionou?
4. Se pudesse mudar uma coisa amanhã, o que seria?
5. Quais outros squads são afetados por esse problema?
6. Como você saberia que resolvemos bem esse problema? (indicadores)

### Refinamento de requisito
1. Qual é o caso de uso principal? E os secundários?
2. Quem são os usuários diretos dessa funcionalidade?
3. O que acontece se der errado? Qual é o pior cenário?
4. Existe alguma restrição técnica ou de negócio que já sabemos?
5. Quais squads precisam ser envolvidos ou notificados?

---

## Instruções de Uso para Claude

1. **Sempre pergunte o squad** se não estiver claro no contexto
2. **Sempre preencha** as seções de Dependências e Indicadores — nunca deixe em branco, mesmo que seja "a mapear"
3. **Adapte o output**: se o usuário está rascunhando, seja conversacional; se pediu documento, gere Markdown limpo (ou ofereça .docx)
4. **Seja direto**: times de produto preferem objetividade. Evite introduções longas.
5. **Se faltar contexto**, faça no máximo 2 perguntas antes de gerar o rascunho — melhor ter algo para editar do que esperar
