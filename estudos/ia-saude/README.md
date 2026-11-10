# Por que o jurídico precisa conhecer o sistema

Uma empresa oferece IA para apoiar médicos e afirma que retira os dados que identificam o paciente antes de enviar o caso ao modelo. Veja um exemplo didático:

```python
def preparar_caso(texto, nome):
    return texto.replace(nome, "[PACIENTE]")

caso = "Ana, CPF fictício 000.000.000-00, relata dor no peito."
enviado = preparar_caso(caso, "Ana")
print(enviado)
# [PACIENTE], CPF fictício 000.000.000-00, relata dor no peito.
assert "000.000.000-00" not in enviado
# O teste falha: o identificador continua no texto.
```

1. **A promessa:** a empresa diz que protege a identidade do paciente.

2. **O comportamento:** o código remove o nome, mas deixa passar outro identificador. Executar corretamente a instrução não significa cumprir a promessa.

3. **O fundamento:** no sandbox de IA da ANPD, testes de uma solução clínica mostraram que filtros não confirmavam a premissa inicial de anonimização. O relatório registrou erros clínicos e bibliográficos. São achados daquela solução, não de toda IA em saúde. [Relatório da ANPD](https://www.gov.br/anpd/pt-br/assuntos/projetos-acoes-iniciativas/sandbox/sandbox-relatorio-final-v1-0.pdf/@@display-file/file).

4. **Dois controles diferentes:** pseudonimizar dados reduz riscos de identificação; não confirma se uma sugestão médica está correta. O médico precisa conseguir examiná-la e rejeitá-la. Isso não afasta os deveres da empresa pelas decisões de tratamento de dados que efetivamente toma.

5. **O trabalho do advogado:** descobrir o que sai do sistema, testar se o filtro funciona, verificar como ocorre a revisão médica e conferir se o contrato descreve a operação real.

**Conclusão:** política e contrato descrevem o que deveria acontecer. O teste mostra o que acontece. Um protocolo jurídico útil precisa conectar os dois.

*Código fictício para estudo; não é uma solução de pseudonimização nem um sistema clínico.*
