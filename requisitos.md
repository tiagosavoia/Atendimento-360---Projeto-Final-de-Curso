# Requisitos do sistema — Atendimento 360

## 1. Objetivo

Registrar os requisitos funcionais e não funcionais observados na versão atual do Atendimento 360. Este documento descreve o comportamento implementado no protótipo.

## 2. Atores

- **Participante:** informa o nome, responde às questões e consulta o próprio resultado.
- **Navegador:** executa a aplicação e mantém os dados no armazenamento local.

## 3. Requisitos funcionais

| ID | Requisito |
|---|---|
| RF01 | O sistema deve permitir que o participante informe seu nome antes de iniciar uma partida. |
| RF02 | O sistema deve apresentar dez questões de múltipla escolha em cada partida. |
| RF03 | O sistema deve apresentar três alternativas para cada questão. |
| RF04 | O sistema deve indicar o nível da questão apresentada. |
| RF05 | O sistema deve limitar o tempo de resposta conforme o nível: 20, 15 ou 10 segundos. |
| RF06 | O sistema deve encerrar a possibilidade de resposta quando o tempo terminar. |
| RF07 | O sistema deve indicar visualmente a alternativa correta após a resposta. |
| RF08 | O sistema deve calcular a pontuação das respostas corretas considerando o nível e o tempo utilizado. |
| RF09 | O sistema deve ajustar o nível de referência de acordo com a sequência de acertos e erros. |
| RF10 | O sistema deve apresentar a pontuação final, o percentual de acertos, o tempo médio e o maior nível alcançado. |
| RF11 | O sistema deve atribuir conquistas conforme as condições de desempenho programadas. |
| RF12 | O sistema deve registrar o resultado da partida no armazenamento local do navegador. |
| RF13 | O sistema deve apresentar um ranking com até cinco participantes, considerando a melhor pontuação de cada nome. |
| RF14 | O sistema deve apresentar o histórico das últimas partidas do participante atual. |
| RF15 | O sistema deve permitir iniciar uma nova partida ou voltar à tela inicial após o resultado. |

## 4. Requisitos não funcionais

| ID | Requisito |
|---|---|
| RNF01 | O sistema deve ser executado em navegador web moderno. |
| RNF02 | A interface deve se adaptar a diferentes larguras de tela. |
| RNF03 | Os controles devem apresentar indicação visual de foco para navegação por teclado. |
| RNF04 | O sistema deve utilizar armazenamento local do navegador para persistir nome e resultados. |
| RNF05 | A aplicação deve funcionar sem instalação de bibliotecas ou dependências externas. |
| RNF06 | O conteúdo textual da interface deve estar em português do Brasil. |
| RNF07 | A aplicação deve continuar utilizável mesmo quando o armazenamento local não estiver disponível, embora não consiga persistir os dados nesse caso. |

## 5. Regras de negócio

- RN01: uma partida contém dez questões distintas.
- RN02: o tempo depende do nível da questão apresentada.
- RN03: somente respostas corretas geram pontos.
- RN04: o bônus de rapidez pode acrescentar até cinco pontos por acerto.
- RN05: dois acertos consecutivos elevam o nível de referência, respeitando o limite de três.
- RN06: uma resposta incorreta ou o tempo esgotado reduz o nível de referência, respeitando o limite de um.
- RN07: o ranking considera a maior pontuação de cada nome.
- RN08: as informações são mantidas localmente no navegador.

## 6. Fora do escopo da versão atual

Não fazem parte da implementação atual: cadastro com senha, recuperação de conta, sincronização online, banco de dados remoto, gestão administrativa de questões e emissão automática de certificados.
