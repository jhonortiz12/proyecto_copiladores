Practica 3: 

tokens: 

echo "for (i = 0; i < 10; i = i + 1) { x = x + i; }" | java -cp ".:$ANTLR_JAR" org.antlr.v4.gui.TestRig MiGramatica programa -tokens

salida esperada: 

[@0,0:2='for',<'for'>,1:0]
[@1,4:4='(',<'('>,1:4]
[@2,5:5='i',<ID>,1:5]
[@3,7:7='=',<'='>,1:7]
[@4,9:9='0',<INT>,1:9]
[@5,10:10=';',<';'>,1:10]
[@6,12:12='i',<ID>,1:12]
[@7,14:14='<',<'<'>,1:14]
[@8,16:17='10',<INT>,1:16]
[@9,18:18=';',<';'>,1:18]
[@10,20:20='i',<ID>,1:20]
[@11,22:22='=',<'='>,1:22]
[@12,24:24='i',<ID>,1:24]
[@13,26:26='+',<'+'>,1:26]
[@14,28:28='1',<INT>,1:28]
[@15,29:29=')',<')'>,1:29]
[@16,31:31='{',<'{'>,1:31]
[@17,33:33='x',<ID>,1:33]
[@18,35:35='=',<'='>,1:35]
[@19,37:37='x',<ID>,1:37]
[@20,39:39='+',<'+'>,1:39]
[@21,41:41='i',<ID>,1:41]
[@22,42:42=';',<';'>,1:42]
[@23,44:44='}',<'}'>,1:44]
[@24,46:45='<EOF>',<EOF>,2:0]


arbol: 

echo "for (i = 0; i < 10; i = i + 1) { x = x + i; }" | java -cp ".:$ANTLR_JAR" org.antlr.v4.gui.TestRig MiGramatica programa -tree

salida esperada: 

(programa (sentencia (forStmt for ( (inicializacion i = (expresion 0)) ; (condicion i < 10) ; (actualizacion i = (expresion (expresion i) + (expresion 1))) ) { (sentencia (asignacion x = (expresion (expresion x) + (expresion i)) ;)) })) <EOF>)


Preguntas del Cuestionario:

1. ¿Qué tokens se generan para la estructura for (i = 0; i < 10; i = i + 1) { x = x + i; }?
Respuesta: 
a) FOR, (, ID, =, INT, ;, ID, <, INT, ;, ID, =, ID, +, INT, ), {, ID, =, ID, +, ID, } por que la gramatica incluye for, por lo que los tokens generados corresponden a la estructura definida. 

2. ¿Cómo se organiza la estructura for en el árbol de análisis sintáctico?
Respuesta: 
for es el nodo raíz y tiene como hijos la inicialización, la condición, la actualizacion y el cuerpo del bucle

3. ¿Qué ocurre si en la gramática se omiten los ; en la estructura for?
Respuesta: 
a) Se genera un error de sintaxis por que  "; "  son obligatorios  en la gramatica definida