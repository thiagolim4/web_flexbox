# Web Responsivo 01

## Fonte
- Tamanho da fonte em porcentagem é dado pelo elemento pai
 - body, pai dos pais, em geral tem um padrão de 16px (font-size)
- ```1.2em = 120%``` em ```font-size``` possuem o mesmo significado, pois:
 - Medida tipográfica: ```em = 16px```
 - ```em``` se referencia pelo ```<div></div>```
- ```rem``` se referencia sempre pelo contexto padrão, e não pelo ```<div></div>``` acima
- Imagens responsivas (sem quebrar o elemento quando esticar): ```max-width: 100%```
- Escrever as fontes sempre primeiro em ```pixel```, e depois em ```rem```

## Media Queries
- Evolução de Media Types (```@media print``` define um layout para impressão)
- ```@media ()```:
 - width: largura específica (do navegador)
 - max-width: dessa largura para baixo
 - min-width: dessa largura para cima (mais usada)
 - height: altura específica
 - device-width: pega a resolução nativa da tela inteira (física)
 - device-height: pega a altura nativa
 - orientation: portrait - retrato
 - orientation: landscape - paisagem
- Páginas geralmente são orientadas pela largura, então utiliza-se mais essa medida
- Breakpoints: frameworks famosos
- 320 an up
- Twitter Bootstrap:
 - Large display: 1200px ^
 - Default: 980px ^
 - Portrait tablets: 768px ^
 - Phones to tablets: 767px v
 - Phones: 480px v
- Coloca tag para dispositivo usar a largura nativa:
```<meta name="viewport" content="width=device-width">```
- Firefox possui modo responsivo
- No Chrome, abre o Inspecionar e pode abrir o "mini-celular" para selecionar telas diferentes
 - Pode simular o uso de rede (3G, etc) para verificar a performance da página
 - Editor de media-query no topo esquerdo (três barras horizontais), pode verificar qual media está sendo executada a cada resolução
- Habilita opção de depuração USB no Android, depois vai no Chrome do Desktop e seleciona devTools > Devices, e lá o celular vai aparecer. Clica em Inspect, e pode modificar espelhado no celular.
- Existe um bug conhecido no iOS que faz com que o viewport não se adapte ao rotacionar o dispositivo. Uma gambiarra que evita o bug é colocar o viewport como ```<meta name="viewport" content="width=device-width, initial-scale=1">.```
