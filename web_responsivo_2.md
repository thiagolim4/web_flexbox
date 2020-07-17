# Web Responsivo 2

## Menu com Adaptações
- Em determinada resolução, o menu se fecha na lateral (botão com clique que faz o menu lateral aparecer)
- Com Javascript, no clique do botão adiciona uma classe na raiz do documento (tag HTML) do tipo (menu-active), e depois, no clique do botão de fechar menu, remove essa classe
 - E nesse menu, no CSS, usa o ```position: fixed, z-index: 1, top: 0``` para ele sobrepor o conteúdo
 - Usa propriedade ```transition: left 0.3s ease-out```
 - Como no caso geral ele não está visível, posiciona o mesmo para fora da tela, com ```left: -90%```
- Para esconder o menu na versão desktop, usar ```display: none```
- Tampar o conteúdo da lateral (sem ser o menu), criar um elemento que ocupa a página inteira quando o menu está ativo
```CSS
.menu-ativo: after{
  content: "";
  display: block;
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  background: rgba(0,0,0, 0.4);
}
```

## Imagens Responsivas
- Tela de Alta Resolução
- As resoluções no CSS são dadas em DIP (device independent pixel), não necessariamente o correspondente aos pixels físicos: ```dPR = pixel fisico / DIP```
- dPR = Device Pixel Ratio
- Media Query: ```@media (resolution 1dppx)```
- Propriedade srcset:
```HTML
<img src="logo.png"
      srcset="logohd.png 2x, logo.png 1x">
```
- Tag ```<picture></picture>```
- Possibilidade de escrever imagem vetorial na página:
```CSS
<svg>
  <circle cx="50" cy="50" r="40" fill="#F90">
</svg>
```
- Pixels nos botões (geralmente): 50px
