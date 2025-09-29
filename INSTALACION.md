# Guía de Instalación - Laboratorio 7: Predicción de Diabetes con AutoGluon

## Autores
- **Javier Prado** - 21496
- **Luis Pedro Montenegro** - 21699

## Requisitos del Sistema

### Python
- **Versión requerida:** Python 3.8, 3.9, 3.10, o 3.11
- **Verificar versión:** 
  ```bash
  python --version
  ```

### Sistema Operativo
- **Windows:** Windows 10/11 (64-bit)
- **macOS:** macOS 10.14+
- **Linux:** Ubuntu 18.04+ o distribuciones equivalentes

## Opciones de Instalación

### Opción 1: Instalación Completa (Recomendada)

1. **Crear entorno virtual:**
   ```bash
   # Crear entorno virtual
   python -m venv lab_autogluon
   
   # Activar entorno (Windows)
   lab_autogluon\Scripts\activate
   
   # Activar entorno (macOS/Linux)
   source lab_autogluon/bin/activate
   ```

2. **Instalar requerimientos:**
   ```bash
   pip install -r requierment.txt
   ```

### Opción 2: Instalación Paso a Paso

1. **Librerías básicas:**
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```

2. **AutoGluon:**
   ```bash
   pip install autogluon
   ```

3. **Librerías adicionales:**
   ```bash
   pip install missingno scikit-learn scipy statsmodels
   ```

### Opción 3: Instalación con Conda

```bash
# Crear entorno con conda
conda create -n lab_autogluon python=3.10

# Activar entorno
conda activate lab_autogluon

# Instalar paquetes principales
conda install pandas numpy matplotlib seaborn jupyter scikit-learn scipy

# Instalar AutoGluon con pip (no disponible en conda)
pip install autogluon missingno statsmodels
```

## Verificación de la Instalación

Ejecuta el siguiente código en Python para verificar que todo esté instalado correctamente:

```python
# Verificar instalación
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import autogluon
from autogluon.tabular import TabularPredictor

print("✅ Todas las librerías están instaladas correctamente!")
print(f"Pandas versión: {pd.__version__}")
print(f"NumPy versión: {np.__version__}")
print(f"AutoGluon versión: {autogluon.__version__}")
```

## Solución de Problemas Comunes

### Error 1: "Microsoft Visual C++ 14.0 is required"
**Solución (Windows):**
- Instalar Microsoft C++ Build Tools
- O instalar Visual Studio Community

### Error 2: Problemas con AutoGluon
**Solución:**
```bash
# Desinstalar e instalar de nuevo
pip uninstall autogluon
pip install autogluon --no-cache-dir
```

### Error 3: Memoria insuficiente
**Solución:**
- Cerrar aplicaciones innecesarias
- Usar un subset de datos para pruebas
- Considerar usar Google Colab o similar

### Error 4: Conflictos de versiones
**Solución:**
```bash
# Crear entorno limpio
pip freeze > backup_requirements.txt
pip uninstall -r backup_requirements.txt -y
pip install -r requierment.txt
```

## Recursos Adicionales

- **Documentación AutoGluon:** https://auto.gluon.ai/
- **Dataset diabetes:** Incluido en el repositorio (`diabetes.csv`)
- **Jupyter Notebook:** `lab.ipynb`

## Configuración de Jupyter

Para trabajar con el notebook:

```bash
# Instalar kernel en Jupyter
python -m ipykernel install --user --name=lab_autogluon

# Iniciar Jupyter
jupyter notebook lab.ipynb
```

## Hardware Recomendado

- **RAM:** Mínimo 8GB, recomendado 16GB+
- **CPU:** Mínimo 4 cores
- **Espacio en disco:** 5GB libres
- **GPU:** Opcional, pero acelera el entrenamiento

## Tiempo Estimado de Instalación

- **Instalación básica:** 5-10 minutos
- **Instalación completa:** 15-30 minutos
- **Con dependencias de GPU:** 30-45 minutos

---

**Nota:** Si encuentras algún problema durante la instalación, revisa los logs de error y consulta la documentación oficial de cada librería.