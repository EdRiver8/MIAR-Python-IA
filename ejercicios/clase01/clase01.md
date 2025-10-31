# Clase 01: Introducción y Python 101

## Información de la Sesión

- **Fecha:** [Fecha de la clase]
- **Duración:** [Duración]
- **Instructor:** [Nombre del instructor]

## Configuración del Entorno

### Entorno Específico para esta Clase

```bash
# Crear entorno para clase 01
python -m venv envs/clase01-python-basics

# Activar entorno
envs\clase01-python-basics\Scripts\activate

# Instalar dependencias básicas
pip install jupyter numpy pandas matplotlib seaborn ipykernel

# Registrar kernel
python -m ipykernel install --user --name clase01 --display-name "Python (Clase 01 - Basics)"

# Guardar dependencias
pip freeze > ejercicios/clase01/requirements.txt
```

## Conceptos Clave de la Clase

### 1. Fundamentos de Python

#### Variables y Asignación

```python
# Asignación de variables
nombre = "Ana"
edad = 25
altura = 1.65
es_estudiante = True

# Python es dinámicamente tipado
variable = 10        # int
variable = "Hola"    # str - la misma variable ahora es string
variable = 3.14      # float
```

#### Reglas para Nombres de Variables

```python
# ✅ Válidos
mi_variable = 1
nombre_usuario = "Juan"
edad2 = 25
_privada = "valor"

# ❌ No válidos
# 2nombre = "error"     # No puede empezar con número
# mi-variable = 1       # No puede tener guiones
# class = "error"       # No puede ser palabra reservada
```

### 2. Tipos de Datos Básicos

#### Números (int, float)

```python
# Enteros (int)
edad = 25
cantidad = -50
numero_grande = 1000000

# Flotantes (float)
precio = 19.99
temperatura = -3.5
pi = 3.14159

# Operaciones básicas
suma = 10 + 5        # 15
resta = 10 - 3       # 7
multiplicacion = 4 * 6   # 24
division = 15 / 3    # 5.0 (siempre float)
division_entera = 15 // 4  # 3
modulo = 15 % 4      # 3 (resto)
potencia = 2 ** 3    # 8
```

#### Cadenas de Texto (str)

```python
# Definición de strings
nombre = "Juan"
apellido = 'Pérez'
texto_largo = """Este es un
texto de múltiples
líneas"""

# Concatenación
nombre_completo = nombre + " " + apellido  # "Juan Pérez"

# F-strings (recomendado)
edad = 25
mensaje = f"Hola, soy {nombre} y tengo {edad} años"

# Métodos útiles de strings
texto = "Python Programming"
print(texto.lower())        # "python programming"
print(texto.upper())        # "PYTHON PROGRAMMING"
print(texto.title())        # "Python Programming"
print(len(texto))          # 18
print(texto.replace("Python", "Java"))  # "Java Programming"
```

#### Booleanos (bool)

```python
# Valores booleanos
verdadero = True
falso = False

# Operadores de comparación
mayor = 10 > 5       # True
menor = 3 < 2        # False
igual = 5 == 5       # True
diferente = 5 != 3   # True

# Operadores lógicos
resultado1 = True and False   # False
resultado2 = True or False    # True
resultado3 = not True         # False

# Valores que se evalúan como False
print(bool(0))          # False
print(bool(""))         # False (string vacío)
print(bool([]))         # False (lista vacía)
print(bool(None))       # False
```

### 3. Estructuras de Datos

#### Listas (list)

```python
# Crear listas
numeros = [1, 2, 3, 4, 5]
nombres = ["Ana", "Luis", "María"]
mixta = [1, "Hola", 3.14, True]
vacia = []

# Acceso por índice
primer_numero = numeros[0]    # 1
ultimo_numero = numeros[-1]   # 5

# Métodos útiles
numeros.append(6)        # Agregar al final
numeros.insert(0, 0)     # Agregar en posición específica
numeros.remove(3)        # Eliminar valor específico
ultimo = numeros.pop()   # Eliminar y retornar último elemento

# Slicing (rebanadas)
sublista = numeros[1:4]   # Elementos del índice 1 al 3
primeros_3 = numeros[:3]  # Primeros 3 elementos
ultimos_2 = numeros[-2:]  # Últimos 2 elementos

# List comprehension
cuadrados = [x**2 for x in range(5)]  # [0, 1, 4, 9, 16]
pares = [x for x in range(10) if x % 2 == 0]  # [0, 2, 4, 6, 8]
```

