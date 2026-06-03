<h1 align="center">Problemario de Métodos Numéricos</h1>

<h3>Realizado por:</h3>

<ul>
    <li>Jose Antonio Guerrero Lazcano</li>
</ul>

<hr>

<h1 id="indice" align="center">ÍNDICE</h1>

<ul>

<li><a href="#competencia-asignatura">Competencia de la Asignatura</a></li>

<li>
<a href="#errores-numericos"> TEMA 1: Errores Numéricos</a>

<ul>
<li><a href="#error-redondeo">Error de redondeo</a></li>
<li><a href="#perdida-precision">Pérdida de precisión</a></li>
<li><a href="#comparacion-directa">Comparación directa</a></li>
<li><a href="#cancelacion-resta">Cancelación de resta</a></li>
<li><a href="#desbordamiento">Desbordamiento</a></li>
<li><a href="#conversion-estrecha">Conversión estrecha</a></li>
<li><a href="#error-absoluto">Error absoluto</a></li>
<li><a href="#error-relativo">Error relativo</a></li>
</ul>

</li>

<li>
<a href="#sistemas-ecuaciones"> TEMA 2: Sistemas de Ecuaciones</a>

<ul>
<li><a href="#eliminacion-gaussiana">Eliminación Gaussiana</a></li>
<li><a href="#gauss-jordan">Gauss-Jordan</a></li>
<li><a href="#gauss-seidel">Gauss-Seidel</a></li>
<li><a href="#jacobi">Método de Jacobi</a></li>
</ul>

</li>
<h2 id="competencia-asignatura" align="center">
Competencia de la Asignatura
</h2>

<p>
Aplica los métodos numéricos para resolver problemas científicos y de ingeniería utilizando la computadora.
</p>


<hr>


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>

<hr>

<h1 id="errores-numericos" align="center">
Errores Numéricos
</h1>

<h2 id="error-redondeo" align="center">
1. Error de redondeo
</h2>

<h3>¿Qué es?</h3>

<p>
El error de redondeo ocurre cuando un número decimal no puede representarse exactamente dentro de la memoria de la computadora, por lo que el sistema realiza una aproximación. Este tipo de error es muy común en métodos numéricos debido a que las computadoras trabajan con una cantidad limitada de cifras significativas.
</p>

<p>
Por ejemplo:
</p>

<pre>
0.1 + 0.2 != 0.3
</pre>

<p>
Esto sucede porque algunos números decimales no pueden almacenarse de manera exacta en formato binario.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Error absoluto</h4>

<pre>
Ea = |Valor real - Valor aproximado|
</pre>

<h4>Error relativo</h4>

<pre>
Er = |Valor real - Valor aproximado| / |Valor real|
</pre>

<h4>Error porcentual</h4>

<pre>
Ep = Er × 100
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite realizar cálculos rápidos en computadoras.</li>
<li>Facilita el manejo de números muy grandes o muy pequeños.</li>
<li>Reduce el consumo de memoria.</li>
<li>Hace posible la implementación de métodos numéricos complejos.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede generar resultados inexactos.</li>
<li>Los errores pueden acumularse durante múltiples operaciones.</li>
<li>En cálculos científicos puede afectar significativamente la precisión.</li>
<li>Puede provocar diferencias entre resultados teóricos y computacionales.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>
<li><b>Ingeniería en Sistemas Computacionales:</b> Desarrollo de software científico, simulación numérica e inteligencia artificial.</li>
<li><b>Ingeniería Civil:</b> Cálculo estructural y análisis de deformaciones.</li>
<li><b>Ingeniería Mecánica:</b> Simulación de movimiento y fuerzas.</li>
<li><b>Ingeniería Electrónica:</b> Procesamiento digital de señales y sistemas embebidos.</li>
<li><b>Ingeniería Industrial:</b> Modelado matemático y optimización.</li>
</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir a = 0.1
    Definir b = 0.2

    resultado = a + b

    Mostrar "Resultado: " + resultado

    Si resultado == 0.3 Entonces

        Mostrar "Es igual a 0.3"

    Sino

        Mostrar "No es exactamente igual a 0.3"

    FinSi

Fin
</pre>

<h3>Ejemplo en Java</h3>

```java
public class ErrorRedondeo {

    public static void main(String[] args) {

        double a = 0.1;
        double b = 0.2;

        double resultado = a + b;

        System.out.println("Resultado: " + resultado);

        if(resultado == 0.3){
            System.out.println("Es igual a 0.3");
        } else {
            System.out.println("No es exactamente igual a 0.3");
        }
    }
}
```
<h2> compilacion del codigo </h2>

<img width="457" height="177" alt="Captura de pantalla 2026-05-26 113252" src="https://github.com/user-attachments/assets/6aa0da87-7d8b-4c09-86bd-8fc9355e54d0" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>

<hr>

<h2 id="perdida-precision" align="center">
2. Pérdida de precisión
</h2>

<h3>¿Qué es?</h3>

<p>
La pérdida de precisión ocurre cuando una computadora no puede representar todos los dígitos exactos de un número durante una operación matemática. Esto provoca que algunas cifras significativas se pierdan o se modifiquen, generando resultados aproximados.
</p>

<p>
Este problema es muy común en métodos numéricos, especialmente cuando se realizan operaciones con números muy grandes, muy pequeños o con muchos decimales.
</p>

<p>
Por ejemplo:
</p>

<pre>
1000000000.0 + 0.0000001
</pre>

