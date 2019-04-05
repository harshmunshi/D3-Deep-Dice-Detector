# D3-Deep-Dice-Detector

D3: Deep Dice Detector is an implementation of dice detection and top surface number recognition.

## Data Collection

Collect the dice dataset from different orientation and lighting conditions as depicted below.


<img src="./images/2018-10-08@13-38-29.png" width="320" height="240"> <img src="./images/2018-10-08@16-09-35.png" width="320" height="240">
<img src="./images/2019-01-09@13-46-48.png" width="320" height="240"> <img src="./images/2019-01-09@13-49-52.png" width="320" height="240">

## Data Annotation

Annotate the data using labelImg tool given [here](https://github.com/tzutalin/labelImg).

The annotations are done by me and given in the annoatations folder.

## Converting xml to csv format

The annotations are in xml format, convert it to csv format using the following command

(available under utils folder)

```
$ python xml_to_csv.py
```

## Shuffle the dataset into test and train

Please have a look at the following file

(available under utils folder)

```
$ jupyter notebook split_labels.ipynb 
```

## Convert the data to tfrecords

To create train.record

(available under utils folder)

```
$ python generate_tfrecord.py --csv_input=data/train_labels.csv  --output_path=train.record
```

To create test.record


```
python generate_tfrecord.py --csv_input=data/test_labels.csv  --output_path=test.record
```

NOTE: EDIT LINE 31 of the code according to the classes you have.