#### Tuplas (tuple)

```python
# Crear tuplas (inmutables)
coordenadas = (10, 20)
colores = ("rojo", "verde", "azul")
persona = ("Ana", 25, "Madrid")

# Acceso por índice
x = coordenadas[0]  # 10
y = coordenadas[1]  # 20

# Desempaquetado
nombre, edad, ciudad = persona
print(f"{nombre} tiene {edad} años y vive en {ciudad}")

# Las tuplas son inmutables
# coordenadas[0] = 15  # Error!
```

#### Diccionarios (dict)

```python
# Crear diccionarios
persona = {
    "nombre": "Ana",
    "edad": 25,
    "ciudad": "Madrid",
    "es_estudiante": True
}

# Diccionario vacío
vacio = {}
vacio2 = dict()

# Acceso a valores
nombre = persona["nombre"]           # "Ana"
edad = persona.get("edad")          # 25
profesion = persona.get("profesion", "No especificada")  # Valor por defecto

# Modificar y agregar
persona["edad"] = 26               # Modificar
persona["profesion"] = "Ingeniera"  # Agregar nueva clave

# Métodos útiles
claves = persona.keys()     # dict_keys(['nombre', 'edad', 'ciudad', ...])
valores = persona.values()  # dict_values(['Ana', 26, 'Madrid', ...])
items = persona.items()     # dict_items([('nombre', 'Ana'), ...])

# Iterar sobre diccionario
for clave, valor in persona.items():
    print(f"{clave}: {valor}")
```

#### Conjuntos (set)

```python
# Crear conjuntos (elementos únicos)
numeros = {1, 2, 3, 4, 5}
colores = {"rojo", "verde", "azul"}

# Desde lista (elimina duplicados)
lista_con_duplicados = [1, 2, 2, 3, 3, 3, 4]
conjunto_unico = set(lista_con_duplicados)  # {1, 2, 3, 4}

# Operaciones de conjunto
conjunto1 = {1, 2, 3, 4}
conjunto2 = {3, 4, 5, 6}

union = conjunto1 | conjunto2         # {1, 2, 3, 4, 5, 6}
interseccion = conjunto1 & conjunto2  # {3, 4}
diferencia = conjunto1 - conjunto2    # {1, 2}
```

### 4. Control de Flujo Básico

#### Condicionales

```python
edad = 18

if edad >= 18:
    print("Eres mayor de edad")
elif edad >= 13:
    print("Eres adolescente")
else:
    print("Eres menor de edad")

# Operador ternario
mensaje = "Mayor" if edad >= 18 else "Menor"
```

#### Bucles

```python
# For con listas
nombres = ["Ana", "Luis", "María"]
for nombre in nombres:
    print(f"Hola {nombre}")

# For con range
for i in range(5):        # 0, 1, 2, 3, 4
    print(i)

for i in range(1, 6):     # 1, 2, 3, 4, 5
    print(i)

for i in range(0, 10, 2): # 0, 2, 4, 6, 8
    print(i)

# While
contador = 0
while contador < 5:
    print(contador)
    contador += 1
```

## Librerías Utilizadas

### NumPy - Computación Numérica

#### ¿Para qué se usa NumPy?

**NumPy (Numerical Python)** es la librería fundamental para computación científica en Python:

1. **Arrays N-dimensionales:** Estructuras de datos eficientes para trabajar con grandes conjuntos de datos
2. **Operaciones Matemáticas:** Funciones matemáticas avanzadas aplicadas a arrays completos
3. **Álgebra Lineal:** Operaciones con matrices, vectores y sistemas de ecuaciones
4. **Base para otras librerías:** Pandas, Scikit-learn, Matplotlib se construyen sobre NumPy

#### Ejemplos básicos de NumPy:

```python
import numpy as np

# Crear arrays
arr = np.array([1, 2, 3, 4, 5])
matriz = np.array([[1, 2], [3, 4]])

# Operaciones matemáticas vectorizadas
resultado = arr * 2  # Multiplica todos los elementos por 2
suma = np.sum(arr)   # Suma todos los elementos

# Funciones estadísticas
media = np.mean(arr)
std = np.std(arr)

# Generación de datos
datos_aleatorios = np.random.normal(0, 1, 1000)  # 1000 números aleatorios
secuencia = np.arange(0, 10, 0.1)  # Secuencia de 0 a 10 con paso 0.1
```