<p>
La computadora puede ignorar el número pequeño debido a la limitada precisión del tipo de dato.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Error absoluto</h4>

<pre>
Ea = |Valor real - Valor aproximado|
</pre>

<h4>Error relativo</h4>

<pre>
Er = |Valor real - Valor aproximado| / |Valor real|
</pre>

<h4>Error porcentual</h4>

<pre>
Ep = Er × 100
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite realizar cálculos complejos rápidamente.</li>
<li>Reduce el tiempo de procesamiento en computadoras.</li>
<li>Facilita el manejo de grandes cantidades de datos.</li>
<li>Hace posible el uso de simulaciones numéricas.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede producir resultados inexactos.</li>
<li>Se pierden cifras significativas durante operaciones matemáticas.</li>
<li>Los errores pueden acumularse en cálculos repetitivos.</li>
<li>Puede afectar la precisión en cálculos científicos e ingenieriles.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Desarrollo de software científico y simulaciones.</li>

<li><b>Ingeniería Electrónica:</b> Procesamiento digital de señales y sistemas embebidos.</li>

<li><b>Ingeniería Civil:</b> Modelos matemáticos y cálculos estructurales.</li>

<li><b>Ingeniería Mecánica:</b> Simulación de fuerzas y movimientos.</li>

<li><b>Ingeniería Industrial:</b> Optimización y análisis estadístico.</li>

</ul>

<hr>

<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir numeroGrande = 1000000000.0
    Definir numeroPequeno = 0.0000001

    resultado = numeroGrande + numeroPequeno

    Mostrar "Resultado: " + resultado

Fin
</pre>

<h3>Ejemplo en Java</h3>

```java
public class PerdidaPrecision {

    public static void main(String[] args) {

        double numeroGrande = 1000000000.0;
        double numeroPequeno = 0.0000001;

        double resultado = numeroGrande + numeroPequeno;

        System.out.println("Resultado: " + resultado);
    }
}
```
<h3> compilación del codigo </h3>

<img width="502" height="181" alt="Captura de pantalla 2026-05-26 113924" src="https://github.com/user-attachments/assets/0f7ae3b5-ad0f-4190-8afa-f6e936376129" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="comparacion-directa" align="center">
3. Comparación directa
</h2>

<h3>¿Qué es?</h3>

<p>
La comparación directa es un problema numérico que ocurre cuando se comparan números decimales utilizando el operador de igualdad <b>==</b>. Debido a los errores de representación y redondeo en las computadoras, dos números que aparentemente deberían ser iguales pueden tener pequeñas diferencias internas.
</p>

<p>
Esto provoca que una comparación directa falle aunque los valores matemáticamente sean equivalentes.
</p>

<p>
Por ejemplo:
</p>

<pre>
0.1 + 0.2 == 0.3
</pre>

<p>
El resultado será falso debido a la representación binaria de los números decimales.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Comparación con tolerancia</h4>

<pre>
|a - b| &lt; ε
</pre>

<p>
Donde:
</p>

<ul>
<li><b>a</b> = valor calculado</li>
<li><b>b</b> = valor esperado</li>
<li><b>ε</b> = tolerancia permitida</li>
</ul>

<h4>Error absoluto</h4>

<pre>
Ea = |Valor real - Valor aproximado|
</pre>

<h4>Error relativo</h4>

<pre>
Er = |Valor real - Valor aproximado| / |Valor real|
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite validar resultados numéricos.</li>
<li>Facilita la toma de decisiones en programas.</li>
<li>Ayuda a verificar condiciones lógicas.</li>
<li>Es sencilla de implementar.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Las comparaciones exactas pueden fallar con números decimales.</li>
<li>Puede generar errores lógicos en programas.</li>
<li>Los resultados dependen de la precisión del tipo de dato.</li>
<li>En cálculos científicos puede producir decisiones incorrectas.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Desarrollo de software, simulaciones y algoritmos numéricos.</li>

<li><b>Ingeniería Electrónica:</b> Procesamiento de señales digitales y sistemas de control.</li>

<li><b>Ingeniería Mecánica:</b> Simulaciones físicas y cálculos computacionales.</li>

<li><b>Ingeniería Civil:</b> Verificación de modelos matemáticos y análisis estructural.</li>

<li><b>Ingeniería Industrial:</b> Sistemas de optimización y análisis estadístico.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir a = 0.1 + 0.2
    Definir b = 0.3

    Mostrar "Valor de a: " + a
    Mostrar "Valor de b: " + b

    Si a == b Entonces

        Mostrar "Son iguales"

    Sino

        Mostrar "No son exactamente iguales"

    FinSi

    // Comparación usando tolerancia

    Definir epsilon = 0.000001

    Si valorAbsoluto(a - b) < epsilon Entonces

        Mostrar "Son aproximadamente iguales"

    FinSi

Fin
</pre>

<h3>Ejemplo en Java</h3>

```java
public class ComparacionDirecta {

    public static void main(String[] args) {

        double a = 0.1 + 0.2;
        double b = 0.3;

        System.out.println("Valor de a: " + a);
        System.out.println("Valor de b: " + b);

        if(a == b){
            System.out.println("Son iguales");
        } else {
            System.out.println("No son exactamente iguales");
        }

        // Comparación correcta usando tolerancia
        double epsilon = 0.000001;

        if(Math.abs(a - b) < epsilon){
            System.out.println("Son aproximadamente iguales");
        }
    }
}
```
<h3>Compilación de codigo</h3>
<img width="382" height="163" alt="Captura de pantalla 2026-05-26 114217" src="https://github.com/user-attachments/assets/bb2d071b-4964-4e76-a681-4014bb6a592f" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="cancelacion-resta" align="center">
4. Cancelación de resta
</h2>

