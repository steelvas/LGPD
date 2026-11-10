# LGPD, decisões automatizadas e responsabilidade digital

Estudo didático. Não é aconselhamento jurídico e não utiliza dados reais de pessoas.

## O antipadrão que deve ser proibido

```python
# NÃO EXECUTE / EXEMPLO PROPOSITADAMENTE ERRADO

bairro = "Bairro Exemplo"
print("negar crédito")
```

O rótulo de um bairro não é critério jurídico lícito apenas porque o código é executado. Riscos: discriminação indireta/proxy, falta de finalidade/adequação/necessidade/transparência, ausência de contestação/revisão significativas, prestação de contas (accountability) frágil.

## Base jurídica de estudo

- **Art. 6, LGPD**: princípios — finalidade, adequação, necessidade, livre acesso, não discriminação, prestação de contas.
- **Art. 20, LGPD**: direito de solicitação de informação e revisão de decisões exclusivamente automatizadas que afetem interesses.
- **Art. 42, LGPD**: responsabilidade por dano decorrente de tratamento ilícito.

Avaliação jurídica é caso a caso. Regras do consumo, do Civil e setoriais podem ser aplicáveis.

## Exemplo seguro — não decide crédito

```python
controles = {
    "consent": True,
    "data_quality": True,
    "traceability": True,
    "human_review_authority": True,
}

def validar_processo(controles):
    faltam = [k for k, v in controles.items() if not v]
    if faltam:
        return "revisão humana e jurídica necessária"
    return "fluxo autorizado para análise"

audit_events = []

def registrar(controles):
    from datetime import datetime
    faltam = [k for k, v in controles.items() if not v]
    event = {
        "timestamp": datetime.now().isoformat(),
        "model_version": "0.1-didatico",
        "missing_controls": faltam,
    }
    audit_events.append(event)
    return validar_processo(controles)

resultado = registrar(controles)
# este registro é meramente ilustrativo e não constituye prova imutável
```

## Protocolo prático por empresa

1. Mapear dados, fluxos e destinatários.
2. Definir finalidade e base jurídica de cada tratamento.
3. Avaliar viés e proxies (incluindo CEP/bairro/raça/classe).
4. Designar revisor humano com autoridade documentada.
5. Manter logs versionados de modelos, dados e decisões.
6. Criar canal de acesso, correção e contestação.
7. Auditar fornecedores/suboperadores e ambientes de nuvem.
8. Definir fluxo de incidente, backup, exclusão e restauração.
9. Realizar testes periódicos e registrar evidências.

Cada controlador/operator deve adaptar o protocolo à sua função econômica, setor, dados, risco, arquitetura e escala.

## Papéis

- **Controlador/negócio**: decide as finalidades e meios essenciais e governa o tratamento.
- **Fornecedor técnico/operator**: executa instruções lícitas documentadas e mantém sua própria segurança.
- **Contrato**: aloca tarefas, mas não apaga a responsabilidade legal.
- **Autonomia real**: um vendor pode se tornar controlador independente quando decide finalidades/meios por conta própria.

## Prova de conformidade

| Declared | Documented | Verified |
|----------|-----------|----------|
| "A decisão é humana quando necessário" | SOPs, matris de base jurídica | Logs, auditorias, revisões de modelo |

A tecnologia não é neutra só porque computa.
