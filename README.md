# Identificación de Voces Deepfake con Diferentes Métodos

### Universidad del Valle de Guatemala  
**Facultad de Ingeniería**  
**Ciencia de la Computación y Tecnologías de la Información**  

---

## Descripción  
Este proyecto tiene como objetivo desarrollar un sistema para identificar voces generadas artificialmente (deepfake) utilizando una variedad de métodos, como:  
- Redes neuronales (LSTM).  
- Modelos tradicionales de aprendizaje automático (SVM, KNN, RandomForest, Etc) y comparar sus resultados al utilizar datos .  
- Comparación de resultados con la capacidad de reconocimiento humano.  

Se utilizó el conjunto de datos **ASVspoof 2021** para entrenar y evaluar los modelos, con el propósito de combatir el uso indebido de tecnologías de generación de voz y proteger la integridad de las comunicaciones digitales. Especificamente para el entrenamiento y evaluación de los modelos se utilizo el conjunto de datos DF que se refiere a DeepFake. 

---

## Instrucciones de Instalación  

### **Requisitos previos**  
Antes de iniciar, asegúrate de contar con los siguientes elementos:  
- **Python 3.8 o superior**  
- **Git** para clonar el repositorio.  
- **Gestor de paquetes `pip`**.  
- **Entorno virtual** (opcional pero recomendado) mediante `virtualenv` o herramientas similares.  

Dependencias principales utilizadas en el proyecto:  
- TensorFlow  
- Librosa
- scikit-learn  
- AutoGluon  
- NumPy y pandas  
- Matplotlib
- Seaborn  

### **Pasos para la instalación**  

#### 1. **Clonar el repositorio**:  
   ```bash
   git clone https://github.com/cayomol01/PG-2024-20211
   ```
#### 2. **Instalar dependencias para la aplicación**:  
```bash
pip install requirements.txt
```
#### 3. **Ejecución de la aplicación: Instrucciones para poner en marcha la aplicación.**

Para ejecutar la aplicación se necesita estar en un cuaderno de google colab. O bien, tener conocimiento de como correr una aplicación de streamlit. El archivo se encuentra bajo la carpeta `Identificacion-De-Voces -> Src -> Demo`,  bajo el nombre [StreamlitDemo.ipynb](Identificacion-De-Voces/src/Demo/StreamlitDemo.ipynb)

Para correr la aplicación como se debe se necesitan 3 celdas.

1. la primera para obtener las credenciales para correr la aplicación. A continuación se muestra el comando que se necesita para obtener las credenciales. El resultado de esta celda deberá copiarse para poder correr la aplicación. 

```bash
!wget -q -O - ipv4.icanhazip.com
```

2. La segunda para crear el archivo.py que será utilizado por streamlit para crear la aplicación como tal. Antes de pasar al siguiente paso, es necesario cambiar las direcciones en la que estan guardados cada uno de los modelos además, del "Scaler". A continuación se muestra donde se pueden cambiar cada una de las direcciones.

````python
path_Autogluon = "/content/drive/My Drive/ProyectoTesis/Autogluon/Modelos2"
path_LSTM = "/content/drive/My Drive/ProyectoTesis/LSTM/LRModelHistories.pkl"
path_svm_kernels = "/content/drive/My Drive/ProyectoTesis/SVM/Streamlit/"
path_scaler = "/content/drive/My Drive/ProyectoTesis/Scaler.pkl"
````

3. La tercera que servira para correr el puerto local donde se podrá observar la aplicación. A continuación se muestra el comando para poder correr la aplicación en el puerto especificado. 
````bash
!streamlit run app.py & npx localtunnel --port 8501
````
El resultado de esta celda mostrará un link, al abrir el link se pediran las credenciales que fueron copiadas. Al pegarlas y darle enter se abrirá la aplicación en la ventana y se podrá utilizar tal y como se muestra en el video del demo. 

#### **Datos importantes para el funcionamiento correcto de la aplicación**
- Al ingresar audios, estos audios deben ser de exactamente **2 segundos**.
- Los audios ingresados deben estar en formato **.flac** ya que los modelos fueron entrenados en ese formato y funcionaran mejor de esa manera. 
- Se recomienda utilizar **Google Colab** ya que todo esta configurado para que pueda ser utilizado en ese ambiente. Además, ayuda a que los modelos funcionen de manera rápida y eficiente al tener más poder computacional.

#### 4. **Instrucciones para ejecutar tests o scripts adicionales.**

Si se desea revisar los modelos o bien volver a entrenar los modelos, se debe utilizar los datos especificados anteriormente en la descripción. Es decir el conjunto de datos DF de la competencia ASVspoof 2021. Antes de poder ser utilizados, se deben realizar ciertas modificaciones al conjunto de datos. 

1. Se deben utilizar los audios de de 2 a 4 segundos de duración. 
2. Una vez se tienen los audios, se deben cortar todos a una duración de 2 segundos para poder establecer un estándar.
3. Sin este conjunto de audios y sin estas especificaciones, no se podrán correr los archivos donde se realizó la creación de los modelos. Al menos, no se podrán correr en su totalidad o bien, serán inútiles debido a que no se tienen datos para trabajar. Por otro lado, existen pasos en los archivos en los que algo sobreescribe a otra cosa. Por lo tanto, no se recomienda utilizar los archivos como tal para correr todo y más basarse en la lógica implementada y las características de los modelos utilizadas para llevar a cabo este trabajo. Por último, para cada audio hay que extraer características con la librería ***Librosa*** tal y como se muestra en el archivo de demo.

**Cabe mencionar que el propósito de este trabajo no fue realizar una aplicación ni establecer código para su reutilización sino sentar pautas sobre qué modelos o métodos funcionan mejor para identificar voces generadas por IA.**

### **Demo**
El video demostrando el demo de la aplicación puede observarse en:
 `Identificación-de-voces -> demo` bajo el nombre **[demo.mp4](Identificacion-De-Voces/demo/demo.mp4)**

### **Informe Final**
El informe final con lo hallado en el trabajo de graduación puede encontrarse en: `Identificación-de-voces -> docs` bajo el nombre **[InformeFinal.pdf](Identificacion-De-Voces/docs/InformeFinal.pdf)**

