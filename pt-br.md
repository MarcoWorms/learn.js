# Learn.js

🇧🇷 Essa é a versão português do Aprenda.js! Continue para baixo para ver o conteúdo :D  
🇬🇧 [Click here to move to the english verion: Learn.js](./README.md)  
🇨🇳 [点此查看中文版本：Learn.js](./zh-cn.md)  

<details>
  <summary>Clique aqui para abrir a tabela de conteúdo</summary>

</details>

## Usando

Você pode copiar qualquer código desse guia e colar ele no console de desenvolvedor do seu navegador para ver o output. Para abrir o console de desenvolvedor abra seu navegador de internet padrão > aperte f12 > console. É recomendado ler esse guia com o console aberto para que você possa ir brincando com os pedaços de código, isso vai te ajudar bastante no processo de aprendizado!

<details>
  <summary>Clique aqui para ver uma imagem de exemplo de como o console se parece</summary>
  
  ![image](https://user-images.githubusercontent.com/7863230/118431315-692b2f00-b6ac-11eb-9aa5-ebcf5185e40a.png)
</details>

# Tipos e estruturas de dados

Programar sempre envolve alguma forma de transformação de dados. Você pode guardar, contar, aplicar operações matemáticas, engatilhar fluxos em outros fluxos, mas o mecanismo básico de linguagens de programação é sempre sobre ler dados e a partir deles executar algum tipo de lógica

No javascript temos os seguintes tipos e estruturas de dados

## Números (Number)

No javascript todos os números são do tipo "Number" e não existe diferença de tipos entre números inteiros e decimais

```js
1
81072865287.331
19.35

// isso é um comentário, tudo depois do // na mesma linha será ignorado!
```

## Operadores Matemáticos

Nós ja podemos começar a escrever alguns programas bem simples se soubermos sobre números e operadores. Vamos escrever alguns:

```js
2 + 4 // 6
(2 * 4) // 8
// Parenthesis works as expected in math
2 / 4 // 0.5
2 ** 4 // 16 (2 * 2 * 2 * 2)
5 % 4 // 1 (the remainder of the integer division)
```

Cada uma das 5 linhas acima pode ser vista como 5 programas bem pequenos. Cada um deles é bem limitado mas eles propositalmente transformam algum dado em outro. No momento esses programas não são usáveis por outras pessoas ja que uma simples calculadora faz muito mais do que fizemos no momento e com muito mais acessibilidade, mas o propósito de chamarmos cada linha de programa é consolidar a visão que um programa é apenas uma transformação de dados. Conforme aprendemos estruturas mais complexas de dados nós atingiremos habilidades de resolução de problemas que nenhuma calculadora chega perto de resolver!

## Palavras (String)

Uma String é uma sequência de caractéres alfanuméricos. Strings são delimitadas por ', ", ou `

' ou " são usados para strings que não tem quebra de linha (você pode adicionar uma quebra de linha nelas com o cacter especial \n)

```js
'pan'
"queca"
'pan queca'
"panqueca queca"
```

Ambas as frases abaixo são as mesmas: ` é uma nova versão do ' e " que permite Strings terem quebras de linha e também nos premite mais pra frente colocar variáveis dentro do texto

```js
"eu estou\ncom fome"

`eu estou
com fome`
```

## Booleans e Comparações

Pra alguns muitas coisas na vida são relativas, mas não para as Booleans. Uma Boolean é um valor que é ou verdadeiro ou falso

```js
true // verdadeiro
false // falso
```

Você pode inverter Booleans com o operador !

```js
!true // false
!false // true
```

Você pode produzir valores do tipo booleano fazendo comparações usando esses operadores:

```js
1 === 1 // true (igual)
1 !== 1 // false (não igual)

4 > 3 // true (maior que)
3 >= 3 // true (maior que ou igual)

4 <= 3 // false (menor que)
4 < 3 // false (menor que ou igual)
```

Booleans também são usadas para fazer comparações lógicas

```js
true && true // true
true && false // false (em qualquer ordem)
false && false // false

true || true // true
true || false // true (em qualquer ordem)
false || false // false

```

## Valores vazios e convertendo valores para Booleans

Nós podemos dizer que um valor na verdade não é nada e uma das piores partes do javascript é que temos 2 formas de dizer isso:

```js
undefined
null
```

Qual é a diferença? Grosseiramente o "undefined" aparece quando um valor nunca foi declarado pra começo de conversa. "null" é um valor que normalmente foi colocado ali por alguém que quis dizer que ali está vazio no momento (pode vir a ser preenchido no futuro ou não). Você não deve se preocupar muito com ambos agora, apenas saiba que eles existem e agem como "false" quando usados em comparações booleanas. Agora que você sabe disso, vamos encerrar esta seção com uma tabela de referência sobre quais valores são considerados "verdadeiros" ou "falsos" quando usados como booleanos:

Os valores a seguir são sempre falsos, o que significa que, quando usados como booleanos, são considerados falsos: 

```js
false
0 // (zero)
'' // (string vazia)
""
``
null
undefined
NaN // Not a Number, aparece quando você faz contas com um tipo que não é um number
```

TODOS os outros valores sempre serão verdadeiros, o que significa que serão considerados verdadeiros em operações booleanas.
