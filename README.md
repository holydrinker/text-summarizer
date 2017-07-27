# text-summarizer
A Python Framework for Extractive Text Summarization.
This work is the project part of the course "Natural Language Processing" from University of Bari (Master Degree in Computer Science).

The core of the framework is a [centroid-based text summarization algorithm](http://www.aclweb.org/anthology/W/W17/W17-1003.pdf).
The framework has been deployed by a REST service /getSummary.
The project was supervised from [Gaetano Rossiello](http://www.di.uniba.it/~swap/index.php?n=Membri.Rossiello), [Giovanni Semeraro](http://www.di.uniba.it/~swap/index.php?n=Membri.Semeraro), [Pierpaolo Basile](http://www.di.uniba.it/~swap/index.php?n=Membri.Basile).

I work on this project with my classmate (and dear friend) [Giovanni Mastroscianni](https://www.linkedin.com/in/giovanni-mastroscianni-502004106/).

## Configuration
You need a word2vec model.
I post here two link to download a english model and an italian model:
[italian](https://www.dropbox.com/s/tscnk0f436983z7/w2v-model-it.rar?dl=0)
[english](https://www.dropbox.com/s/wlp1srqomn0agwd/w2v-model-en.rar?dl=0)
Download a model.bin a place it in the main project directory. Rename it "model".

The project is set up to work on italian text and italian model. The model strongly influence the configuration of the framework because we need to process the text to summarize with the same pipeline that was processed the corpus used for model's training.
So, if you want to use english model, when summarizer is created (in this work is istantiated in the REST service [summarizer_restful/views.py](https://github.com/holydrinker/text-summarizer/blob/master/summarizer_restful/views.py)) set the constructor's argument ```remove_stopword``` to ```True```.

## Run
To run this framework just move with your terminal in the project directory and type (you need python installed and all the dependencies in the [requirements file](https://github.com/holydrinker/text-summarizer/blob/master/requirements.txt)) ```python manage.py runserver 8001```.

Now the server is running!

Go to the [client directory](https://github.com/holydrinker/text-summarizer/tree/master/simple-client-for-a-demo) and open the index.html file for a demo :)
