# IA no recrutamento: quem decide de verdade?

Uma empresa vende uma ferramenta que recomenda quais candidatos devem avançar. O gestor afirma: “A decisão é humana, porque um funcionário clica em confirmar”.

```python
def triagem(pontos, clique):
    sugestao = "eliminar" if pontos < 70 else "avançar"

    if clique == "confirmar":
        return sugestao

print(triagem(69, "confirmar"))  # eliminar
```

1. **Código:** a pontuação produz a sugestão. O clique apenas a repete. Este exemplo representa a *etapa de decisão* de um produto hipotético; a regra Python, sozinha, não é IA.

2. **Resultado:** não conseguimos demonstrar que o funcionário viu os dados relevantes, identificou erros ou tinha poder para alterar a sugestão. Chamar essa etapa de “revisão humana” não prova que ela ocorreu.

3. **Fundamento:** o [PL 2.338/2023](https://www.camara.leg.br/proposicoesWeb/fichadetramitacao?idProposicao=2487262), **ainda em tramitação**, inclui a triagem de candidatos entre as aplicações de alto risco e propõe [supervisão capaz de compreender, interpretar, decidir e intervir](https://www.camara.leg.br/proposicoesWeb/prop_mostrarintegra?codteor=2868197&filename=Tramitacao-2-PL-2338-2023). Isso orienta a análise do risco, mas **não deve ser anunciado como lei vigente**.

4. **Decisão do gestor:** antes de contratar ou lançar o produto, definir se a IA apenas recomenda ou elimina candidatos na prática; quem pode reverter o resultado; quais testes serão feitos; e que informação o fornecedor entregará para permitir essa verificação.

5. **Atuação do advogado digital:** acompanhar o fluxo com RH e tecnologia, traduzir o risco em requisitos contratuais e critérios de teste, e conferir se o procedimento descrito corresponde ao que o sistema faz.

**A conclusão é simples:** inserir uma pessoa no fluxo não basta. É preciso verificar se ela consegue exercer julgamento próprio. Esse é o ponto em que compreender o produto se torna parte do trabalho jurídico preventivo.