<h3>¿Qué es?</h3>

<p>
La cancelación de resta es un problema numérico que ocurre cuando se restan dos números muy cercanos entre sí. Debido a que ambos valores son casi iguales, gran parte de sus cifras significativas se cancelan, provocando una pérdida importante de precisión en el resultado.
</p>

<p>
Este error es muy común en métodos numéricos y cálculos científicos donde se trabajan diferencias pequeñas entre valores grandes o similares.
</p>

<p>
Por ejemplo:
</p>

<pre>
1000.0001 - 1000.0000
</pre>

<p>
Aunque el resultado esperado es pequeño, la computadora puede perder precisión durante la operación.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Cancelación de resta</h4>

<pre>
Resultado = a - b
</pre>

<p>
Cuando:
</p>

<pre>
a ≈ b
</pre>

<p>
la precisión disminuye considerablemente.
</p>

<h4>Error absoluto</h4>

<pre>
Ea = |Valor real - Valor aproximado|
</pre>

<h4>Error relativo</h4>

<pre>
Er = |Valor real - Valor aproximado| / |Valor real|
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite calcular diferencias entre valores.</li>
<li>Es una operación fundamental en métodos numéricos.</li>
<li>Se utiliza en simulaciones y modelos matemáticos.</li>
<li>Facilita cálculos científicos complejos.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede provocar pérdida de cifras significativas.</li>
<li>Reduce la precisión de los resultados.</li>
<li>Los errores pueden propagarse en operaciones posteriores.</li>
<li>Afecta cálculos científicos y de ingeniería.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Algoritmos numéricos y simulaciones computacionales.</li>

<li><b>Ingeniería Electrónica:</b> Procesamiento digital de señales.</li>

<li><b>Ingeniería Mecánica:</b> Simulación de movimiento y fuerzas.</li>

<li><b>Ingeniería Civil:</b> Cálculos estructurales y análisis matemático.</li>

<li><b>Ingeniería Industrial:</b> Modelado matemático y optimización.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir a = 1000.0001
    Definir b = 1000.0000

    resultado = a - b

    Mostrar "Resultado de la resta: " + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class CancelacionResta {

    public static void main(String[] args) {

        double a = 1000.0001;
        double b = 1000.0000;

        double resultado = a - b;

        System.out.println("Resultado de la resta: " + resultado);
    }
}
```
<h3>Compilación de codigo</h3>
<img width="535" height="242" alt="Captura de pantalla 2026-05-26 114258" src="https://github.com/user-attachments/assets/da1fb25f-84ce-4a5d-9af1-5f955785d7e4" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="desbordamiento" align="center">
5. Desbordamiento
</h2>

<h3>¿Qué es?</h3>

<p>
El desbordamiento ocurre cuando un cálculo produce un número mayor o menor que el rango máximo que puede almacenar un tipo de dato en la computadora. Cuando esto sucede, el resultado puede volverse incorrecto, infinito o incluso provocar errores en el programa.
</p>

<p>
Este problema es muy común en operaciones matemáticas con números extremadamente grandes o pequeños.
</p>

<p>
Por ejemplo:
</p>

<pre>
Integer.MAX_VALUE + 1
</pre>

<p>
El resultado excede la capacidad máxima del tipo entero y provoca un desbordamiento.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Condición de desbordamiento</h4>

<pre>
Resultado > Valor máximo permitido
</pre>

<p>
o
</p>

<pre>
Resultado < Valor mínimo permitido
</pre>

<h4>Error absoluto</h4>

<pre>
Ea = |Valor real - Valor aproximado|
</pre>

<h4>Error relativo</h4>

<pre>
Er = |Valor real - Valor aproximado| / |Valor real|
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite detectar límites de almacenamiento en memoria.</li>
<li>Ayuda a optimizar el uso de tipos de datos.</li>
<li>Facilita el control de errores numéricos.</li>
<li>Es útil para validar operaciones matemáticas.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Produce resultados incorrectos.</li>
<li>Puede provocar fallos en programas.</li>
<li>Genera pérdida de información numérica.</li>
<li>Afecta cálculos científicos y financieros.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Programación, manejo de memoria y algoritmos.</li>

<li><b>Ingeniería Electrónica:</b> Sistemas embebidos y procesamiento digital.</li>

<li><b>Ingeniería Mecánica:</b> Simulación de cálculos físicos complejos.</li>

<li><b>Ingeniería Industrial:</b> Análisis de datos y optimización.</li>

<li><b>Ingeniería Civil:</b> Modelos matemáticos y simulaciones estructurales.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir numeroMaximo = valorMáximoEntero

    Mostrar "Valor máximo del entero: " + numeroMaximo

    resultado = numeroMaximo + 1

    Mostrar "Resultado después del desbordamiento: " + resultado

Fin
</pre>

<h3>Ejemplo en Java</h3>

```java
public class Desbordamiento {

