## Windows
### - Labelimg to tfrecords
**The Problem** <br>
Using the labelimg tool ([https://github.com/tzutalin/labelImg](https://github.com/tzutalin/labelImg)) it creates .xml files in the PASCAL VOC format. This must be converted to tfrecord files to be used with the Tensorflow Object Detection API ([https://github.com/tensorflow/models/tree/master/research/object_detection](https://github.com/tensorflow/models/tree/master/research/object_detection)) <br>
**Background** <br>
TF record file types are the the file that tensorflow uses. However, labelimg does not produce tfrecord files meaning we must convert them.

Following this tutorial by Sentdex [https://pythonprogramming.net/creating-tfrecord-files-tensorflow-object-detection-api-tutorial/](https://pythonprogramming.net/creating-tfrecord-files-tensorflow-object-detection-api-tutorial/) we can convert the files

**Solution** <br>
1. Download the files `xml_to_csv.py` and `generate_tfrecord.py` from Datitran's repo - [https://github.com/datitran/raccoon_dataset](https://github.com/datitran/raccoon_dataset), and save it into your _object_detection_ folder. <br> <br>
If you're having trouble downloading them, view them in their raw format by clicking the button labeled _raw_'. Then you can right-   click   the page and click _save-as_ which will prompt you about where you would like to save the file. 

2. Make sure your .xml labels for your training data are inside the folder (you may have to create it) `object_detection/images/train` and your test labels are inside the folder `object_detection/images/test`

3. Edit `xml_to_csv.py` <br>
   From:
   <pre>
   def main():
       image_path = os.path.join(os.getcwd(), 'annotations')
       xml_df = xml_to_csv(image_path)
       xml_df.to_csv('raccoon_labels.csv', index=None)
       print('Successfully converted xml to csv.')
   </pre>  To:
   <pre>
   def main():
       for directory in ['train','test']:
           image_path = os.path.join(os.getcwd(), 'images/{}'.format(directory))
           xml_df = xml_to_csv(image_path)
           xml_df.to_csv('data/{}_labels.csv'.format(directory), index=None)
           print('Successfully converted xml to csv.')
    </pre>

4. Open command prompt (cmd) - with or without a virtual environment - and run `python xml_to_csv.py` <br> If it runs successfully it should say `Successfully converted xml to csv.` 

5. Go to `object_detection/data` and there should be two new .csv files. When opened (in a program like Microsoft Office Excel) there should be data. :tada: Congratulations you have successfully converted .xml to csv. :tada: 

Don't celebrate to early - there's still one more step to go

6. Edit `generate_tfrecord.py` <br>

   <pre>
   # TO-DO replace this with label map
   def class_text_to_int(row_label):
       if row_label == 'raccoon':
           return 1
       else:
           None
   </pre>  
   Where it says `raccoon` you want to replace that with the class that is in your dataset.
   
7. Open CMD in the directory `/object_detection` - using a virtualenv if you want, and run  - `python generate_tfrecord.py --csv_input=data/train_labels.csv --output_path=data/train.record`. The `csv_input` argument is the path to the .csv file that was created earlier. The `output_path` argument is the path to where you want your tfrecord file to be created.

8. If it worked then you should get the message `Successfully created the TFRecords:`.
   If you did get a an error, along the lines of `object_detection\images\P1140753 : The system cannot find the file specified.
; No such file or directory` then that means that you need to edit your .csv file. On the first column - labeled filename, you should go through each row and add a filetype extension - e.g. `.JPG` to the end of what's there.
