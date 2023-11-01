Katara is an ecosystem with Geoprocessing, 3D Map Visualization and a Large Language Model (Llama 2).

At first glance, it's just a chat with a globe, but the ecosystem goes far beyond what you can see.

The entire ecosystem is divided into five main layers: **Geoprocessing**, **Frontend**, **Backend**, **AI** (Large Language Model - Llama 2), **Storage** (LLAMA 7B, Water Datasets).

Click on the [link](https://github.com/project-katara/.github/blob/main/assets/katara.png) for the complete flowchart of the katara ecosyst

<img style="margin-left: auto; margin-right: auto; width: 100%;" src="/assets/katara.png">

## Artificial Intelligence (AI) - LLAMA

Our LLaMa was created using a pre-processed model called Llama-2-7b-Chat-GGUF. Basically, it converts Llama 2 to a standard called GPT-Generated Unified Format.

We used the 7 billion parameter model, which is the repository of the enhanced 7B model, optimized for dialogue use cases and converted to the Hugging Face Transformers format.

<img style="margin-left: auto; margin-right: auto; width: 100%;" src="/assets/llama.png">

Our model has five main parts:

**EMBEDDINGS**: We used [hkunlp/instructor-large](https://huggingface.co/hkunlp/instructor-large).

[Embeddings](https://www.cloudflare.com/learning/ai/what-are-embeddings/) are representations of values or objects like text, images, and audio that are designed to be consumed by machine learning models and semantic search algorithms. They translate objects like these into a mathematical form according to the factors or traits each one may or may not have, and the categories they belong to.

Essentially, embeddings enable machine learning models to find similar objects. Given a photo or a document, a machine learning model that uses embeddings could find a similar photo or document. Since embeddings make it possible for computers to understand the relationships between words and other objects, they are foundational for artificial intelligence (AI).

**DB** - Database Object responsible for saving training data in memory so that it can be consumed later by the model itself.

**RETRIEVER** - Also known as [Retrieval-Augmented Generation](https://research.ibm.com/blog/retrieval-augmented-generation-RAG) is an AI framework for retrieving facts from an external knowledge base to ground large language models (LLMs) on the most accurate, up-to-date information and to give users insight into LLMs' generative process.

**LLM** - Large Language Models are a core component of [LangChain](https://python.langchain.com/docs/get_started/introduction). LangChain does not serve its own LLMs, but rather provides a standard interface for interacting with many different LLMs.

**RetrievalQA** - [Retrieval Question-Answering (QA)](https://medium.com/data-and-beyond/retrieval-qa-with-prompt-no-api-46dd6c9d06f8) is an impressive technology that excels at extracting answers from a given context.

## Geoprocessing

Our geoprocessing was built using the open source GeoServer technology, which was consumed using the [_Web Map Service_](https://en.wikipedia.org/wiki/Web_Map_Service) communication protocol.

Our GeoServer server has been loaded with maps from various sources, all with their appropriate licenses respected.

<img style="margin-left: auto; margin-right: auto; width: 100%;" src="/assets/geoprocessing.png">

#### Maps:

[_Global River Classification_](https://www.hydrosheds.org/products/gloric) (GloRiC): The Global River Classification (GloRiC) provides river types and sub-classifications for all river stretches contained in the HydroRIVERS database.

[_HydroLAKES_](https://www.hydrosheds.org/products/hydrolakes) (Lake Polygons): Aims to provide the shoreline polygons of all global lakes with a surface area of at least 10 ha.

[_HydroRIVERS_](https://www.hydrosheds.org/products/hydrorivers) (HydroRIVERS): represents a vectorized line network of all global rivers that have a catchment area of at least 10 km² or an average river flow of at least 0.1 m³/sec, or both. HydroRIVERS has been extracted from the gridded HydroSHEDS core layers at 15 arc-second resolution

[_HydroLAKES_](https://www.hydrosheds.org/products/hydrolakes) (Lake pour points): Aims to provide the shoreline polygons of all global lakes with a surface area of at least 10 ha.

[_General Bathymetric Chart of the Oceans_](https://www.gebco.net) (GEBCO): Aims to provide the most publicly available bathymetry data sets for the world’s oceans.

[_Earth Observatory_](https://earthobservatory.nasa.gov/global-maps/MYDAL2_M_SKY_WV) (Water Vapor): The Earth Observatory is part of the EOS Project Science Office at NASA Goddard Space Flight

[_Global Imagery Browse Services_](https://www.earthdata.nasa.gov/eosdis/science-system-description/eosdis-components/gibs) (GIBS): GIBS provides quick access to over 1,000 satellite imagery products, covering every part of the world. Most imagery is updated daily—available within a few hours after satellite observation, and some products span almost 30 years. The satellite imagery can be rendered in your own web client or GIS application.

[_Socioeconomic Data and Applications Center_](https://sedac.ciesin.columbia.edu/) (SEDAC):
A Data Center in NASA's Earth Observing System Data and Information System (EOSDIS) — Hosted by CIESIN at Columbia University

[_Terrestris_](https://www.terrestris.de/en/openstreetmap-wms/):
This service presents the data of the OpenStreetMap-Project in a clear and simple way.

[_Environmental Performance Index_](https://epi.yale.edu/epi-results/2022/component/h2o) (SEDAC):
The 2022 Environmental Performance Index (EPI) provides a data-driven summary of the state of sustainability around the world.

## Backend

Our backend was created with two programming languages, Python and Javascript. It has two parts:

**RestFull API (Python)**: We used the [FastAPI](https://fastapi.tiangolo.com/) framework to create all the communication and documentation between the LLaMa layer and HTTP calls.

The documentation can be accessed from our [Katara LLaMA](https://huggingface.co/spaces/dkdaniz/katara) repository, which is hosted on [huggingface](https://huggingface.co/).

**API Websocket (Javascript)**: We built our [websocket](https://www.npmjs.com/package/ws) using [nodejs](https://nodejs.org/en). It is responsible for managing all the classrooms between teachers and students.

<img style="margin-left: auto; margin-right: auto; width: 100%;" src="/assets/backend.png">

## Frontend

Our Frontend was built to provide the best experience for students and teachers on desktop or mobile.

<img style="margin-left: auto; margin-right: auto; width: 100%;" src="/assets/frontend.png">

It is divided into three main parts:

**Globe**: Responsible for rendering all the maps for the user.

**Classroom**: Responsible for integrating teachers and students in a single shared room, so everyone can follow answers and questions in real time.

**Student**: Responsible for interacting with our LLaMa service, providing inputs (questions) and consuming outputs (answers).

## Storage

Our AI was trained with data provided by NASA. The training process consisted of a few steps: Data Screening, Data Capture, Data Processing and finally Data Processing by our LLaMa version 2.

The data was taken from the following sources:

#### Internal Data

[LLaMa 2](https://ai.meta.com/llama/): Dataset from Facebook's own model
[Llama-2-7b-Chat-GGUF](https://huggingface.co/TheBloke/Llama-2-7b-Chat-GGUF): Model that uses the GPT-Generated Unified Format

#### External Data

[Earth Observatory](https://earthobservatory.nasa.gov/)
[Environmental Performance Index (EPI)](https://epi.yale.edu/)
[Wikipedia](https://en.wikipedia.org/wiki/Water)
[Climatekids - Nasa](https://climatekids.nasa.gov/)
[Climate - Nasa](https://climate.nasa.gov/)
[Center for Science Education](https://ncse.ngo/)
[Earth Data - Nasa](https://www.earthdata.nasa.gov/)
[HydroSheds](https://www.hydrosheds.org/)
[Food and Agriculture Organization of the United Nations - FAO](https://www.fao.org/home/en)

<img style="margin-left: auto; margin-right: auto; width: 100%;" src="/assets/storage.png">
