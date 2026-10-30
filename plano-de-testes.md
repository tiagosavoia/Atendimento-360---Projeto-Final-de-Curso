# Plano de testes — Atendimento 360

## 1. Objetivo

Definir verificações manuais para avaliar as principais funções do Atendimento 360. Os casos abaixo descrevem o que deve ser testado e o resultado esperado; eles não significam que todos os testes já foram executados.

## 2. Ambiente sugerido

- Navegador atualizado (Google Chrome, Microsoft Edge ou Firefox).
- Computador e, quando possível, celular.
- Armazenamento local habilitado no navegador.

## 3. Casos de teste

| ID | Cenário | Procedimento | Resultado esperado |
|---|---|---|---|
| CT01 | Abrir o jogo | Abrir `index.html` no navegador. | A tela inicial e o ranking são apresentados sem erro. |
| CT02 | Nome obrigatório | Tentar iniciar sem preencher o nome. | A partida não começa e o campo de nome recebe foco. |
| CT03 | Iniciar partida | Informar um nome e selecionar o botão de início. | A primeira questão é apresentada. |
| CT04 | Quantidade de questões | Concluir uma partida respondendo a todas as questões. | A partida contém dez questões e termina após a décima resposta. |
| CT05 | Tempo do nível 1 | Apresentar uma questão de nível 1. | O cronômetro inicia em 20 segundos. |
| CT06 | Tempo do nível 2 | Apresentar uma questão de nível 2. | O cronômetro inicia em 15 segundos. |
| CT07 | Tempo do nível 3 | Apresentar uma questão de nível 3. | O cronômetro inicia em 10 segundos. |
| CT08 | Resposta correta | Selecionar a alternativa correta antes do fim do tempo. | A alternativa correta é destacada e a pontuação aumenta. |
| CT09 | Resposta incorreta | Selecionar uma alternativa incorreta. | A alternativa selecionada é destacada como incorreta, a correta é indicada e não há pontos para a questão. |
| CT10 | Tempo esgotado | Aguardar o cronômetro chegar a zero. | A questão é registrada como não respondida e não soma pontos. |
| CT11 | Bloqueio de resposta duplicada | Após responder, tentar selecionar outra alternativa. | As alternativas permanecem desabilitadas e a questão não é contabilizada novamente. |
| CT12 | Progressão de nível | Obter dois acertos consecutivos. | O nível de referência pode subir, sem ultrapassar o nível 3. |
| CT13 | Redução de nível | Errar uma questão. | O nível de referência diminui, sem ficar abaixo do nível 1. |
| CT14 | Resultado final | Concluir as dez questões. | São exibidos pontos, percentual de acertos, tempo médio, maior nível e conquistas aplicáveis. |
| CT15 | Persistência | Concluir uma partida e atualizar a página ou voltar à tela inicial. | O resultado continua disponível no mesmo navegador. |
| CT16 | Ranking | Concluir partidas com nomes diferentes. | O ranking apresenta até cinco participantes, considerando a melhor pontuação de cada nome. |
| CT17 | Histórico | Concluir mais de uma partida com o mesmo nome. | O gráfico apresenta as partidas recentes registradas para esse participante. |
| CT18 | Nova partida | Selecionar “Jogar novamente” após o resultado. | Uma nova partida começa com pontuação e contadores reiniciados. |
| CT19 | Responsividade | Abrir o jogo em uma tela estreita ou dispositivo móvel. | Os elementos se ajustam à largura disponível sem impedir a interação. |
| CT20 | Nome com caracteres especiais | Informar um nome com acentos ou caracteres como `&` e `<`. | O nome é exibido como texto, sem ser interpretado como marcação HTML. |

## 4. Registro da execução

Preencha esta tabela somente depois de executar os testes:

| ID | Resultado observado | Status (Aprovado/Reprovado/Pendente) | Observações |
|---|---|---|---|
| CT01 |  |  |  |
| CT02 |  |  |  |
| CT03 |  |  |  |
| CT04 |  |  |  |
| CT05 |  |  |  |
| CT06 |  |  |  |
| CT07 |  |  |  |
| CT08 |  |  |  |
| CT09 |  |  |  |
| CT10 |  |  |  |
| CT11 |  |  |  |
| CT12 |  |  |  |
| CT13 |  |  |  |
| CT14 |  |  |  |
| CT15 |  |  |  |
| CT16 |  |  |  |
| CT17 |  |  |  |
| CT18 |  |  |  |
| CT19 |  |  |  |
| CT20 |  |  |  |

## 5. Critério de conclusão

Os testes podem ser considerados concluídos após a execução dos cenários no ambiente definido, com registro do resultado observado. Corrija os defeitos encontrados e repita os casos afetados antes de registrar a versão como validada.
