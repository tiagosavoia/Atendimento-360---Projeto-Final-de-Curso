# Documentação técnica — Atendimento 360

## 1. Visão geral

O Atendimento 360 é uma aplicação web simples, executada no navegador, que apresenta situações de atendimento ao cliente em formato de jogo de perguntas e respostas. O sistema registra o desempenho localmente e apresenta indicadores ao final de cada partida.

## 2. Tecnologias e execução

A aplicação utiliza HTML5, CSS3 e JavaScript sem bibliotecas externas. Os dados de nome e partidas são persistidos com `LocalStorage`.

Para executar localmente, basta abrir `index.html` em um navegador moderno. Não há processo de compilação nem instalação de dependências.

## 3. Organização interna

A implementação está concentrada em `index.html`, que contém:

- marcação HTML das áreas da página;
- regras CSS da interface, incluindo ajustes para telas menores;
- dados das dez questões;
- funções JavaScript de navegação, seleção de questões, cronômetro, pontuação e armazenamento.

### Principais dados

- `questoes`: lista com enunciado, nível, alternativas e índice da alternativa correta.
- `TOTAL_QUESTOES`: quantidade de questões por partida (10).
- `TEMPO_POR_NIVEL`: tempo disponível em cada nível.
- `partida`: estado temporário da partida atual, como rodada, pontos, acertos, nível, tempos e questões utilizadas.

### Principais funções

| Função | Responsabilidade |
|---|---|
| `lerDados` | Recupera dados JSON do armazenamento local. |
| `salvarDados` | Salva dados no `LocalStorage`. |
| `mostrarInicio` | Apresenta o início e o ranking. |
| `iniciarPartida` | Inicializa os dados de uma nova partida. |
| `escolherQuestao` | Seleciona uma questão ainda não utilizada, considerando o nível. |
| `mostrarQuestao` | Exibe a questão e inicia o cronômetro. |
| `atualizarTempo` | Atualiza o tempo restante e a barra de progresso. |
| `responder` | Registra a resposta, calcula pontos e ajusta o nível. |
| `finalizarPartida` | Salva o resultado e apresenta as métricas finais. |

## 4. Fluxo de funcionamento

1. O participante informa o nome na tela inicial.
2. O sistema inicializa uma partida com nível de referência 1.
3. Uma questão ainda não utilizada é selecionada.
4. O cronômetro é iniciado de acordo com o nível da questão apresentada.
5. Ao responder ou esgotar o tempo, o sistema registra o resultado da questão.
6. O sistema atualiza pontuação, sequência de acertos e nível de referência.
7. O fluxo se repete até completar dez questões.
8. O resultado é salvo no navegador e exibido ao participante.

## 5. Regras de negócio

- Cada partida contém dez questões, sem repetição dentro da mesma partida.
- O tempo é de 20 segundos para questões de nível 1, 15 segundos para nível 2 e 10 segundos para nível 3.
- Uma resposta correta soma `10 × nível da questão` e um bônus de rapidez de até 5 pontos.
- Uma resposta incorreta ou não respondida não soma pontos e zera a sequência de acertos.
- Dois acertos consecutivos aumentam o nível de referência em uma unidade, limitado ao nível 3.
- Um erro reduz o nível de referência em uma unidade, limitado ao nível 1.
- O nível máximo alcançado é guardado para compor o resultado.
- O ranking apresenta até cinco participantes, considerando a maior pontuação registrada para cada nome.

## 6. Persistência

O navegador armazena o nome em `atendimento360_nome` e os resultados em `atendimento360_partidas`. A aplicação também consulta chaves utilizadas pela versão anterior (`user` e `sessions`) para tentar aproveitar registros antigos.

Como a persistência é local, os dados ficam restritos ao navegador e ao dispositivo utilizados. Não há sincronização remota.

## 7. Interface e acessibilidade

A interface utiliza CSS responsivo para se adaptar a telas menores, estados visuais para respostas corretas e incorretas, foco visível em controles e regiões com `aria-live` para comunicar atualizações importantes. O sistema também considera a preferência do navegador por redução de movimento.

## 8. Limitações conhecidas

- Não há autenticação de usuários.
- Não há banco de dados remoto nem sincronização entre dispositivos.
- O ranking é local e pode ser alterado por quem controla o navegador.
- O conteúdo e a quantidade de questões são definidos no código.
- Não existe painel para cadastrar ou editar perguntas pela interface.

## 9. Possíveis evoluções

Como trabalho futuro, podem ser avaliados: separação de HTML, CSS e JavaScript em arquivos próprios; armazenamento em servidor; autenticação; painel de gerenciamento de questões; exportação de relatórios; e ampliação das explicações educativas após cada resposta.
