PRACTICA 1

tokens: 

echo "a = 10; b = 5 + a * 2; c = (b - 3) / 2;" | java -cp ".:$ANTLR_JAR" org.antlr.v4.gui.TestRig MiGramatica programa -tokens

salida esperada: 

[@0,0:0='a',<ID>,1:0]
[@1,2:2='=',<'='>,1:2]
[@2,4:5='10',<INT>,1:4]
[@3,6:6=';',<';'>,1:6]
[@4,8:8='b',<ID>,2:0]
[@5,10:10='=',<'='>,2:2]
[@6,12:12='5',<INT>,2:4]
[@7,14:14='+',<'+'>,2:6]
[@8,16:16='a',<ID>,2:8]
[@9,18:18='*',<'*'>,2:10]
[@10,20:20='2',<INT>,2:12]
[@11,21:21=';',<';'>,2:13]
[@12,23:23='c',<ID>,3:0]
[@13,25:25='=',<'='>,3:2]
[@14,27:27='(',<'('>,3:4]
[@15,28:28='b',<ID>,3:5]
[@16,30:30='-',<'-'>,3:7]
[@17,32:32='3',<INT>,3:9]
[@18,33:33=')',<')'>,3:10]
[@19,35:35='/',<'/'>,3:12]
[@20,37:37='2',<INT>,3:14]
[@21,38:38=';',<';'>,3:15]
[@22,40:39='<EOF>',<EOF>,4:0]


Arbol: 

echo "a = 10; b = 5 + a * 2; c = (b - 3) / 2;" | java -cp ".:$ANTLR_JAR" org.antlr.v4.gui.TestRig MiGramatica programa -tree

Salida esperada: 

(programa (expresion a = (expresion 10)) ; (expresion (expresion b = (expresion 5)) + (expresion (expresion a) * (expresion 2))) ; (expresion (expresion c = (expresion ( (expresion (expresion b) - (expresion 3)) ))) / (expresion 2)) ;)



Preguntas del cuestionario: 

1. ¿Cómo se representan los operadores +, -, * y / en los tokens generados?
Respuesta:  
b) Como operadores aritméticos específicos  por que la gramatiica esta echa para realizar operaciones matematicas, ya que el analizador léxico procesa el código y identificará estos símbolos y los marcará como tokens específicos para las operaciones de suma, resta, multiplicación y división.

2. ¿Qué estructura sigue el árbol de análisis sintáctico generado por ANTLR4 para la expresión b = 5 + a * 2;?
Respuesta: 
d) * se evalúa antes que +, organizando el árbol en función de la precedencia  por que  sigue la jerarquia de operadores segun su precedencia, la multiplicacion tiene una prioridad de la suma. 

3. ¿Por qué es importante visualizar los tokens y el árbol de análisis en el proceso de compilación?
Respuesta:  
d) Todas las anteriores por que  esto permite a los desarroladores verificar si la estructura del programa sige las reglas definidad en la gramatica. 



