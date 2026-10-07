# El ejercicio consiste en pedirle al cliente su sueldo y puesto de trabajo para calcularle el sueldo final,
# aceptando solo el sueldo si es un número entero y si es mayor de 1000.

La tarea está dividida en dos archivos php, uno es el formulario donde el cliente introduce sus datos, ("UT02-P02.html)
y el otro documento es el que recibe los datos de este formulario para calcular su sueldo (UT02-P02B.php).

El __formulario__ usa el método POST para enviar los datos al otro archivo, __EXPLICACIÓN__:

El campo del sueldo utiliza:
/* <input type="number" min="1001" step="1" required>

Esto permite usar solo números enteros y mayores que 1000.

El puesto se selecciona mediante un ekemento <select>:
<select name="puesto"> <option value="base">Base</option> <option value="directivo">Directivo</option> <option value="alto_cargo">Alto cargo</option> </select>

y el formulario se envía al otro archivo mediante:
<form action="UT02-P02B.php" method="post">.

el segundo archivo recibe sueldo y puesto, mediante $_POST:
$sueldo = $_POST["sueldo"]; $puesto = $_POST["puesto"];

Al recibir los datos, comprueba el puesto seleccionado con un if:
if ($puesto == "base") { 
    $porcentaje = 10; 
} elseif ($puesto == "directivo") { 
    $porcentaje = 15; 
} else { 
    $porcentaje = 20; 
}

y dependiendo del puesto, usa un porcentaje distinto:
Base 10%
Directivo 15%
Alto Cargo 20%

Entonces segun el puesto, calcularía el sueldo que tendrá el cliente dependiendo de su puesto.

Resumen: Si el cliente introduce por ejemplo 1200€, y su puesto es el Base, el programa comprueba si el sueldo es un numero entero, si es mayor de mil, y calcularía:  Complemento = 1200 * 10  100, Complemento = 120€, por tanto 1200 + 120 = 1320€.
al final mostraría:
El sueldo base es de 1200€
El complemento es del 10%
El sueldo final es de 1320€
