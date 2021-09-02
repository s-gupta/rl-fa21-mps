## ECE598SG (Special Topics in Robot Learning)
### Programming Assignment 1
You must do `(A or B) and C`. If you took CS543 / ECE 549 in Spring 2020, you
must do `B and C`. <br/>
A. [Semantic Segmentation](./sseg) <br/>
B. [Character RNN](./char-rnn) <br/>
C. [Linear Quadratic Regulators](./lqr) <br/>

#### Instructions
1. Assignment is due at 11:59 PM on Thursday September 16, 2021.
2. Please see
[policies](http://saurabhg.web.illinois.edu/teaching/ece598sg/fa2021/policies.html)
on [course
website](http://saurabhg.web.illinois.edu/teaching/ece598sg/fa2021/index.html).
3. We will be using [gradescope](https://www.gradescope.com/) for 
submissions and auto-grading. Gradescope entry code is `2R8Z5Y`. Submission instructions:
   1. A single report for all questions in PDF format, to be submitted to
   gradescope (under assignment `MP1`). Please also tag your PDF with locations 
   for each question in the gradescope interface.
   2. Autograded components should be uploaded to the assigment
   `MP1-autograder`. Follow the instructions for each autograded component for
   what should be uploaded. You final submission to the `MP1-autograder`
   assigment should contain **all** components to be autograded for MP1. You
   should upload the following files:
     - `MP1_sseg_predictions.npy`: If completing part A, generation code available in sample code
     - `MP1_char_predictions.npy`: If completing part B, generation code available in sample code
     - `MP1_lqr_solution.py`: Containing your LQR implementation in a class named `LQRControl` (see template)
     - Code for parts A or B, include model definition and training loop.
   3. We reserve the right to take off points for not following submission
   instructions.
4. Problems A. and B. will involve training neural network models. You will
benefit from use of GPUs for these problems. You can access GPUs through
[campus
cluster](http://saurabhg.web.illinois.edu/teaching/ece598sg/fa2021/compute.html),
and also through Google Colab. Please see course website for instructions on
how to use campus cluster. Instructions to use Google Colab can be found below.
5. Lastly, be careful not to work of a public fork of this repo. Make a *private*
clone to work on your assignment. 

#### Google Colab
1. Access https://colab.research.google.com/ and login through for Illinois Google account.
2. Create a new notebook.
3. Select GPU Runtime: `Runtime` > `Change Runtime Type` > `Hardware Accelerator` > `GPU`.
4. You can copy over the starter code into this new notebook, and start development.
5. You can install dependencies by executing `!pip install -r requirements.txt`.
6. For the datasets, you have 2 options:
   1. You can download and unzip the data onto this colab instance (using
   `!wget` and `!tar -xf` commands through the notebook cells. This is likely
   the faster of the two options, though you will have to do this every time
   you open this notebook.
   2. You can copy the data into your Google Drive, and access it as follows.
   This may be slower, but the data will be persistent, so you only need to set
   it up once. 
   ```
   from google.colab import drive
   drive.mount('/content/gdrive/')
   import os
   os.chdir("/content/gdrive/My Drive/path_to_folder")
   ```
7. Keep in mind that you need to keep your browser window open while running
Colab. Colab does not allow long-running jobs but it should be sufficient for
the requirements of this assignment. Colab also likely won't save the state of
your notebooks for too long, so make sure you are saving and downloading models
that you train. 
8. Lastly, Colab might restrict the number of GPU hours you can use, so design
your experiments carefully so as to use your compute time wisely.
