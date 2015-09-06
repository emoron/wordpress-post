---
ID: 117
post_title: Agentes basados en conocimiento
author: admin
post_date: 2015-09-05 18:05:53
post_excerpt: ""
layout: post
permalink: >
  http://188.166.92.76/agentes-basados-en-conocimiento/
published: true
---
<span style="font-weight: 400;">El componente principal de un agente basado en conocimiento es su base de conocimiento. Usualmente una BC es un conjunto de sentencias, similares a las sentencias en inglés, u otros lenguajes naturales. Cada sentencia se presenta en un lenguaje denominado, lenguaje de representación de conocimiento. Y se representa alguna aserción acerca del mundo, debe haber un mecanismo para añadir nuevas sentencias a la base de conocimiento, y uno para preguntar qué se sabe en la base de conocimiento. Los nombres estándar para estas dos tareas son </span><i><span style="font-weight: 400;">Decir y Preguntar</span></i><span style="font-weight: 400;">, respectivamente. Ambas tareas requieren realizar inferencia, es decir, derivar nuevas sentencias a partir de las antiguas.</span>

&nbsp;

<span style="font-weight: 400;">funci</span><span style="font-weight: 400;">ó</span><span style="font-weight: 400;">n AGENTE</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">BC</span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">percepci</span><span style="font-weight: 400;">ó</span><span style="font-weight: 400;">n</span><span style="font-weight: 400;">)</span><span style="font-weight: 400;"> devuelve una acci</span><span style="font-weight: 400;">ón</span>

<span style="font-weight: 400;">  variables estáticas</span><span style="font-weight: 400;">:</span><span style="font-weight: 400;"> BC</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;"> una </span><span style="font-weight: 400;">base</span><span style="font-weight: 400;"> de conocimiento</span>

<span style="font-weight: 400;">  t</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;"> un contador</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;"> inicializado a </span><span style="font-weight: 400;">0</span><span style="font-weight: 400;"> que indica el tiempo</span>

<span style="font-weight: 400;">  DECIR</span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">BC</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">CONSTRUIR</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">SENTENCIA</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">DE</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">PERCEPCIÓN</span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">percepci</span><span style="font-weight: 400;">ó</span><span style="font-weight: 400;">n</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;"> t</span><span style="font-weight: 400;">))</span>

<span style="font-weight: 400;">  acci</span><span style="font-weight: 400;">ó</span><span style="font-weight: 400;">n </span><span style="font-weight: 400;">&lt;-</span><span style="font-weight: 400;"> PREGUNTAR</span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">BC</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">PEDIR</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">Acci</span><span style="font-weight: 400;">ó</span><span style="font-weight: 400;">n</span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">t</span><span style="font-weight: 400;">))</span>

<span style="font-weight: 400;">  DECIR</span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">BC</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">CONSTRUIR</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">SENTENCIA</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">DE</span><span style="font-weight: 400;">-</span><span style="font-weight: 400;">ACCIÓN</span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">acci</span><span style="font-weight: 400;">ó</span><span style="font-weight: 400;">n</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">t</span><span style="font-weight: 400;">))</span>

<span style="font-weight: 400;">  t </span><span style="font-weight: 400;">&lt;-</span><span style="font-weight: 400;"> t </span><span style="font-weight: 400;">+</span><span style="font-weight: 400;"> 1</span>

<span style="font-weight: 400;"> devolver acci</span><span style="font-weight: 400;">ón</span>

&nbsp;
<h2><b>Lógica</b></h2>
<h3><b>Conceptos Fundamentales</b></h3>
<span style="font-weight: 400;">Una lógica nos permite definir la semántica del lenguaje. Si lo relacionamos con el lenguaje hablado, la semántica trata "el significado" de las sentencias. En lógica, esta definición bastante más precisa</span>
<h3><b>Lógica Proposicional</b></h3>
<span style="font-weight: 400;">La sintaxis de la lógica proposicional nos define las sentencias que se pueden construir. Las sentencias atómicas (es decir, los elementos sintácticos indivisibles) se componen de un único</span><b> símbolo proposicional.</b><span style="font-weight: 400;"> Cada uno de estos símbolos representa una proposición que puede ser verdadera o falsa. Utilizaremos letras mayúsculas para estos símbolos: P, Q, R y siguientes. Los nombres de los símbolos suelen ser arbitrarios pero a menudo se escogen de manera que tengan algún sentido mnemotécnico para el lector.</span>

&nbsp;

