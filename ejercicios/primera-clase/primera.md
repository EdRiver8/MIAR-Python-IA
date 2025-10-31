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
