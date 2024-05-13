# Chat with videos locally using Ollama.

This is a demo Artificial Intelligence **"ChatWithVideo"** project created for Individual Profiling.

<div style="display: flex;">
    <img src="https://i.gyazo.com/868c529a968903cca5bcd17c6885b50d.png" alt="ollama" width="200"/>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/0a/Python.svg/640px-Python.svg.png" alt="python" width="200"/>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/Jupyter_logo.svg/1200px-Jupyter_logo.svg.png" alt="jupyter_notebook" width="200"/>
    <img src="https://d1muf25xaso8hp.cloudfront.net/https%3A%2F%2Fmeta-q.cdn.bubble.io%2Ff1703662981765x545641909212891260%2Fopenai-icon-2021x2048-4rpe5x7n.png?w=&h=&auto=compress&dpr=1&fit=max" alt="whisper_openAi" width="200"/>
</div>



### Steps to run the project:

1. Clone the repository “ChatWithVideos” containing Python notebooks and JSON files using the below URL:

        https://github.com/karanghai9/ChatWithVideos.git

2. Once cloned locally, you may have a look at the “TranscriptsGenerator.ipynb” file to understand how we have generated the transcripts for all the lectures in  the “segments_updated.json” file.

    Please note: There is no need to run this file locally until you want to generate further transcripts for new lectures.

3. Now another important file you might find is “WorkingDocChatBackup.ipynb”, where the logic of our chatbot exists. The code written in this file is performing the below operations:
    1. Taking the “segments_updated.json” file as input and creating chunks of size 1024 each, in the file named “chunks_updated.json”.
    2. Creating the embeddings of our chunks and saving them in FAISS vectorstore.
    3. Taking a default system prompt to act like Karan, a student of TH Bingen University.
    4. Provide an endpoint along with a basic interface to get a query from the user and responding it with the model of our choice.

4. Download the ollama application to plug any of the GPT models of your choice with our code. You may find the list of available models here: 

        https://ollama.com
    Once installed ollama, open the application and then run the following command in the terminal:

        ollama run tinyllama:chat
    The above command will download and then run the mistral model locally. You should see something like this:

    You may choose a different model based on your preference, from the collection of models in ollama library: 

        https://ollama.com/library
    Since, at the moment we are more interested in fine-tuning the model rather than running it directly in our command prompt, we must exit     from the currently running model using the command: 

        /bye
    Please note: Above step does not mean that you should also exit from the ollama application.
    Ollama must still be serving on: 

        http://localhost:11434/
5. Now, run all the cells of the “WorkingDocChatBackup.ipynb” notebook and change the model name to whichever model you have downloaded from        ollama in the RetrievalQA step.

6. At last, you might have the flask code where you have the choice of 2 cells:
    To run either the UI (uncommented one) or the endpoint only(commented cell). 
    Based on whichever cell you choose to run, you will find a URL where your app is being served.
    
7. In the previous step if you have chosen to run the UI cell, you should be able to see the basic UI.

8. Else if you have chosen to run only the endpoint, you may test it using the Postman.
