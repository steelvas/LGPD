# Exclusão de dados: apagar na tela é suficiente?

Uma pessoa pede a exclusão de seus dados. A empresa confirma o pedido porque o cadastro desapareceu do aplicativo. Mas sua fornecedora de tecnologia ainda mantém cópias.

```python
copias = {
    "aplicativo": True,
    "banco_de_dados": True,
    "backup": True,
    "fornecedor": True,
}

copias["aplicativo"] = False

print(copias)
# O cadastro sumiu da tela; as outras cópias continuam.
```

1. **Código → resultado:** alterar o aplicativo não demonstra o que ocorreu no banco, nos backups ou com terceiros. O exemplo é uma simulação de estados, não um procedimento real de exclusão.

2. **Fundamento:** a [LGPD](https://www2.camara.leg.br/legin/fed/lei/2018/lei-13709-14-agosto-2018-787077-normaatualizada-pl.html) prevê eliminação após o término do tratamento, mas admite hipóteses justificadas de conservação (arts. 15 e 16). Também permite pedir a eliminação de dados desnecessários, excessivos ou tratados irregularmente e, em condições próprias, dos dados tratados com consentimento (art. 18, IV e VI). Portanto, o protocolo não pode prometer “apagar tudo imediatamente” sem antes verificar **o que deve ser eliminado e o que deve ser conservado legalmente**. A LGPD ainda prevê a comunicação da eliminação a agentes com quem houve compartilhamento, ressalvadas as exceções legais (art. 18, § 6º).

3. **Decisão da empresa-fim:** identificar onde os dados estão, por que cada cópia existe, quem recebeu os dados e qual é o fundamento e o prazo de eventual conservação. Se ela determina a finalidade e os elementos essenciais do tratamento, atua como controladora — não se desobriga porque contratou tecnologia.

4. **Decisão da empresa-meio:** definir como recebe a instrução, executa a exclusão nos ambientes sob seu controle, trata cópias de segurança e subfornecedores, impede que uma restauração reintroduza dados excluídos e entrega evidências verificáveis. Se atua como operadora, deve seguir as instruções da controladora (art. 39); o nome escrito no contrato não substitui a análise das decisões que efetivamente toma. Veja também o [guia da ANPD sobre agentes de tratamento](https://www.gov.br/anpd/pt-br/centrais-de-conteudo/materiais-educativos-e-publicacoes/guia-orientativo-para-definicoes-dos-agentes-de-tratamento-de-dados-pessoais-e-do-encarregado).

5. **Atuação do advogado digital:** construir com as equipes um protocolo próprio para cada operação: pedido recebido → análise jurídica da retenção → instrução técnica → execução nas cópias pertinentes → verificação → resposta ao titular. No contrato, especificar responsáveis, prazos, subfornecedores, tratamento de backups e evidências. Depois, testar se o fluxo funciona.

**Conclusão:** um protocolo genérico diz “excluímos dados”. Um protocolo útil permite responder *quais dados, de quais sistemas, por quem, quando, com qual exceção legal e mediante qual prova*. O advogado precisa conhecer tanto o serviço vendido pela empresa-fim quanto a arquitetura operada pela empresa-meio para transformar essa resposta em obrigação executável — sem prometer que um registro de sistema, sozinho, prova a eliminação definitiva.