    public static void main(String[] args) {

        int numeroMaximo = Integer.MAX_VALUE;

        System.out.println("Valor máximo del entero: " + numeroMaximo);

        int resultado = numeroMaximo + 1;

        System.out.println("Resultado después del desbordamiento: " + resultado);
    }
}
```
<h3>Compilación de codigo</h3>
<img width="566" height="190" alt="Captura de pantalla 2026-05-26 114700" src="https://github.com/user-attachments/assets/e444b0a6-2d3f-4a88-9bb9-3411d0c96fb7" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="conversion-estrecha" align="center">
6. Conversión estrecha
</h2>

<h3>¿Qué es?</h3>

<p>
La conversión estrecha ocurre cuando un dato de un tipo numérico grande se convierte a otro tipo con menor capacidad de almacenamiento. Durante esta conversión pueden perderse datos, decimales o incluso cambiar completamente el valor original.
</p>

<p>
Este problema es muy común en programación y métodos numéricos cuando se convierten valores de tipo <b>double</b> a <b>int</b>, o de <b>long</b> a <b>short</b>.
</p>

<p>
Por ejemplo:
</p>

<pre>
double numero = 9.99;
int valor = (int) numero;
</pre>

<p>
El valor decimal se pierde durante la conversión.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Conversión estrecha</h4>

<pre>
TipoPequeño = (TipoPequeño) TipoGrande
</pre>

<h4>Error absoluto</h4>

<pre>
Ea = |Valor real - Valor aproximado|
</pre>

<h4>Error relativo</h4>

<pre>
Er = |Valor real - Valor aproximado| / |Valor real|
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Reduce el consumo de memoria.</li>
<li>Facilita la compatibilidad entre tipos de datos.</li>
<li>Puede mejorar el rendimiento en algunos sistemas.</li>
<li>Permite adaptar datos a ciertos algoritmos.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede provocar pérdida de información.</li>
<li>Los valores decimales pueden eliminarse.</li>
<li>Puede generar errores numéricos.</li>
<li>En cálculos científicos afecta la precisión.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Programación, bases de datos y algoritmos.</li>

<li><b>Ingeniería Electrónica:</b> Sistemas embebidos y microcontroladores.</li>

<li><b>Ingeniería Industrial:</b> Procesamiento de datos y automatización.</li>

<li><b>Ingeniería Mecánica:</b> Simulación computacional y cálculos numéricos.</li>

<li><b>Ingeniería Civil:</b> Modelado matemático y software de simulación.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir numeroDecimal = 9.99

    numeroEntero = convertirEntero(numeroDecimal)

    Mostrar "Número decimal: " + numeroDecimal

    Mostrar "Número entero: " + numeroEntero

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class ConversionEstrecha {

    public static void main(String[] args) {

        double numeroDecimal = 9.99;

        int numeroEntero = (int) numeroDecimal;

        System.out.println("Número decimal: " + numeroDecimal);

        System.out.println("Número entero: " + numeroEntero);
    }
}
```
<h3>Compilación de codigo</h3>
<img width="455" height="223" alt="Captura de pantalla 2026-05-26 115027" src="https://github.com/user-attachments/assets/c81d88b4-dbce-47ee-9170-9ac2a46a333c" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="error-absoluto" align="center">
7. Error absoluto
</h2>

<h3>¿Qué es?</h3>

<p>
El error absoluto es la diferencia entre el valor real de una cantidad y el valor aproximado obtenido mediante cálculos o métodos numéricos. Este tipo de error permite medir qué tan lejos está un resultado calculado respecto al valor verdadero.
</p>

<p>
Es uno de los errores más utilizados en métodos numéricos, análisis matemático y cálculos científicos.
</p>

<p>
Por ejemplo:
</p>

<pre>
Valor real = 3.1416
Valor aproximado = 3.14
</pre>

<p>
El error absoluto indica la diferencia exacta entre ambos valores.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Error absoluto</h4>

<pre>
Ea = |Valor real - Valor aproximado|
</pre>

<h4>Ejemplo matemático</h4>

<pre>
Ea = |3.1416 - 3.14|

Ea = 0.0016
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Es fácil de calcular e interpretar.</li>
<li>Permite medir la precisión de un resultado.</li>
<li>Ayuda a comparar métodos numéricos.</li>
<li>Se utiliza ampliamente en cálculos científicos.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>No indica qué tan grande es el error respecto al valor real.</li>
<li>Puede ser engañoso con números muy grandes o muy pequeños.</li>
<li>No expresa el error en porcentaje.</li>
<li>Depende de la escala de los datos.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Validación de algoritmos y simulaciones.</li>

<li><b>Ingeniería Civil:</b> Análisis estructural y cálculos matemáticos.</li>

<li><b>Ingeniería Mecánica:</b> Simulación de fuerzas y movimiento.</li>

<li><b>Ingeniería Electrónica:</b> Procesamiento de señales y mediciones.</li>

<li><b>Ingeniería Industrial:</b> Control de calidad y análisis estadístico.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir valorReal = 3.1416
    Definir valorAproximado = 3.14

    errorAbsoluto = valorAbsoluto(valorReal - valorAproximado)

    Mostrar "Valor real: " + valorReal
    Mostrar "Valor aproximado: " + valorAproximado
    Mostrar "Error absoluto: " + errorAbsoluto

Fin
</pre>

<h3>Ejemplo en Java</h3>

```java
public class ErrorAbsoluto {

    public static void main(String[] args) {

        double valorReal = 3.1416;
        double valorAproximado = 3.14;

        double errorAbsoluto;

        errorAbsoluto = Math.abs(valorReal - valorAproximado);

        System.out.println("Valor real: " + valorReal);
        System.out.println("Valor aproximado: " + valorAproximado);
        System.out.println("Error absoluto: " + errorAbsoluto);
    }
}
```
<h3>Compilación de codigo</h3>

