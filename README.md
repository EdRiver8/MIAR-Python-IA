<<<<<<< HEAD
# Máster - Notas de Clase

## Estructura del Proyecto

- `clases/01_MIAR_OCT25/` - Material de clase del profesor
- `ejercicios/` - Ejercicios y prácticas propias organizados por clase
- `envs/` - Entornos virtuales de Python

## ¿Por qué usar Entornos Virtuales?

### Problemas que Resuelven

1. **Conflictos de Dependencias:**

   - Diferentes proyectos pueden requerir versiones distintas del mismo paquete
   - Evita el "dependency hell" (infierno de dependencias)

2. **Aislamiento de Proyectos:**

   - Cada proyecto tiene su propio conjunto de paquetes
   - Los cambios en un proyecto no afectan a otros

3. **Reproducibilidad:**

   - Permite recrear el mismo entorno en diferentes máquinas
   - Facilita la colaboración y deployment

4. **Limpieza del Sistema:**
   - No contamina la instalación global de Python
   - Evita problemas con paquetes del sistema operativo

### Ejemplo de Problema Sin Entornos Virtuales

```bash
# Instalación global - ¡EVITAR!
pip install pandas==1.5.0  # Para proyecto A
pip install pandas==2.0.0  # Para proyecto B - ¡Conflicto!
```

## Buenas Prácticas para Entornos Virtuales

### 1. Un Entorno por Proyecto/Sesión

```bash
# ✅ Buena práctica
python -m venv envs/sesion-01-python-basics
python -m venv envs/sesion-02-data-analysis
python -m venv envs/proyecto-final

# ❌ Mala práctica
python -m venv mi_entorno_para_todo
```

### 2. Nombres Descriptivos

```bash
# ✅ Nombres claros y descriptivos
envs/01-python-fundamentals/
envs/02-pandas-numpy/
envs/03-machine-learning/

# ❌ Nombres genéricos
envs/env1/
envs/test/
envs/proyecto/
```

### 3. Documentar Dependencias

```bash
# Generar archivo de dependencias
pip freeze > requirements.txt

# Instalar desde archivo de dependencias
pip install -r requirements.txt
```

### 4. Estructura de Archivos Recomendada

```
proyecto/
├── envs/
│   ├── sesion-01/
│   ├── sesion-02/
│   └── proyecto-final/
├── notebooks/
├── data/
├── src/
└── requirements/
    ├── sesion-01.txt
    ├── sesion-02.txt
    └── proyecto-final.txt
```

### 5. Comandos Esenciales

```bash
# Crear entorno
python -m venv envs/nombre-proyecto

# Activar (SIEMPRE antes de trabajar)
envs\nombre-proyecto\Scripts\activate  # Windows
source envs/nombre-proyecto/bin/activate  # Linux/Mac

# Verificar entorno activo
which python  # Linux/Mac
where python  # Windows

# Instalar paquetes
pip install package-name

# Guardar dependencias
pip freeze > requirements.txt

# Desactivar al terminar
deactivate
```

### 6. ¿Qué NO incluir en Git?

```gitignore
# .gitignore
envs/
__pycache__/
*.pyc
.env
.venv
```

### 7. Verificación del Entorno

```python
# Verificar que estás en el entorno correcto
import sys
print(sys.executable)
print(sys.path)
```

## Configuración Básica de Entornos Virtuales

### Crear y Activar un Entorno Virtual

```bash
# Crear entorno virtual
python -m venv envs/nombre_entorno

# Activar entorno
envs\nombre_entorno\Scripts\activate  # Windows
source envs/nombre_entorno/bin/activate  # Linux/Mac

# Desactivar entorno
deactivate
```

### Configuración de Jupyter

```bash
# Con el entorno activado
pip install jupyter notebook ipykernel

# Registrar el entorno como kernel en Jupyter
python -m ipykernel install --user --name nombre_entorno --display-name "Python (Nombre Descriptivo)"

# Ejecutar Jupyter
jupyter notebook
```

## Flujo de Trabajo Recomendado

1. **Crear y activar entorno por clase**
2. **Instalar dependencias necesarias**
3. **Registrar kernel en Jupyter**
4. **Guardar dependencias en requirements.txt**
5. **Trabajar en notebooks específicos de la clase**

## Índice de Clases

- [Clase 01: Introducción y Python 101](ejercicios/clase01/clase01.md)
- [Clase 02: Tipos de Datos en Python](ejercicios/clase02/clase02.md) _(próximamente)_
- [Clase 03: Estructuras de Control](ejercicios/clase03/clase03.md) _(próximamente)_

## Recursos Generales

### Documentación Oficial

- [Python Documentation](https://docs.python.org/3/)
- [Jupyter Documentation](https://jupyter-notebook.readthedocs.io/)

### Tutoriales Recomendados

- [Python.org Tutorial](https://docs.python.org/3/tutorial/)
- [Real Python](https://realpython.com/)

## TODO General

- [ ] Configurar entorno base
- [ ] Establecer estructura de carpetas
- [ ] Crear plantillas para notas de clase
=======
# 01_MIAR_OCT25
>>>>>>> a60a64ecd2123c34362b4878f0948bdc5d49a06b
