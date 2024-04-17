# **Taller 9 - Large Language Model**
### *Hecho por Ricardo Pulido Renteria*
---

En este taller, se trabaja con Python y la API de OpenAI con el fin de crear un prompt donde hacer nuestras consultas, para más adelante utilizar una base de datos vectorizada de Pinecone para brindar un contexto propio para obtener resultados personalizados sin hacer pública nuestra información.

## **Descarga y ejecución**

Para poder ejecutar este proyecto, el cual se ejecutará en tu ambiente local por fines de desarrollo y pruebas, debes contar con algunos elementos que serán indicados a continuación.


## **Prerequisitos**

La ejecución de este proyecto requiere de:
- `Python (3.11 o superior)`
- `pip (24 o superior)`
- `Conexión a internet`


## **Instalación**

Para poder trabajar con el proyecto, clonamos el repositorio de GitHub.

```bash
git clone https://github.com/RicardoPR17/arep-taller9.git
```
o puede descargarlo en formato zip y descomprimirlo. Luego, se deben ejecutar los siguientes comandos:

  1. Acceder al directorio del proyecto usando el comando 
```bash
cd arep-taller9
```
  2. Una vez dentro del directorio del proyecto general, accedemos a un entorno virtual con el siguiente comando según si es CMD o PowerShell
```cmd
venv\Scripts\activate.bat
```
```powershell
venv\Scripts\Activate.ps1
```
En MacOS y Linux se usaría el siguiente comando
```bash
source myvenv/bin/activate
```

  3. Instalamos las dependencias con el comando
```bash
pip install -r 'requirements.txt'
```

Hecho esto, estaremos listos para ejecutar el proyecto.    

## **Ejecución**

Para ejecutar nuestro proyecto, debemos ejecutar cada uno de los archivos. Iremos pasando por ellos a medida de la muestra, en cada caso requerimos que el API key de OpenAI y de Pinecone sean válidas y sigan activas.

## **Uso**

Para utilizar estos servicios, se requiere de un API key válido y con créditos de OpenAI. Por ello, contar con una cuenta en OpenAI y para el final con la base de datos vectorizada se requiere de una cuenta de Pinecone.

## **Pruebas**

A continuación se muestran los resultados de las ejecuciones de los diferentes archivos creados en el proyecto.

+ *firstProgram.py*

![first](<Imágenes README/first.png>)

Aquí, vemos que al consultar directamente a ChatGPT por medio de crear una conexión con su API. En este caso, preguntando por el core de la teoría de ciencia de Popper.

+ *LLMMemoryDB*

![LLMMemoryDB](<Imágenes README/LLMMemoryDB.png>)

Aquí, en el código se utiliza como contexto la información de un repositorio de GitHub. Con la información que este contiene, se procede a hacer una consulta a ChatGPT utilizando el contexto obtenido con el fin de obtener un resultado personalizado sin necesidad de exponer nuestra información de forma pública para ser usada por el modelo. Dado que el resultado se ve cortado en la imagen, a continuación se copia dicha respuesta:

>page_content='LLM Powered Autonomous Agents\n    \nDate: June 23, 2023  |  Estimated Reading Time: 31 min  |  Author: Lilian Weng\n\n\nBuilding agents with LLM (large language model) as its core controller is a cool concept. Several proof-of-concepts demos, such as AutoGPT, GPT-Engineer and BabyAGI, serve as inspiring examples. The potentiality of LLM extends beyond generating well-written copies, stories, essays and programs; it can be framed as a powerful general problem solver.\nAgent System Overview#\nIn a LLM-powered autonomous agent system, LLM functions as the agent’s brain, complemented by several key components:\n\nPlanning\n\nSubgoal and decomposition: The agent breaks down large tasks into smaller, manageable subgoals, enabling efficient handling of complex tasks.\nReflection and refinement: The agent can do self-criticism and self-reflection over past actions, learn from mistakes and refine them for future steps, thereby improving the quality of final results.\n\n\nMemory' metadata={'source': 'https://lilianweng.github.io/posts/2023-06-23-agent/'}

>page_content='Memory\n\nShort-term memory: I would consider all the in-context learning (See Prompt Engineering) as utilizing short-term memory of the model to learn.\nLong-term memory: This provides the agent with the capability to retain and recall (infinite) information over extended periods, often by leveraging an external vector store and fast retrieval.\n\n\nTool use\n\nThe agent learns to call external APIs for extra information that is missing from the model weights (often hard to change after pre-training), including current information, code execution capability, access to proprietary information sources and more.' metadata={'source': 'https://lilianweng.github.io/posts/2023-06-23-agent/'}

>Task decomposition is a technique used to break down complex tasks into smaller and simpler steps. This approach helps agents to plan and execute tasks more efficiently by dividing them into manageable subtasks. It can be done through prompting techniques like Chain of Thought or Tree of Thoughts, or with task-specific instructions.

+ *RAGPinecone*

![RAG](<Imágenes README/rag.png>)

Para este último ejercicio, en un archivo llamado "_paper.txt_" se copia el contenido del paper realizado para el proyecto de AREP. Con este contenido, se crea una base de datos vectorizada en Pinecone (usando un API key que nos brinda al crear una cuenta) para posteriormente consultar sus vectores y usar dicho contenido para la consulta sobre Google Flue Trends.



## **Construido con**
  - [pip](https://pypi.org/project/pip/) - Administrador de dependencias