### Pandas - Análisis y Manipulación de Datos

#### ¿Para qué se usa Pandas?

**Pandas** es la librería principal para análisis y manipulación de datos estructurados:

1. **DataFrames y Series:** Estructuras de datos similares a tablas de Excel o SQL
2. **Lectura/Escritura de archivos:** CSV, Excel, JSON, SQL, etc.
3. **Limpieza de datos:** Manejo de valores faltantes, duplicados, transformaciones
4. **Análisis exploratorio:** Estadísticas descriptivas, agrupaciones, filtros
5. **Manipulación de datos:** Uniones, pivotes, reshape de datos

#### Ejemplos básicos de Pandas:

```python
import pandas as pd

# Crear DataFrame desde diccionario
data = {
    'nombre': ['Ana', 'Luis', 'María'],
    'edad': [25, 30, 35],
    'ciudad': ['Madrid', 'Barcelona', 'Valencia']
}
df = pd.DataFrame(data)

# Exploración básica
print(df.head())          # Primeras 5 filas
print(df.info())          # Información del dataset
print(df.describe())      # Estadísticas descriptivas

# Filtrado de datos
mayores_30 = df[df['edad'] > 30]
madrid = df[df['ciudad'] == 'Madrid']

# Agrupaciones
promedio_edad = df.groupby('ciudad')['edad'].mean()
```

## Ejercicios Realizados

### Ejercicio 1: [Título del ejercicio]

- **Objetivo:** [Describir objetivo]
- **Archivo:** [nombre_archivo.py o .ipynb]
- **Notas:** [Observaciones importantes]

### Ejercicio 2: [Título del ejercicio]

- **Objetivo:** [Describir objetivo]
- **Archivo:** [nombre_archivo.py o .ipynb]
- **Notas:** [Observaciones importantes]

## Actividades de Clase

### Dataset Analysis

- **Notebook:** `../../clases/01_MIAR_OCT25/act/01MIAR_ACT_Dataset.ipynb`
- **Descripción:** [Describir qué se hizo en el análisis]
- **Conceptos aplicados:** [Lista de conceptos]

### White Papers Review

- **Notebook:** `../../clases/01_MIAR_OCT25/act/01MIAR_ACT_WhitePapers.ipynb`
- **Descripción:** [Describir qué papers se revisaron]
- **Puntos clave:** [Puntos importantes del review]

## Tareas y Ejercicios Pendientes

- [ ] [Tarea 1]
- [ ] [Tarea 2]
- [ ] [Revisar conceptos de X]

## Dudas y Notas Adicionales

- [Agregar dudas que surgieron en clase]
- [Conceptos que necesitan refuerzo]
- [Enlaces a recursos adicionales]

## Archivos de la Clase

```
ejercicios/clase01/
├── clase01.md                    # Este archivo
├── requirements.txt              # Dependencias de la clase
├── notebooks/                    # Notebooks de práctica
│   ├── ejercicio01.ipynb
│   └── ejercicio02.ipynb
└── scripts/                      # Scripts de Python
    ├── ejemplo01.py
    └── ejemplo02.py
```

### Nota sobre Múltiples Archivos `requirements.txt`

Es una buena práctica mantener un archivo `requirements.txt` separado para cada entorno/clase. Esto asegura que cada entorno sea independiente y reproducible sin instalar paquetes innecesarios de otras clases.

#### ¿Cómo generar el archivo?

```bash
# 1. Activa el entorno
envs\clase01-python-basics\Scripts\activate

# 2. Guarda las dependencias
pip freeze > ejercicios\clase01\requirements.txt
```

#### ¿Cómo instalar desde el archivo?

Esto es útil para recrear el entorno en otra máquina o si borraste la carpeta `envs`.

```bash
# 1. (Opcional) Crea el entorno si no existe
python -m venv envs/clase01-python-basics

# 2. Activa el entorno correspondiente
envs\clase01-python-basics\Scripts\activate

# 3. Instala las dependencias exactas desde el archivo
pip install -r ejercicios\clase01\requirements.txt
```

## Próxima Clase

**Clase 02: Tipos de Datos en Python**

- Preparar: [Lista de preparación]
- Leer: [Materiales de lectura]
