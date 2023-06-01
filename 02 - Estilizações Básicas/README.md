# Estilização Básica

- [Seletores](#seletores)
- [Combinadores](#combinadores)
- [Dimensionamento e Espaçamento](#dimensionamento-e-espaçamento)
- [Cores](#cores)
- [Imagens](#imagens)
- [Fundo dos Elementos](#fundo-dos-elementos)
- [Bordas](#bordas)
- [Fontes](#fontes)
- [Textos](#textos)
- [Sombras](#sombras)

## Seletores

Selecionam elementos para aplicar o CSS:

- Por Tipos: Busca por uma tag HTML específica.
- Por ID (#): Busca através do atributo _id_.
- Por Classe (.): Busca através do atributo _class_
- Universal (*): Seleciona todos os elementos HTML.
- De Atributo ([att]): Seleciona elementos que possuem um atributo específico no documento HTML e também busca atributos com um valor específico.

## Combinadores

    [SELETOR] [COMBINADOR] [SELETOR] [COMBINADOR] [SELETOR] ...

Para aplicar as mesmas regras CSS para vários seletores diferentes, podemos separá-los utilizando vírgula. A vírgula comporta-se como um "OR".

    p, div, .classe, #something, [id^="botao"], ... {...}

Para aplicar regras como um "AND", utilizar seletores juntos.

    p.texto {...}

### Descendentes (espaço)

    div p {...}

Aplica estilo para os `p` dentros de `div` (filhos).

### Filhos Diretos (>)

    div > p {...}

Aplica estilo para o `p` logo após o `div`.

### Irmãos Gerais (~)

    div ~ p {...}

Elemento `p` que está no mesmo nível (identação) de `div`.

### Irmãos Adjacentes (+)

    div + p {...}

Elemento `p` que está no mesmo nível (identação) e ao lado do `div`.

## Dimensionamento e Espaçamento

Para dimensionamento, `width` para largura e `height` para altura.

- `auto`: Calcula-se o suposto valor que a propriedade deveria/deve ter.
- `initial`: Utiliza o valor inicial, o valor padrão.
- `inherit`: Utiliza o valor do elemento pai.

Para espaçamento / posicionamento, `margin` para distanciar de outros elementos, e `padding` para distânciar internamente.

Utilizar `box-sizing` relaciona como que `padding` e `border` sejam limitados pelo `width` e/ou `height`.

- `content-box`: `width` e `height` se referem ao conteúdo do elemento.
- `border-box`: `width` e `height` incluem `border` e `padding` no seu valor.

## Cores

São formas de cores no CSS:

- Pré-definida;
- Palavra-chave "currentcolor";
- Hexadecimal;
- Hexadecimal com transparência;
- RGB;
- RGBA;
- HSL;
  - Hue (0 ~ 360): Grau na roda de cores.
    - 0/360: Vermelho;
    - 120: Verde;
    - 240: Azul;
  - Saturation (0% ~ 100%): Valor percentual.
    - 0: Tom de cinza;
    - 100: Cor total;
  - Lightness (0% ~ 100%): Luminosidade da cor.
    - 0: Preto;
    - 100: Branco;
- HSLA;

## Imagens

`object-fit`: Como o conteúdo de um elemento deve ser ajustado.

- contain: Manter a proporção enquanto se ajusta à caixa;
- cover: Manter a proporção enquanto cobre a caixa;
- fill: Redimensionar para preencher a caixa;
- none: Não redimensionar;
- scale-down: Aplicar `none` ou `contain`, a depender de qual resultar em um menor tamanho.

`object-position`: Como o conteúdo de um elemento deve ser alinhado.

## Fundo dos Elementos

- `background-color`: Cor de fundo do elemento.
- `background-image`: Define um ou mais imagens de fundos para um elemento (são desenhados em camadas);
  - `linear-gradient()`;
  - `url()`;
- `background-size`: Define o tamanho da imagem de plano de fundo do elemento.
  - **contain**: Dimensiona a imagem para o maior possível, sem cortar ou esticar, dentro do seu _container_.
  - **cover**: Dimensiona a imagem para o menor possível, preservando sua proporção, buscando preeencher o seu _container_.
  - **auto**: Dimensiona a imagem no intuito de manter suas proporções intrínsecas.
  - `<length>` / `<percentage>`: largura, altura.
- `background-repeat`: Define como as imagens de fundo serão repetidas.
  - **repeat**: Repete-se o quão necessário para cobrir toda a área. A última imagem é cortada se não couber.
  - **space**: A imagem é repetida o máximo possível sem corte. A primeira e a última imagens são fixadas em ambos os lados do elemento, e o espaço em branco é distribuído uniformemente entre as imagens.
  - **round**: À medida que o espaço permitido aumenta de tamanho, as imagens repetidas se estendem, não deixando lacunas, até que haja espaço para que outra seja adicionada. Quando a próxima imagem é adicionada, todas as atuais são compactadas para permitir espaço.
  - **no-repeat**: Não há repetição.
  - Equivalências:
    - **repeat-x**: repeat no-repeat
    - **repeat-y**: no-repeat repeat
    - **repeat**: repeat repeat
    - **space**: space space
    - **round**: round round
    - **no-repeat**: no-repeat no-repeat
- `background-origin`: Definir a origem do plano de fundo.
  - **border-box**: Origem relativa ao border.
  - **padding-box**: Origem relativa ao padding.
  - **content-box**: Origem relativa ao content.
- Para manipular o posicionamento da imagem de fundo, utiliza-se (ou não) `background-origin` em conjunto com `background-position`.
- `background-attachment`: Define o posicionamento de uma imagem de fundo em situação de scroll.
  - **fixed**: Imagem fixa ao `viewport`, não se move com a rolagem do elemento, nem da janela.
  - **local**: Imagem se movimenta com seu conteúdo, permanece fixa à janela.
  - **scroll**: Imagem fixa em relação ao elemento em si e não rola com seu conteúdo.
- `background-clip`: Definir como a imagem ou cor deve preencher o elemento.
  - **border-box**: O fundo se estende até a borda externa da borda (abaixo, em ordem Z).
  - **padding-box**: O fundo se estende até a borda externa do preenchimento. Nenhum plano de fundo é desenhado abaixo da borda.
  - **content-box**: O plano de fundo é pintado dentro (cortado para) a caixa de conteúdo.
  - **text**: O plano de fundo é pintado dentro (recortado para) o texto de primeiro plano.
- Para definir como as imagens de fundo e cores devem mesclar entre si, utilizar `backgorund-blend-mode`.

Exemplo para múltiplas imagens:

    .teste {
        background-image: url('...A.png'), url('...B.png');
        background-size: 200px 100%, cover;
    }

[Patterns Gallery](https://projects.verou.me/css3patterns/)

## Bordas

- A propriedade `border` é uma abreviação para definir a borda de um elemento.
  - `border-width`: Espessura da borda;
  - `border-style`: Estilo da borda;
  - `border-color`: Cor da borda;
  - Aplicar apenas 1 valor, este será aplicado para todos os lados.
  - Aplicar 2 valores, estes serão aplicados para bordas horizontais e verticais, respectivamente.
  - Aplicar 4 valores, estes serão aplicados para as bordas superior, direita, inferior, esquerda; respectivamente.
- A propriedade `border-image` é uma abreviação para definir uma imagem como borda de um elemento.
  - `border-image-source`: Endereço da imagem (url());
  - `border-image-slice`: Divide a imagem utilizada em 9 seções: 4 cantos + 4 lados + 1 meio;
    - [Ferramenta](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders/Border-image_generator).
  - `border-image-width`: Controla largura/dimensão da imagem utilizada como borda;
  - `border-image-outset`: Define a distância da imagem de borda para sua caixa;
  - `border-image-repeat`: Controla a repetição dos lados da borda (Seções 5, 6, 7, 8);

## Fontes

Catálogo de fontes: [Google Fonts](fonts.google.com)

Na tipografia existe os **tipos genéricos**, conhecidos como **grupos de fontes**:

- **Serif**: Compostas por pequenos traços e prolongamentos que ficam no fim de cada letra (serifas);
  - Ela torna as letras individuais mais distintas e mais fáceis de serem reconhecidas de forma rápida pelo nosso cérebro.
  - Ideal para textos corridos impressos.
- **Sans-Serif**: Fontes sem serifas, não possuem os traços e prolongamentos no fim ads letras;
  - Muito legíveis a pequenos tamanhos e belas e limpas nos tamanhos grandes.
  - Não aconselhadas para textos longos (monótonas e difíceis de seguir).
  - Usadas para textos mais curtos como legendas, créditos, títulos.
- **Display**: Fontes enfeitadas, ampla categoria de fontes, representam símbolos;
  - Usadas para destacar e desempenhar em tamanhos maiores em comparação ao texto.
- **Handwriting**: Fontes manuscritas, se assemelham com a escrita à mão;
  - Boas para uso em produtos físicos como cartazes, revistas, folhetos, etc.
- **Monospace**: Fontes que todos os caracteres ocupam a mesma largura;
  - Grande importância em ambientes de desenvolvimentos e textos em que o alinhamento se faz muito necessário.

A propriedade `font` é uma abreviação para definir a fonte de um elemento.

- `font-style`: Definir o estilo/efeito da fonte;
  - **normal**, **italic**, **oblique**,
- `font-variant`: Definir comportamento relacionado à variante de caixa-alta;
- `font-weight`: Definir a espessura do texto (negrito);
- `font-stretch`: Controlar se o texto deverá ficar mais estreito ou largo;
- `font-size`: Definir o tamanho da fonte;
  - **xx-small**, **x-small**, **small**, **medium**, **large**, **x-large**, **xx-large**, **xxx-large** são palavras chaves para tamanhos absolutos, baseados no tamanho padrão da fonte do usuário (**medium**);
  - **larger**, **smaller** são palavras chaves para tamanho relativo ao tamanho da fonte do elemento pai.
  - _\<length>_;
  - _\<percentage>_;
- `line-height`: Definir a altura de cada linha de texto;
- `font-family`: Definir uma lista priorizada com nomes de famílias de fontes ou genéricas. Utiliza-se aspas para fontes com nomes compostos;

Para fontes personalizadas, pode utilizar-se `@font-face`

    @font-face{
      font-family: Name;
      src: local(), url(...);
    }

    p {
      font-family: Name;
    }

## Textos

Utilizar `text-transform` para definir quais caracteres vão estar em maiúsculo, minúsculo, etc.

A propriedade `text-align` é responsável por alinhar o texto com seu elemento.

Utilizar `text-decoration` para adicionar ou remover linhas decorativas do texto:

- **-line**: underline, overline, line-through, blink;
- **-style**: solid, double, dotted, dashed, wavy;
- **-color**: hexadecimal, rgb, etc;
- **-thickness**: auto, from-font, \<length>, \<percentage>;

A propriedade `text-ident` define o recuo da primeira linha do texto.

Para manipular espaçamento, utilizar `letter-spacing` para caracteres, e `word-spacing` para palavras.

A propriedade `white-space` define o tratamento dos espaços em branco do texto de um elemento.

|             | New lines | Spaces and tabs | Text wrapping | End-of-line spaces          | End-of-line other space separators |
|-------------|----------|----------------|---------------|-----------------------------|-----------------------------------|
| `normal`    | Collapse | Collapse       | Wrap          | Remove                      | Hang                              |
| `nowrap`    | Collapse | Collapse       | No wrap       | Remove                      | Hang                              |
| `pre`       | Preserve | Preserve       | No wrap       | Preserve                    | No wrap                           |
| `pre-wrap`  | Preserve | Preserve       | Wrap          | Hang                        | Hang                              |
| `pre-line`  | Preserve | Collapse       | Wrap          | Remove                      | Hang                              |
| `break-spaces`  | Preserve   | Preserve         | Wrap        | Wrap                        | Wrap                              |

Utilizar `word-wrap: break-word` para permitir que palavras possam ser quebradas em pontos abritários para se manter contida no elemento, junto com `word-break` para definir como quebras de linha devem ser inseridas.

A propriedade `text-overflow` define como o conteúdo oculto é sinalizado aos usuários quando há overflow. Pode ser cortado (**clip**), exibir uma elipse (‘…’, **ellipsis**) ou exibir uma string personalizada (apenas no firefox).

A propriedade `writing-mode` define a orientação do texto (estilo ou outros idiomas).

## Sombras

O `box-shadow` é utilizado para adicionar efeitos de sombra em volta um elemento. Utiliza-se **length** (**offset-x** e **offset-y**), **blur-radius**, **spread-radius**, opcionalmente **inset** e opcionalmente **color**. Para textos, utilizar `text-shadow`.

Pode-se utilizar a combinação de `filter` e `drop-shadow()` para aplicar um efeito de sombra à imagem de entrada.