<img width="344" height="127" alt="Captura de pantalla 2026-05-27 191054" src="https://github.com/user-attachments/assets/5e4e5bd5-71ff-4334-ab03-bb8b490f29e8" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="error-relativo" align="center">
8. Error relativo
</h2>

<h3>¿Qué es?</h3>

<p>
El error relativo es una medida que indica qué tan grande es el error absoluto en relación con el valor real. Este tipo de error permite conocer la magnitud del error proporcionalmente al tamaño del dato original.
</p>

<p>
En métodos numéricos y cálculos científicos, el error relativo es muy importante porque ayuda a evaluar la precisión de una aproximación independientemente de la escala de los valores.
</p>

<p>
Por ejemplo:
</p>

<pre>
Valor real = 50
Valor aproximado = 49
</pre>

<p>
Aunque la diferencia es pequeña, el error relativo permite saber qué tan significativo es el error respecto al valor verdadero.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Error relativo</h4>

<pre>
Er = |Valor real - Valor aproximado| / |Valor real|
</pre>

<h4>Error porcentual</h4>

<pre>
Ep = Er × 100
</pre>

<h4>Ejemplo matemático</h4>

<pre>
Er = |50 - 49| / 50

Er = 1 / 50

Er = 0.02
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite medir la precisión proporcional de un cálculo.</li>
<li>Facilita la comparación entre diferentes resultados.</li>
<li>Es ampliamente utilizado en métodos numéricos.</li>
<li>Ayuda a evaluar la calidad de aproximaciones matemáticas.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>No puede calcularse cuando el valor real es cero.</li>
<li>Puede generar valores muy grandes con números pequeños.</li>
<li>Depende directamente de la exactitud del valor real.</li>
<li>Puede ser más difícil de interpretar que el error absoluto.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Evaluación de algoritmos numéricos y simulaciones.</li>

<li><b>Ingeniería Civil:</b> Análisis estructural y cálculos de precisión.</li>

<li><b>Ingeniería Mecánica:</b> Simulación matemática y análisis físico.</li>

<li><b>Ingeniería Electrónica:</b> Procesamiento de señales y mediciones.</li>

<li><b>Ingeniería Industrial:</b> Control estadístico y optimización.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir valorReal = 50
    Definir valorAproximado = 49

    errorRelativo = valorAbsoluto(valorReal - valorAproximado) / valorReal

    Mostrar "Valor real: " + valorReal
    Mostrar "Valor aproximado: " + valorAproximado
    Mostrar "Error relativo: " + errorRelativo

    errorPorcentual = errorRelativo * 100

    Mostrar "Error porcentual: " + errorPorcentual + "%"

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class ErrorRelativo {

    public static void main(String[] args) {

        double valorReal = 50;
        double valorAproximado = 49;

        double errorRelativo;

        errorRelativo = Math.abs(valorReal - valorAproximado) / valorReal;

        System.out.println("Valor real: " + valorReal);
        System.out.println("Valor aproximado: " + valorAproximado);
        System.out.println("Error relativo: " + errorRelativo);

        double errorPorcentual = errorRelativo * 100;

        System.out.println("Error porcentual: " + errorPorcentual + "%");
    }
}
```
<h3>Compilación de codigo</h3>
<img width="333" height="115" alt="Captura de pantalla 2026-05-27 191731" src="https://github.com/user-attachments/assets/b97f211c-c018-478c-a632-79def4e89110" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="eliminacion-gaussiana" align="center">
1. Eliminación Gaussiana
</h2>

<h3>¿Qué es?</h3>

<p>
La Eliminación Gaussiana es un método numérico utilizado para resolver sistemas de ecuaciones lineales. Su objetivo es transformar una matriz aumentada en una matriz triangular superior mediante operaciones elementales entre filas.
</p>

<p>
Después de convertir la matriz en forma escalonada, se utiliza el proceso de sustitución hacia atrás para encontrar el valor de las incógnitas.
</p>

<p>
Este método es ampliamente utilizado en álgebra lineal, programación científica y simulaciones matemáticas.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Sistema de ecuaciones lineales</h4>

<pre>
a11x1 + a12x2 + a13x3 = b1
a21x1 + a22x2 + a23x3 = b2
a31x1 + a32x2 + a33x3 = b3
</pre>

<h4>Factor de eliminación</h4>

<pre>
Factor = aji / aii
</pre>

<h4>Actualización de filas</h4>

<pre>
Fila_j = Fila_j - (Factor × Fila_i)
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite resolver sistemas de ecuaciones lineales de manera ordenada.</li>
<li>Es un método exacto en muchos casos.</li>
<li>Puede implementarse fácilmente en programación.</li>
<li>Es útil para matrices grandes.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede presentar errores de redondeo.</li>
<li>Consume muchos recursos en matrices muy grandes.</li>
<li>Puede fallar si existen divisiones entre cero.</li>
<li>La precisión depende del tipo de dato utilizado.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Desarrollo de algoritmos matemáticos y simulaciones.</li>

<li><b>Ingeniería Civil:</b> Análisis estructural y cálculo de fuerzas.</li>

<li><b>Ingeniería Mecánica:</b> Sistemas dinámicos y simulaciones físicas.</li>

<li><b>Ingeniería Electrónica:</b> Resolución de circuitos eléctricos.</li>

<li><b>Ingeniería Industrial:</b> Optimización y modelos matemáticos.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir n = 3

    Definir matriz =
    {
        {2, -1, 1, 8},
        {-3, -1, 2, -11},
        {-2, 1, 2, -3}
    }

    // Eliminación Gaussiana
    Para i = 0 hasta n - 1

        Para j = i + 1 hasta n - 1

            factor = matriz[j][i] / matriz[i][i]

            Para k = i hasta n

                matriz[j][k] =
                matriz[j][k] - factor * matriz[i][k]

            Fin Para

        Fin Para

    Fin Para

    // Sustitución hacia atrás
    Definir resultado[n]

    Para i = n - 1 hasta 0

        resultado[i] = matriz[i][n]

        Para j = i + 1 hasta n - 1

            resultado[i] =
            resultado[i] - matriz[i][j] * resultado[j]

        Fin Para

        resultado[i] =
        resultado[i] / matriz[i][i]

    Fin Para

    // Mostrar resultados
    Para i = 0 hasta n - 1

        Mostrar "x" + (i + 1) + " = " + resultado[i]

    Fin Para

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class EliminacionGaussiana {

    public static void main(String[] args) {

        int n = 3;

        double[][] matriz = {
            {2, -1, 1, 8},
            {-3, -1, 2, -11},
            {-2, 1, 2, -3}
        };

        // Eliminación Gaussiana
        for (int i = 0; i < n; i++) {

            for (int j = i + 1; j < n; j++) {

                double factor = matriz[j][i] / matriz[i][i];

                for (int k = i; k < n + 1; k++) {

                    matriz[j][k] =
                    matriz[j][k] - factor * matriz[i][k];
                }
            }
        }

        // Sustitución hacia atrás
        double[] resultado = new double[n];

        for (int i = n - 1; i >= 0; i--) {

            resultado[i] = matriz[i][n];

            for (int j = i + 1; j < n; j++) {

                resultado[i] =
                resultado[i] - matriz[i][j] * resultado[j];
            }

            resultado[i] =
            resultado[i] / matriz[i][i];
        }

        // Mostrar resultados
        for (int i = 0; i < n; i++) {

            System.out.println("x" + (i + 1)
            + " = " + resultado[i]);
        }
    }
}
```
<h3>Compilación de codigo</h3>

