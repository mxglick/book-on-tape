# books-on-tape
Books On Tape: Author Classification

# Books On Tape: Author Classification

**Introduction**
Literary authors have a wide variety of styles, contexts, and characters they describe in their works. Many of these styles are repeatable, demonstrating identifiable patterns across their bodies of work. These styles can evolve over time, changing as the lives of the authors themselves evolve. 

**Project Goals**
Your mission is two-fold. First, you will use Amazon Transcribe to generate text files from books on tape recordings. Second, you will use those text files to build a machine learning model that can recognize the difference between two different authors at similar points in historical time: Jane Austen and Charles Dickens. 

**Data sources**
There are many sources of literature in the public domain, and books that are recorded for free usage. Here is one option: 
-http://www.openculture.com/freeaudiobooks 

Download two audio files, one from both Jane Austen and Charles Dickens. Make sure to select MP3 formats, because you will run a Transcribe job with those files. For now, select only one file. You'll break this into your train and validation sets. When you're ready to test your final model, you'll download an additional book from both authors, run it against your models, and attempt to get an accurate prediction. 

Store these downloads in an S3 bucket that your team has access to. 

**Machine Learning Method**
For classification, there are a wide variety of options available to you. The easiest way to get started in text classification is using the SageMaker built-in algorithm, BlazingText. For a deeper dive on BlazingText, make sure to read the SageMaker documentation's introduction to the algorithm, specifically the 'How it works' section. 

 When you get responses from the Transcribe job, you will need to determine what length of document you use to train the model. This means that you will need to format the Transcribe results into a both data type that BlazingText can read, and a data type that intuitively lends itself well to the author classification problem. You might do this sentence-by-sentence. You also might do this chapter-by-chapter. Make your selection first for ease-of-use, and as your project develops enhance your feature engineering strategy as necessary.

**Presenting Results**
In particular, we are most interested in understanding which of your methods lead to the best model performance. How will you evaluate your model? Does a larger variety of data lead to a better model, or does a different feature engineering strategy? How would you deploy this into production, and what would your entire architecture look like? 


# Questions to Evaluate a Machine Project 

This set of questions can be used during a machine learning course that introduces technical people who did not previously have a background in ML, and helps them understand if their project is well designed according to machine learning standards.

## Infrastructure

* What is the time to train your model? Can you use streaming data to reduce the amount of time to train? Can you split over multiple instances to reduce the time to train?
⋅⋅* PENDING

* What infrastructure are you using to train your models? Is it the lowest possible cost? Have you considered using GPU's to lower your train time?
⋅⋅* PENDING

* Where are you storing your data; is that the best solution?
⋅⋅* S3 Bucket for different formats of the data and preprocessing

* What devops framework do you have to continuously integrate changes as you make them?
⋅⋅* PENDING

* Where are you developing your model, and is it the best choice for your scenario?
⋅⋅* PENDING

## Conceptual

* Does the data that you're using reflect the real world?
⋅⋅* Yes, similar POC currently doing on the job
* What actually impacts the real world prediction problem, and is that in your data set?
⋅⋅* PENDING


## Data transformation

* Did you normalize your data?
⋅⋅* Converting

* Did you randomly shuffle your data?
⋅⋅* Yes, see notebook python code

* Did you remove any outliers for your data?
⋅⋅* Yes, see notebook python code

* How did you handle missing or nonsensical values in your data?
⋅⋅* No missing data as each data set is a sentence from audio file

* How are you handling any sequential elements of your data set?
⋅⋅* N\A

* Did you remove any bias from it? Have you thought about the ethical implications of your machine learning system, and the fact that the data set itself you are using is potentially biased?
⋅⋅* N\A

* In the case of transfer learning, does your data match the model's input expectation (eg. image size, image format, color-correction, etc)
⋅⋅* N\A

## Method

* Which model did you select, and why?
⋅⋅* Classification as I want to do labeling of each sentence from the book

* How are you evaluating your model?
⋅⋅* PENDING

* Is your model overfitting, and what are you doing to counteract that?
⋅⋅* PENDING

* What are the limitations of your model, and what are its strong points?
⋅⋅* PENDING

* What are the guardrails on the your model performance metrics? What is the minimum and maximum accuracy you expect to achieve?
⋅⋅* PENDING
