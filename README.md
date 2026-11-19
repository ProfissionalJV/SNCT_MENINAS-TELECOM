# Quiz Meninas Telecom: conectando o futuro com elas

Quiz para totem do projeto **Meninas Telecom**, do Ministério das Comunicações em parceria com a Anatel, apresentado na Semana Nacional de Ciência e Tecnologia. Tema: mulheres nas telecomunicações e na tecnologia.

> Jogo em um único arquivo HTML, com fontes e imagens embutidas. Interface em português (pt-BR). Não depende de bibliotecas nem de CDN. Identidade visual roxo e amarelo.

## Como é uma partida

1. **Início**, com o texto de apresentação do projeto
2. **Cartas de explicação:** 3 cartas viradas para baixo. A pessoa toca em cada uma para ler e só depois segue.
3. **Quem vai jogar?** (crianças ou adultos)
4. **5 perguntas**
5. **Encerramento**, com confete a partir de 4 acertos e os botões **Jogar novamente** e **Voltar ao início**

## Como rodar

- **No totem (sem internet):** deixe todos os arquivos na mesma pasta e abra `jogo-meninas-telecom.html` em tela cheia (F11) no Chrome ou Edge.
- **Online:** publique a pasta em qualquer hospedagem de arquivos estáticos (por exemplo, Cloudflare). Hospedado, o jogo precisa de internet.

Funciona em **1920x1080** (deitado) e **1080x1920** (totem em pé). O layout muda sozinho.

## Estrutura

```
jogo-meninas-telecom.html   o jogo
perguntas-telecom.js        todas as perguntas
img/                        logos e adesivos
```

O arquivo de perguntas se chama `perguntas-telecom.js`.

## Perguntas

Ficam em `perguntas-telecom.js`, com 32 perguntas para crianças e 33 para adultos. Cada partida sorteia 5:

```js
window.PERGUNTAS = {
  criancas: [
    { p: "Pergunta?", r: ["A", "B", "C", "D"], c: 3, e: "Explicação opcional.", tema: "telecom" },
  ],
  adultos: [ /* ... */ ],
};
```

- `c` é a posição da alternativa certa (0 a 3). As alternativas são embaralhadas a cada pergunta.
- Para acrescentar perguntas, coloque mais linhas no fim da lista de crianças ou de adultos.
- Se o arquivo não for encontrado, o jogo usa 5 perguntas de exemplo que ficam dentro do HTML.

## Configuração

No começo do script do HTML:

| Constante | O que faz |
|---|---|
| `PERGUNTAS_POR_PARTIDA` | Perguntas por partida (5) |
| `EMBARALHAR_PERGUNTAS` | `true` sorteia a ordem a cada partida; `false` segue a ordem do arquivo |
| `ACERTOS_PARA_COMEMORAR` | Acertos para o confete (4) |
| `LOGO` | Logo do topo; para trocar, ponha o arquivo em `img/` e aponte aqui |
| `MOSTRAR_APOIO` | Mostra ou esconde a assinatura de apoio |
| `INATIVIDADE_SEGUNDOS` / `INATIVIDADE_CONTAGEM` | Tempo parado até avisar e contagem até voltar ao início |
| `MODO_LEVE` | `true` desliga desfoque e reduz efeitos, para computadores fracos (também vale `?leve` no endereço) |
| `TEXTO_OBJETIVO` | Primeira frase da introdução |
| `CARTAS` | Texto das 3 cartas de explicação |

O roteiro original terminava a primeira frase da introdução em "tem como objetivo", e `TEXTO_OBJETIVO` foi completado com o texto do encerramento. Troque pelo texto oficial se for outro. Os títulos das cartas também são sugestões, pois o roteiro trazia só o texto.

## Créditos

Ministério das Comunicações e Anatel. Conteúdo das perguntas: equipe do projeto.
<span class="credito">Desenvolvido por: Victor A. Lêla © 2026</span>
