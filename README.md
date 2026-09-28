# Converte Mais

O **Converte Mais** é uma ferramenta web que ajuda a transformar conteúdos de PDFs em texto formatado e HTML. O usuário trabalha com marcadores simples inseridos no texto, e a aplicação converte esse conteúdo para facilitar sua reutilização em documentos e plataformas de ensino.

## Funcionalidades

- Carregamento e visualização de um PDF ao lado do editor de texto, sem precisar alternar entre janelas.
- Conversão de marcadores em parágrafos, títulos, negrito, itálico, listas, citações, tabelas e blocos de código.
- Inserção de imagens com legenda, fonte e descrição, além de numeração automática e uma lista de imagens utilizadas.
- Limpeza de espaços e quebras de linha excessivas e aplicação de padrões de espaçamento e alinhamento.
- Destaque de palavras que precisam de revisão, perguntas retóricas e números sem espaçamento adequado antes de unidades de medida.
- Cópia do resultado como texto ou HTML, para uso em documentos e plataformas como o Moodle.
- Salvamento automático do texto no navegador para preservar o trabalho entre acessos.
- Atalhos de teclado para agilizar a edição e a conversão.

## Como usar

1. Acesse [Converte Mais](https://converte-mais.vercel.app/).
2. Carregue um PDF na área ao lado do editor para consultar o material enquanto trabalha.
3. Digite ou cole o conteúdo no editor e use os marcadores ou atalhos disponíveis.
4. Clique em **GERAR** ou use `Ctrl + Enter` para converter.
5. Copie o resultado como texto ou HTML usando os botões correspondentes.

## Marcadores disponíveis

Os marcadores são escritos no próprio texto. Use `(p)` para separar parágrafos e, quando indicado, repita o marcador para delimitar o conteúdo. Os atalhos abaixo são usados no editor de texto.

### Texto e formatação

| Marcador | Função | HTML gerado | Atalho |
| --- | --- | --- | --- |
| `(p)` | Separa parágrafos. | `<p>` | Alt + S |
| `# Título #` até `###### Título ######` | Cria títulos de nível 1 a 6. | `<h1>` a `<h6>` | Alt + 1 a Alt + 6 |
| `(st)texto(st)` | Aplica negrito. | `<strong>` | Alt + X |
| `(em)texto(em)` | Aplica itálico. | `<em>` | Alt + Z |
| `(sub)texto(sub)` | Formata texto subscrito. | `<sub>` | Alt + U |
| `(sup)texto(sup)` | Formata texto sobrescrito. | `<sup>` | Alt + Y |
| `(pcent)texto` | Centraliza um parágrafo. | `<p style="text-align: center">` | — |
| `(br)` | Insere uma quebra de linha. | `<br>` | Alt + Q |
| `(linha)` | Insere uma linha horizontal. | `<hr>` | Alt + L |

### Listas

| Marcador | Função | HTML gerado | Atalho |
| --- | --- | --- | --- |
| `(ul)item` | Cria um item de lista não ordenada; repita `(ul)` para cada item. | `<ul><li>` | Alt + D |
| `(ol)item` | Cria um item de lista ordenada; repita `(ol)` para cada item. | `<ol><li>` | Alt + F |
| `(x)`, `(X)`, `(i)`, `(I)` ou `(0)` após o primeiro `(ol)` | Define a numeração como letras minúsculas/maiúsculas, algarismos romanos minúsculos/maiúsculos ou números com zero à esquerda. | `<ol style="list-style-type: ...">` | — |

### Tabelas e imagens

| Marcador | Função | HTML gerado | Atalho |
| --- | --- | --- | --- |
| `(table) ... (table)` | Delimita uma tabela. Separe células com `;` e linhas com `;;`. | `<table><tr><td>` | Alt + B |
| `(th)` | Define uma célula de cabeçalho. | `<th>` | Alt + H |
| `(th):` | Define uma célula de cabeçalho centralizada. | `<th style="text-align: center">` | Alt + J |
| `:` no início de uma célula | Centraliza o conteúdo da célula. | `<td style="text-align: center">` | — |
| `(colspan=n)` / `(rowspan=n)` | Mescla uma célula por colunas ou linhas, usando `n` como quantidade. | Atributos `colspan="n"` / `rowspan="n"` em `<td>` ou `<th>` | — |
| `(img | URL | LEGENDA | FONTE | DESCRIÇÃO)` | Insere uma imagem com legenda, fonte e descrição. | `<figure>`, `<img>` e elementos de legenda/fonte | Alt + I |

### Citações, caixas e código

| Marcador | Função | HTML gerado | Atalho |
| --- | --- | --- | --- |
| `(block)` / `(/block)` | Abre e fecha uma citação longa. | `<blockquote>` | Alt + K |
| `(box)` / `(/box)` | Abre e fecha uma caixa de conteúdo destacada. | `<div>` com estilos | Alt + O |
| `(code)texto(code)` | Formata um trecho de código em linha. | `<code>` | Alt + C |
| `(pre)` | Preserva espaços e formatação do texto que vem após o marcador. | `<div style="white-space: pre-wrap">` | Alt + P |
| `(precode)` | Cria um bloco de código com as tags HTML `<pre><code>`. | `<pre><code>` | Alt + Ç |
| `(codeblock)` | Cria um bloco de código formatado e exibe tags HTML como texto. | `<div><pre>` | Alt + N |
| `(ref [texto da referência])` | Marca uma referência, reunida automaticamente na saída. | `<ul><li>` na lista de referências | Alt + R |

## Futuras melhorias

- Fix: ctrl + z não funciona após uso de atalhos
- Add: âncoras que levam de volta pro topo
- Add: clicar no botão e incluir texto do botão no prompt
- Fix: `<table>` lista dentro de colspan em tabela (testar rowspan)
- Fix: `<ul>` e `<ol>` colocar tabela, imagens e listas dentro de listas
- Add: texto em duas colunas (`<div style="column-count: 2; column-gap: 20px; text-align: center; white-space: pre-wrap;">`)
- Update: melhorar lista das imagens usadas (idéias: botão que abre popup/janela, dois cliques abre a foto em uma nova aba)
- Add: possibilidade de editar o html direto
- Add: escape para tags html
- Fix: `<br>` em títulos
- Add: botão para mandar sugestão
- Add: carregar o pdf a ser convertido dentro da ferramenta
- Add: botão para converter bullets "•" ou "-" em (ul)
- Add: botão "TEXTO PARA QUESTÕES" (sem fotos, sem referências)
- Update: inserir âncoras nas palavras proibidas para que possa clicar e levar até o ponto onde deve ser feito a edição
- Update: `<table>` inserir título (legenda?) de tabela
- Add: textarea secundário para "fixar" as referências e o "material baseado em" 
- Add: criar marcador para referências
- Add: criar marcador genérico, para questões que devem ser resolvidas depois
- Add: marcador para numeração automática de tabelas e quadros


---

*Última autalização: 28/09/2026*