### B. Character RNN

In this problem, you will experiment with recurrent neural networks (RNN). RNNs
are basic memory models that can store information, and are a popular choice
for dealing with variable length sequence of input and outputs. Not too long
ago, RNN based models did very well on a number of language tasks, but they
have now been taken over by attention-based models. Yet, RNN based models are
used in a number of paper that we will read in this course, and so it is
worthwhile to learn more about them through this assignment.

We will be building a character-level language model using RNNs. A language
model, given some context, makes predictions for what will come next. We will
build a character-level language model, that given the previous characters will
predict the next character.

#### Data
We will work with a dataset of paper titles and abstracts from arXiv in the
general area of robot learning (selected from ([1](#references))). We have
`2485` papers for training, and `532` for validation and `10000` strings
testing. We have provided a basic dataloader that you can build upon.  Data can
be downloaded from
[here](https://saurabhg.web.illinois.edu/teaching/ece598sg/fa2021/mps/mp1/arXiv.zip).
Download the file into the `data` folder, and untar it to obtain a folder
called `arXiv`. It should have files `train.txt`, `val.txt` and
`test_prefix_strings.torch` containing paper titles and abstract for the
different splits, and the test strings.

#### Starter Code
We also provide a basic model (that predicts the next character given the
current character), and also a training loop that shows how to use pytorch for
setting up training and validation. Validation code computes the negative
log-likelihood (NLL) of predictions on the validation set, and we will use that
to measure how well your model is doing. We also have code that uses the
learned model to generate abstracts from titles, and you will also inspect the
quality of your generations. 

#### What you need to do
1. **Develop your model [8 pts]**: Design recurrent models for solving this
   task. You will have to implement another class analogous to `TwoGram` class
   provided in the starter code. You can refer to online tutorials and research
   papers, but don't copy someone else's code.
   
   You should experiment with at least two, if not more of the following:
   1. different variants (LSTMs vs GRU vs RNNs), 
   2. size of hidden layers, 
   3. number of hidden recurrent layers. 
   4. other training hyper-parameters (learning rate, batch size, etc.)
   
   In your report, carefully document and report the major things you try, by
   noting the key architectural details, design rationale, and the impact on
   training plots and validation metrics.  You should also include the relevant
   training plots and validation metrics.
   
   For reference, our very basic implementation is able to do 1 training epoch
   in under 20 seconds, and achieves a NLL of 1.0 in under 40 minutes of
   training. At the very least your implementation should achieve as low 
   a NLL on the validation set, but you may be able to do substantially
   better with more training, and trying out alternate architectures.

2. **Inspect generations from your model [2pts]**. With your best model, use
`generate_abstract` function to generate abstracts for titles in the validation set.
Pick out some interesting examples that show where the model works well, and
where it doesn't, and characterize the error modes that your observe. 

3. **Test set performance [5pts - autograded]**: The starter code produces
predictions on the test set, writing to the file `MP1_char_predictions.npy`.
After you have finished developing your model, generate predictions using this
code to evaluate against the ground truth labels on gradescope. Upload the file
`MP1_char_predictions.npy` to the `MP1-autograder` assignment on gradescope to
have it graded. Additionally, with your submission, upload your code (model
definition and training loop). Make sure to include all auto-graded components
from all components of MP1 for your final submission.

#### References
1. https://www.kaggle.com/Cornell-University/arxiv