<img width="341" height="126" alt="Captura de pantalla 2026-05-27 191917" src="https://github.com/user-attachments/assets/9f853c84-4932-4ccc-8e14-fbb573e3fcc8" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="gauss-jordan" align="center">
2. Gauss-Jordan
</h2>

<h3>¿Qué es?</h3>

<p>
El método de Gauss-Jordan es una técnica numérica utilizada para resolver sistemas de ecuaciones lineales. Es una extensión de la Eliminación Gaussiana, pero en este método la matriz se transforma completamente hasta obtener una matriz identidad.
</p>

<p>
A diferencia de la Eliminación Gaussiana, el método de Gauss-Jordan elimina tanto los elementos debajo como encima del pivote, permitiendo obtener directamente los valores de las incógnitas sin necesidad de realizar sustitución hacia atrás.
</p>

<p>
Este método es ampliamente utilizado en álgebra lineal, programación científica y análisis matemático.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Sistema de ecuaciones lineales</h4>

<pre>
a11x1 + a12x2 + a13x3 = b1
a21x1 + a22x2 + a23x3 = b2
a31x1 + a32x2 + a33x3 = b3
</pre>

<h4>Normalización del pivote</h4>

<pre>
Fila_i = Fila_i / Pivote
</pre>

<h4>Eliminación de elementos</h4>

<pre>
Fila_j = Fila_j - (Factor × Fila_i)
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Obtiene directamente las soluciones del sistema.</li>
<li>No requiere sustitución hacia atrás.</li>
<li>Es útil para calcular matrices inversas.</li>
<li>Puede implementarse fácilmente en programación.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Consume más operaciones que la Eliminación Gaussiana.</li>
<li>Puede presentar errores de redondeo.</li>
<li>Es menos eficiente para matrices muy grandes.</li>
<li>Puede fallar si existen pivotes iguales a cero.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Algoritmos matemáticos y simulaciones.</li>

<li><b>Ingeniería Civil:</b> Cálculo estructural y análisis de fuerzas.</li>

<li><b>Ingeniería Mecánica:</b> Sistemas dinámicos y simulaciones físicas.</li>

<li><b>Ingeniería Electrónica:</b> Resolución de circuitos eléctricos.</li>

