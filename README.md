# SDSSclassifier
A classification wrapper for Sloan Digital Sky Survey.

Queries to the SDSS are formed as SQL commands. This project will allow you to predict an output row of an SDSS query 
to a star, a galaxy or a Quasar. The row must conform to a specification that can be accepted by the machine learning output function.

## createQuery(SQL:SQLquery) -> list[list]

## acceptTrainingResult(csv:SQLresult) -> Bool
Must conform to training result row specification.

## acceptTestingResult(csv:SQLresult) -> Bool
Must conform to testing result row specification.

## csvML(csv:SQLresult) -> list[list] 
Calls ML algo on all rows.

## rowML(row:SQLrow) -> "Star","Quasar","Galaxy"
This must be a multinomial classifier. That is, we pass the row to three binary classifiers, and it spits out the one which is true.
(What happens if more than one is true??)

Training Algorithm:
Linear Perceptron.
Second Order Legendre Polynomial perceptron.
Second Order SVM.
Fail.

## exportToFile(string:file,list[list]:MLcsv) -> null
Sends whatever we discovered to an output csv file.
