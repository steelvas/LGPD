# Dados do cliente podem ficar guardados para treinar a IA?

Uma empresa contrata uma fornecedora para analisar solicitações. O serviço é entregue, mas a fornecedora também guarda o conteúdo recebido para melhorar seu próprio modelo.

```python
base_treinamento = []

def prestar_servico(solicitacao):
    resultado = "análise entregue"
    base_treinamento.append(solicitacao)
    return resultado

pedido = {"texto": "Exemplo fictício"}
print(prestar_servico(pedido))
print(base_treinamento)  # O conteúdo permanece guardado.
```

1. **Código → resultado:** a análise foi entregue, mas surgiu uma segunda operação: guardar dados para treinamento. O código ilustra a entrada numa base de treinamento; não treina, por si só, um modelo de IA.

2. **Fundamento:** prestar o serviço e treinar um produto próprio podem ser **finalidades diferentes**. A [LGPD](https://www2.camara.leg.br/legin/fed/lei/2018/lei-13709-14-agosto-2018-787077-normaatualizada-pl.html) exige finalidade específica, adequação, necessidade e uma hipótese legal aplicável. “Machine learning” não é base legal nem prazo de guarda. A [ANPD esclarece](https://www.gov.br/anpd/pt-br/acesso-a-informacao/perguntas-frequentes) que a LGPD não fixa um prazo único: ele depende das circunstâncias e da finalidade. O treinamento tampouco é proibido em todos os casos; sua licitude precisa ser demonstrada na operação concreta.

3. **Decisão da empresa-fim:** verificar se os dados enviados ao fornecedor podem ser usados **somente para executar o serviço** ou também para treinamento. Precisa saber quais categorias de dados saem, se há informações sensíveis ou de terceiros, qual é o destino e que alternativa existe para limitar o envio.

4. **Decisão da empresa-meio:** se quiser treinar um modelo próprio, deve identificar essa finalidade separadamente, justificar os dados necessários e a duração da guarda, avaliar os direitos dos titulares e demonstrar os controles aplicados. Ao decidir por conta própria usar dados do cliente para seu produto, **pode deixar de atuar apenas como operadora nessa atividade**; a classificação depende das decisões reais, não do rótulo contratual. O [guia da ANPD](https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-para-definicoes-dos-agentes-de-tratamento-de-dados-pessoais-e-do-encarregado) trata dessa distinção.

5. **Atuação do advogado digital:** confrontar contrato, documentação e fluxo técnico; separar dados necessários ao serviço dos destinados a treinamento; definir permissões, vedações, prazo, critérios de exclusão e meios de verificação. Deve ainda perguntar algo que o código não responde: **excluir o arquivo da base resolve o eventual efeito que ele já teve no modelo?** Isso exige avaliação técnica, não promessa jurídica automática.

**Conclusão:** a frase “guardamos para melhorar a IA” não encerra a análise. O protocolo específico precisa dizer *quem autorizou cada finalidade, quais dados entram, por quanto tempo permanecem e como se comprova o cumprimento*. É nessa passagem do contrato para o comportamento do produto que a assessoria jurídica preventiva agrega valor.