<li><b>Ingeniería Industrial:</b> Modelos matemáticos y optimización.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir matriz =
    {
        {2, 1, -1, 8},
        {-3, -1, 2, -11},
        {-2, 1, 2, -3}
    }

    filas = número de filas de la matriz
    columnas = número de columnas de la matriz

    Para i = 0 hasta filas - 1

        pivote = matriz[i][i]

        // Convertir pivote en 1
        Para j = 0 hasta columnas - 1

            matriz[i][j] =
            matriz[i][j] / pivote

        Fin Para

        // Hacer ceros en las demás filas
        Para j = 0 hasta filas - 1

            Si i ≠ j Entonces

                factor = matriz[j][i]

                Para k = 0 hasta columnas - 1

                    matriz[j][k] =
                    matriz[j][k] -
                    factor * matriz[i][k]

                Fin Para

            Fin Si

        Fin Para

    Fin Para

    // Mostrar resultados
    Mostrar "Resultados:"

    Para i = 0 hasta filas - 1

        Mostrar "x" + (i + 1) +
        " = " + matriz[i][columnas - 1]

    Fin Para

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class GaussJordan {

    public static void main(String[] args) {

        double[][] matriz = {
            {2, 1, -1, 8},
            {-3, -1, 2, -11},
            {-2, 1, 2, -3}
        };

        int filas = matriz.length;
        int columnas = matriz[0].length;

        for (int i = 0; i < filas; i++) {

            double pivote = matriz[i][i];

            // Convertir pivote en 1
            for (int j = 0; j < columnas; j++) {

                matriz[i][j] =
                matriz[i][j] / pivote;
            }

            // Hacer ceros en las demás filas
            for (int j = 0; j < filas; j++) {

                if (i != j) {

                    double factor = matriz[j][i];

                    for (int k = 0; k < columnas; k++) {

                        matriz[j][k] =
                        matriz[j][k] -
                        factor * matriz[i][k];
                    }
                }
            }
        }

        // Mostrar resultados
        System.out.println("Resultados:");

        for (int i = 0; i < filas; i++) {

            System.out.println("x" + (i + 1)
            + " = " + matriz[i][columnas - 1]);
        }
    }
}
```
<h3>Compilación de codigo</h3>

<img width="329" height="140" alt="Captura de pantalla 2026-05-27 192114" src="https://github.com/user-attachments/assets/7d9c96a8-3c1f-4324-b4bd-2fafb8e6f3b8" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="gauss-seidel" align="center">
3. Gauss-Seidel
</h2>

<h3>¿Qué es?</h3>

<p>
El método de Gauss-Seidel es un método numérico iterativo utilizado para resolver sistemas de ecuaciones lineales. A diferencia de métodos directos como Eliminación Gaussiana o Gauss-Jordan, este método obtiene soluciones aproximadas mediante iteraciones sucesivas.
</p>

<p>
En cada iteración, los valores calculados se actualizan inmediatamente y se reutilizan en los siguientes cálculos, lo que generalmente permite una convergencia más rápida.
</p>

<p>
Este método es ampliamente utilizado en simulaciones numéricas, análisis matemático y programación científica.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Fórmula general de Gauss-Seidel</h4>

<pre>
xi(k+1) = (1 / aii)
[ bi - Σ(aij * xj) ]
</pre>

<p>
Donde:
</p>

<ul>
<li><b>aii</b> = elemento diagonal principal</li>
<li><b>bi</b> = término independiente</li>
<li><b>xj</b> = valores aproximados de las variables</li>
<li><b>k</b> = número de iteración</li>
</ul>

<h4>Criterio de error</h4>

<pre>
Error = |Valor nuevo - Valor anterior|
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Requiere menos memoria que métodos directos.</li>
<li>Es eficiente para matrices grandes.</li>
<li>Puede converger rápidamente en ciertos sistemas.</li>
<li>Es sencillo de implementar en programación.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>No siempre converge.</li>
<li>Depende de una buena aproximación inicial.</li>
<li>Puede acumular errores numéricos.</li>
<li>La convergencia depende de la matriz del sistema.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li><b>Ingeniería en Sistemas Computacionales:</b> Simulaciones numéricas y algoritmos matemáticos.</li>

<li><b>Ingeniería Civil:</b> Análisis estructural y resolución de sistemas grandes.</li>

<li><b>Ingeniería Mecánica:</b> Simulación de movimiento y dinámica.</li>

<li><b>Ingeniería Electrónica:</b> Análisis de circuitos eléctricos.</li>

<li><b>Ingeniería Industrial:</b> Optimización y modelado matemático.</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir matriz A =
    {
        {4, 1, 2},
        {3, 5, 1},
        {1, 1, 3}
    }

    Definir vector b = {4, 7, 3}

    Definir vector x = {0, 0, 0}

    Definir iteraciones = 10

    Para k = 0 hasta iteraciones - 1

        x[0] = (b[0] - A[0][1] * x[1]
                - A[0][2] * x[2]) / A[0][0]

        x[1] = (b[1] - A[1][0] * x[0]
                - A[1][2] * x[2]) / A[1][1]

        x[2] = (b[2] - A[2][0] * x[0]
                - A[2][1] * x[1]) / A[2][2]

    Fin Para

    Mostrar "Resultados:"

    Para i = 0 hasta longitud de x - 1

        Mostrar "x" + (i + 1)
        + " = " + x[i]

    Fin Para

Fin
</pre>

<h3>Ejemplo en Java</h3>

```java
public class GaussSeidel {

