# Web Flexbox 1

## Cabeçalho de links
- Menu de navegação: tag ```<nav>``` com título no lado esquerdo (h1), quero posicionar ambos no topo, um na ponta esquerda (título) e o menu na ponta direita
 - ```display: inline-block```, alinha ao lado do outro, permitindo que ```width``` e ```height``` sejam modificadas, mas o espaçamento dos elementos entre si tem que ser feito de modo manual (margins)
 - ```vertical-align: middle```, deixa centralizado
 - No entanto, com esse espaçamento, precisa mexer na distância do menu manualmente
 - ```float:right``` pro menu lateral, ele vai pro canto, mas todos os elementos de baixo sobem para perto do título (h1) na esquerda
 - ```display: inline``` não permite definir nem largura nem altura

## Flexbox
- Quem é o pai (container maior), e coloca: ```display: flex```, e junto ```align-items: center```, que vai alinhar todos os elementos dentro desse flex com center
 - ```justify-content: space-between```: pega o espaço na lateral que sobrou e joga entre os dois elementos
- Menu ```<nav>```: deixar um elemento ao lado do outro
 - ```display: flex```: deixa um link ao lado do outro
 - ```justify-content: space-between```: nesse caso, não faz diferença se não houver espaço em branco dentro da caixa
- Site ```caniuse.com``` permite verificar tecnologias que funcionam nos navegadores

## Footer
- Utiliza % para definir tamanhos dos rodapés, além do flexbox
- Para distribuir o espaço restante entre o meio dos elementos e as laterais (de modo que eles fiquem centralizados no meio), utiliza-se ```justify-content: space-around```
- Display: flex também alinha a altura dos elementos filhos dentro do pai

## Listas lado a lado
- Listas com títulos, se usar display: flex, todos os itens ficarão um ao lado do outro
 - Para mudar isso, deixando ao invés de ao lado, mas embaixo, usa-se ```flex-direction: column```. O padrão geralmente é ```flex-direction: row```
 - Para fazer quebra de colunas (chegou ao fim da página, faz uma quebra), usa ```flex-wrap: wrap```
 - O mesmo funciona caso queira quebrar linha
 - Ou, usando duas proprieades: ```flex-flow: column wrap```

## Espaçamento com flex
- ```justify-content: flex-end```: espaço à esquerda, conteúdo à direita
- ```justify-content: flex-start```: conteúdo à esquerda, espaço à direita
- ```justify-content: center```: conteúdo no meio
- ```justify-content: space-between```: coloca todo o espaço entre os elementos
- ```justify-content: space-around```: coloca o espaço em volta dos elementos (deixa eles no centro)
- Todo o espaçamento e alinhamento vai depender da direção do flex, se for definido "column", inverte tudo

## Layout Grid
- Elementos em grid, para tirar margem somente de alguns boxes das laterais (múltiplos de 4), pode usar:
```CSS
.conteudoPrincipal-cursos-link:nth-child(4n) {
    margin-left: 0;
}
.conteudoPrincipal-cursos-link:nth-child(4n+1) {
    margin-left: 0;
}
```

## Mobile
- Pode usar ```height: auto``` para calcular automaticamente um elemento com listas de itens dentro
- ```@media(max-width: 768px)```

## Flex Order, Grow e Shrink
- É possível mudar as ordens dos elementos dentro do pai:
 - Por padrão, todos são ```order: 0```
 - ```order: -1;```, o elemento com essa ordem vai vir antes de todos os outros
 - ```order: 1;```, vai ficar por último
- ```flex-grow: 1``` cresce para o restante que sobrar do elemento. Se tiver dois elementos, e utilizar essa propriedade pra cada um, cada elemento ocupa metade do container (50%)
- ```flex:grow 0``` é o padrão
 - Essa propriedade funciona dividindo o espaço vazio, se colocar grow 3 pra um e grow 1 pra outro, o navegador divide o espaço em 4 e distribui isso pra eles
- ```flex-shrink:``` conforme diminui a tela, quero que certos elementos diminuam mais que outros
 - ```flex-shrink: 0```: não diminui conforme tela diminui
 - ```flex-shrink: 1```: padrão
 - ```flex-shrink: 2```: diminui 2x mais que os outros
- Pode juntar as duas propriedades, a primeira é grow, a segunda é shrink, como em: ```flex: 1 1```
- ```flex-basis: 25%``` define uma largura (ou altura, se estiver com o fluxo de column) para os elementos, é como se fosse um width

## Propriedades Flex Container e Item
- Container:
```
display: flex
flex-direction
justify-content
flex-wrap
flex-flow
align-items
align-content
```

- Flex item:
```
order
flex-grow
flex-shrink
flex-basis
flex
align-self
```