<span style="font-weight: 400;">Las sentencias complejas se construyen a partir de sentencias más simples mediante el uso de la conectivas lógicas, que son las siguientes:</span>

<span style="font-weight: 400;"> (no). Una sentencia como $</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">1,3$</span><span style="font-weight: 400;"> se denomina </span><b>negación</b><span style="font-weight: 400;"> de $</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">1,3$</span><span style="font-weight: 400;">. Un </span><b>Literal</b><span style="font-weight: 400;"> puede ser una sentencia atómica ( un </span><b>literal positivo </b><span style="font-weight: 400;">)  o una sentencia atómica negada (un</span><b> literal negativo</b><span style="font-weight: 400;">)</span>

<span style="font-weight: 400;">(y) Una sentencia que tenga como conectiva principal </span><span style="font-weight: 400;">, como es </span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">1,3</span> <span style="font-weight: 400;">H</span><span style="font-weight: 400;">3,1</span><span style="font-weight: 400;">)</span><span style="font-weight: 400;">, se denomina </span><b>conjunción</b><span style="font-weight: 400;">. sus componentes son los </span><b>conjuntores</b><span style="font-weight: 400;">. </span>

&nbsp;

<span style="font-weight: 400;">(o). Una sentencia que utiliza la conectiva </span><span style="font-weight: 400;">, como es </span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">1,3</span> <span style="font-weight: 400;">H</span><span style="font-weight: 400;">3,1</span><span style="font-weight: 400;">)</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">2,2</span><span style="font-weight: 400;">, es una </span><b>disyunción</b><span style="font-weight: 400;"> de los </span><b>disyuntores</b> <span style="font-weight: 400;">(</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">1,3</span><span style="font-weight: 400;">H</span><span style="font-weight: 400;">3,1</span><span style="font-weight: 400;">)</span><span style="font-weight: 400;"> y </span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">2,2</span>

<span style="font-weight: 400;">(implica). Una sentencia como </span><span style="font-weight: 400;">(</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">1,3</span><span style="font-weight: 400;">H</span><span style="font-weight: 400;">3,1</span><span style="font-weight: 400;">)</span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">2,2</span><span style="font-weight: 400;"> se denomina </span><b>implicación </b><span style="font-weight: 400;">(o condicional). Su premisa es </span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">1,3</span><span style="font-weight: 400;">H</span><span style="font-weight: 400;">3,1</span><span style="font-weight: 400;">y su conclusión o consecuente es </span><span style="font-weight: 400;">W</span><span style="font-weight: 400;">2,2</span><span style="font-weight: 400;">. Las implicaciones se conocen como </span><b>reglas</b><span style="font-weight: 400;"> o afirmaciones </span><b>si-entonces</b><span style="font-weight: 400;">. Algunas veces, en otros libros el símbolo de la implicación se representa mediante </span><span style="font-weight: 400;">o </span><span style="font-weight: 400;">.</span>

&nbsp;

<span style="font-weight: 400;">Obsérvese que para cada sentencia construida a partir de conectivas binarias deberá ir encerrada entre paréntesis. Para asegurar que la gramática no sea ambigua. El orden de precedencia en la lógica proposicional (de mayor a menor) es: </span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">,</span><span style="font-weight: 400;">. Así en la sentencia</span>

<span style="font-weight: 400;">P</span><span style="font-weight: 400;">Q</span><span style="font-weight: 400;">R</span><span style="font-weight: 400;">S</span>

<span style="font-weight: 400;">es equivalente a la sentencia</span>

<span style="font-weight: 400;">((</span><span style="font-weight: 400;">P)</span><span style="font-weight: 400;">(Q</span><span style="font-weight: 400;">R))</span><span style="font-weight: 400;">S</span>

<span style="font-weight: 400;">La precedencia entre la conectivas no resuelve la ambiguidad en sentencias como </span><span style="font-weight: 400;">A</span><span style="font-weight: 400;">B</span><span style="font-weight: 400;">C</span><span style="font-weight: 400;">, que se podría leer como </span><span style="font-weight: 400;">((A</span><span style="font-weight: 400;">B)</span><span style="font-weight: 400;">C)</span><span style="font-weight: 400;">o como </span><span style="font-weight: 400;">(A</span><span style="font-weight: 400;">(B</span><span style="font-weight: 400;">C)</span><span style="font-weight: 400;">.</span>

&nbsp;

<b>Semántica</b><span style="font-weight: 400;">.</span>

&nbsp;