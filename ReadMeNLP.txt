We highly recommend you to read this file in a text editor like VS Code or Notepad++

Enes Sapan 22050151002
Dilara Tosun 20050111041
İrem Erdöl 21050111055

Installation of Tensorflow, fasttext and polyglot:
    Unsuccessful attempts:
        For Ubuntu:
            Firstly we want to say that we tried everything that said below in Ubuntu 18.04, 20.04, 22.04 and 24.04 (dual boot).

            With Anaconda or Miniconda:
                Created a new environment just for tensorflow.
                Activated the spesific environment and begin to install libraries. 
                Here's some commands for example:

                    pip install polyglot nltk spacy
                    pip install pandas matplotlib
                    pip install polyglot numpy morfessor pycld2 pyicu

                These commands all worked some way or another (even if they printed some errors while installing we managed to fix it)

                But when it comes to TENSORFLOW it is somewhat different:
                    Firstly we tried to install tensorflow by:

                        pip install tensorflow

                    Output in terminal said that tensorflow and the related libraries was installed succesfully.
                    But when we tried to import on python there was some errors that said:
                        IT CANNOT FIND GPU RELATED DRIVERS(like CuDNN, Cuda, Cublas etc.)
                    And also another error that said IT CANNOT FIND TENSORRT
                    When we see this firstly we did:

                        pip install tensorflow[and-cuda]

                    Tried version parametered commands as well and nothing changed, surprisingly.    

                    So we checked that if out tensorflow's version and Nvidia driver version are compatible.
                    They were not compatible because the latest Nvidia drivers and the latest tensorflow version.
                    You can check the version compatibilities in here: https://www.tensorflow.org/install/source#gpu.   
                    We tried to install the drivers that are compatible with the latest tensorflow version(2.16.1). It did not work.
                    We tried to downgrade our tensorflow version and also installed the compatible drivers with it. 
                    Tensorflow versions that we tried: 2.15.0, 2.14.0, 2.14.1, 2.13.0, 2.12.0, 2.11.0, 2.10.0, 2.9.0, 2.8.0 and 2.7.0
                    We even tried to "just run tensorflow on CPU, not on GPU" but it continued to give similar errors as well.

                    So no Ubuntu version was the solution as you can see.

            For Windows:
                We tried exact same things but in VMware and WSL2. Got similar errors and results.

                Anaconda on Windows:
                    We tried to create an environment and install libraries from Anaconda Navigator.
                    It gave us the similar errors as in Ubuntu.        
                     
    Successful attempts:
        For Windows:
            Installed python 3.10 (not with anaconda just python itself)
            Then we created a folder and opened it on Visual Studio Code. 
            Created new .ipynb file and opened it again in VS Code. 
            Opened a new terminal (Git Bash). installed environment packages by:
                
                pip install virtualenv

            And then created a new environment by:
                
                python -m venv myenv or python3.10 -m venv myenv

            Also activated the environment with:
                
                cd myenv/Scripts/
                ./activate

            Installed libraries like numpy and pandas with pip. the command that we installed the tensorflow with is:
                
                pip install tensorflow==2.14.1

            In windows side tensorflow was working after these steps but we could not find any logical way to install polyglot and fasttext. 
            So we decided to install and use them in Google Collab since we definitely could not implement it in Ubuntu nor Windows.

        Google Collab:
            We just installed with pip(or !pip or pip3 etc.) and import the libraries and it works. Incredible isn't it?      

Files and what they do:
    For the tasks 2, 3 and 4:
		Task 2:
			Firstly we dropped the sentences that are null. Then we imported Azerbaijani from polyglot.
			After that we dropped every sentence that are not accepted as Azerbaijani by polyglot.
			With using matplotlib we visualized the distribution of scores and upvotes.
			
		Task 3:
			We cleaned the emojis we forgot to remove in task 2. 
			We splitted sentences to train and test data by 80% and 20%.
			
		Task 4:
			Polyglot, spacy and NLTK was used for tokenizing the sentences into words. 
			Between them polyglot and spacy were the best ones, we could not see much difference between them.
			The words were more or less same for the two. Polyglot was slightly better if we have to compare them.
			For the NLTK there were some null and meaningless words. So it was a little bit worse than the other two.

	For the tasks 5, 6 and 7:
		Task 5:
			We created a baseline model using the RNN with GRU layers.
			We implemented the pre-trained models and changed our codes slightly based on them.
			After that we tried each activation functions one-by-one in different codes and analyse the outputs based on them.
		
		Task 6:
			While we are working with the task 5, we simultaneously calculated the loss and accuracy for both each epochs of training and epochs of testing.
			For analyse, the most up-front things were ReLu and tanh having 80% accuracy at most and 50% loss at least.
		
		Task 7:
			For visualize we used Matplotlib and TSNE.