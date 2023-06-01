# Unidades de Medida em CSS

## Unidades de Medidas Absolutas

Não estão atrelados a outros valores de referência:

- **cm**;
- **mm**;
- **Q** (quarto de milímetro);
- **in** (polegadas);
- **pc** (paica);
- **pt** (pontos);
- **px** (pixels);

Densidade: Quantidade de pixels que podem ser armazenados em uma região da tela.

Os pixels lógicos são usados para desenhar elementos na tela e são independentes da densidade de pixels do dispositivo. Já os pixels reais são os pontos luminosos que compõem a tela do dispositivo.

## Unidades de Medidas Relativas

São calculadas com base em unidades já conhecidas de outro elemento.

- **%**: A porcentagem é uma unidade de medida que irá utilizar como referência o elemento pai.
- **em** (nome tem origem à uma unidade tipográfica relativa à letra 'M'):
  - Para tamanho da fonte, vai utilizar como referência o valor da propriedade font-size do elemento pai;
  - Para outras propriedades, será em relação ao tamanho da fonte do próprio elemento;
- **rem** (root em): Ao invés de utilizar o elemento pai, utiliza o tamanho da fonte do elemento raíz (tag html) como referência.
- **vw** (viewport width);
- **vh** (viewport height);
- **ex**: Similar à origem do _em_, muda o tamanho em relação à altura do caractere 'x';
- **ch**: Utiliza o caractere '0' como referência;

Viewport é a área visível de uma página web. As unidades de medida _viewport_ vão ser calculadas em relação ao tamanho da área em que o usuário está vendo sua página (1v_ = 1%).