    public static void main(String[] args) {

        double[][] A = {
            {4, 1, 2},
            {3, 5, 1},
            {1, 1, 3}
        };

        double[] b = {4, 7, 3};

        double[] x = {0, 0, 0};

        int iteraciones = 10;

        for (int k = 0; k < iteraciones; k++) {

            x[0] = (b[0] - A[0][1] * x[1]
                    - A[0][2] * x[2]) / A[0][0];

            x[1] = (b[1] - A[1][0] * x[0]
                    - A[1][2] * x[2]) / A[1][1];

            x[2] = (b[2] - A[2][0] * x[0]
                    - A[2][1] * x[1]) / A[2][2];
        }

        System.out.println("Resultados:");

        for (int i = 0; i < x.length; i++) {

            System.out.println("x" + (i + 1)
            + " = " + x[i]);
        }
    }
}
```
<h3>Compilación de codigo</h3>
<img width="330" height="139" alt="Captura de pantalla 2026-05-27 192300" src="https://github.com/user-attachments/assets/ee9a44c5-266b-45fa-848e-8159e7992312" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="jacobi" align="center">
4. Método de Jacobi
</h2>

<h3>¿Qué es?</h3>

<p>
El método de Jacobi es un método iterativo utilizado para resolver sistemas de ecuaciones lineales. Este método consiste en despejar cada variable de las ecuaciones del sistema y calcular nuevas aproximaciones utilizando únicamente los valores obtenidos en la iteración anterior.
</p>

<p>
Es ampliamente utilizado en métodos numéricos debido a que permite resolver sistemas grandes de ecuaciones de manera sencilla y organizada.
</p>

<p>
El método continúa realizando iteraciones hasta que el error entre una iteración y otra sea suficientemente pequeño.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Forma general del método de Jacobi</h4>

<pre>
x₁(k+1) = (b₁ - a₁₂x₂(k) - a₁₃x₃(k) - ... - a₁nxn(k)) / a₁₁

x₂(k+1) = (b₂ - a₂₁x₁(k) - a₂₃x₃(k) - ... - a₂nxn(k)) / a₂₂

...

xn(k+1) = (bn - an₁x₁(k) - an₂x₂(k) - ... - an(n-1)x(n-1)(k)) / ann
</pre>

<h4>Error aproximado</h4>

<pre>
Ea = |Valor actual - Valor anterior|
</pre>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Es fácil de implementar.</li>
<li>Permite resolver sistemas grandes de ecuaciones.</li>
<li>Puede aplicarse en programación paralela.</li>
<li>No requiere transformar completamente la matriz.</li>
<li>Es útil para matrices diagonalmente dominantes.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede tardar muchas iteraciones en converger.</li>
<li>No siempre garantiza convergencia.</li>
<li>Es menos rápido que otros métodos iterativos como Gauss-Seidel.</li>
<li>Depende mucho de los valores iniciales.</li>
<li>Puede generar errores acumulativos.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Resolución de sistemas matemáticos y simulaciones numéricas.
</li>

<li>
<b>Ingeniería Civil:</b>
Análisis estructural y cálculo de cargas.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Modelado de sistemas físicos y transferencia de calor.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Análisis de circuitos eléctricos.
</li>

<li>
<b>Ingeniería Industrial:</b>
Optimización de procesos y modelos matemáticos.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir EPSILON = 0.0001
    Definir MAX_ITERACIONES = 100

    Definir matriz A =
    {
        {10, -1, 2},
        {-1, 11, -1},
        {2, -1, 10}
    }

    Definir vector B = {6, 25, -11}

    Definir vector X = {0, 0, 0}
    Definir vector nuevoX = {0, 0, 0}

    iteracion = 0
    convergencia = falso

    Mientras no convergencia
    y iteracion < MAX_ITERACIONES

        Para i = 0 hasta longitud de B - 1

            suma = B[i]

            Para j = 0 hasta longitud de B - 1

                Si i ≠ j Entonces

                    suma =
                    suma - A[i][j] * X[j]

                Fin Si

            Fin Para

            nuevoX[i] =
            suma / A[i][i]

        Fin Para

        errorMaximo = 0

        Para i = 0 hasta longitud de B - 1

            error =
            valorAbsoluto(nuevoX[i] - X[i])

            Si error > errorMaximo Entonces

                errorMaximo = error

            Fin Si

            X[i] = nuevoX[i]

        Fin Para

        Si errorMaximo < EPSILON Entonces

            convergencia = verdadero

        Fin Si

        iteracion = iteracion + 1

    Fin Mientras

    Mostrar "Resultados:"

    Para i = 0 hasta longitud de X - 1

        Mostrar "x" + (i + 1)
        + " = " + X[i]

    Fin Para

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class Jacobi {

    public static final double EPSILON = 0.0001;
    public static final int MAX_ITERACIONES = 100;

    public static void main(String[] args) {

        double[][] A = {
            {10, -1, 2},
            {-1, 11, -1},
            {2, -1, 10}
        };

        double[] B = {6, 25, -11};

        double[] X = metodoJacobi(A, B);

        System.out.println("Resultados:");

        for(int i = 0; i < X.length; i++) {
            System.out.println("x" + (i + 1) + " = " + X[i]);
        }
    }

    public static double[] metodoJacobi(double[][] A, double[] B) {

        int n = B.length;

        double[] X = new double[n];
        double[] nuevoX = new double[n];

        int iteracion = 0;
        boolean convergencia = false;

        while(!convergencia && iteracion < MAX_ITERACIONES) {

            for(int i = 0; i < n; i++) {

                double suma = B[i];

                for(int j = 0; j < n; j++) {

                    if(i != j) {
                        suma -= A[i][j] * X[j];
                    }
                }

                nuevoX[i] = suma / A[i][i];
            }

            double errorMaximo = 0;

            for(int i = 0; i < n; i++) {

                double error = Math.abs(nuevoX[i] - X[i]);

                if(error > errorMaximo) {
                    errorMaximo = error;
                }

                X[i] = nuevoX[i];
            }

            if(errorMaximo < EPSILON) {
                convergencia = true;
            }

            iteracion++;
        }

        return X;
    }
}
```
<h3>Compilación de codigo</h3>

<img width="324" height="140" alt="Captura de pantalla 2026-05-27 192823" src="https://github.com/user-attachments/assets/4e2dc8fb-3759-4b3c-95f6-4af9a0ecd67d" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>
