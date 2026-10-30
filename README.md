# Atendimento 360 – Serious Game

O **Atendimento 360** é um jogo educativo (*serious game*) desenvolvido como protótipo para treinamento de atendimento ao cliente. O participante responde a 10 questões de múltipla escolha, com tempo limitado e três níveis de dificuldade.

## Objetivo

Proporcionar uma atividade prática para refletir sobre situações comuns de atendimento, como escuta, comunicação, empatia, organização, resolução de problemas e cuidado com dados pessoais.

## Funcionalidades

- Identificação do participante pelo nome.
- Dez questões de múltipla escolha por partida.
- Três níveis de dificuldade.
- Tempo de resposta variável conforme o nível.
- Pontuação por resposta correta e bônus de rapidez.
- Ajuste do nível de acordo com a sequência de acertos e erros.
- Feedback visual após cada resposta.
- Resultado com pontuação, aproveitamento, tempo médio e maior nível.
- Conquistas por desempenho.
- Ranking com a melhor pontuação registrada por participante.
- Histórico das últimas partidas do participante.

## Tecnologias

- **HTML5** para a estrutura da aplicação.
- **CSS3** para a interface e a adaptação a telas menores.
- **JavaScript** para as regras, questões, cronômetro e resultados.
- **LocalStorage** para salvar nome e resultados no navegador.

Não são necessárias bibliotecas externas, banco de dados ou instalação de dependências.

## Como executar

1. Baixe ou clone este repositório.
2. Abra o arquivo `index.html` em um navegador atualizado.
3. Informe o nome do participante.
4. Selecione **Começar treinamento** e responda às dez questões.

Também é possível publicar o projeto pelo GitHub Pages. Para isso, nas configurações do repositório, habilite Pages para a branch principal e a pasta raiz.

## Regras gerais

| Nível da questão | Tempo disponível |
|---|---:|
| 1 | 20 segundos |
| 2 | 15 segundos |
| 3 | 10 segundos |

A pontuação de uma resposta correta considera o nível da questão e um bônus de rapidez: `10 × nível + bônus de até 5 pontos`. Respostas incorretas ou não respondidas não acrescentam pontos.

Após dois acertos consecutivos, o nível de referência pode subir. Uma resposta incorreta ou o término do tempo reduz esse nível. A seleção da questão considera o nível de referência e as questões ainda não utilizadas na partida.

## Conquistas

- **Sem erros:** acertar as dez questões.
- **Reflexo rápido:** obter tempo médio inferior a seis segundos.
- **Nível máximo:** alcançar o nível 3.
- **Bom desempenho:** acertar pelo menos oito questões.

## Armazenamento e limitações

Os dados são armazenados localmente no navegador por meio do `LocalStorage`. Portanto:

- o ranking e o histórico não são compartilhados entre dispositivos;
- os resultados não são enviados para um servidor;
- limpar os dados do navegador pode apagar o histórico;
- o projeto não possui autenticação nem painel administrativo.

A versão atual é um protótipo acadêmico executado no navegador.

## Estrutura

```text
Atendimento-360/
├── index.html
├── README.md
├── .gitignore
└── docs/
    ├── documentacao-tecnica.md
    ├── requisitos.md
    └── plano-de-testes.md
```

## Documentação complementar

- [Documentação técnica](docs/documentacao-tecnica.md)
- [Requisitos do sistema](docs/requisitos.md)
- [Plano de testes](docs/plano-de-testes.md)

## Contexto acadêmico

Projeto desenvolvido no contexto do curso de **Engenharia de Software**, como protótipo de *serious game* voltado ao treinamento empresarial e ao atendimento ao cliente.
