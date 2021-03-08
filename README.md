# label_and_generate

Firstly, you clone labelImage in https://github.com/tzutalin/labelImg to label for your images with format you want such as .txt, .xml. And download https://github.com/tensorflow/models/tree/master/research/object_detection

LabelImg saves a .xml file containing the label data for each image. These .xml files will be used to generate TFRecords, which are one of the inputs to the TensorFlow trainer. Once you have labeled and saved each image, there will be one .xml file for each image in the \test and \train directories.

Then you run xml_to_csv to change xml format into csv format for trainning SSD Mobinet models.

# Create train data:
 python generate_tfrecord.py --csv_input=data/train_labels.csv  --output_path=train.record

# Create test data:
  python generate_tfrecord.py --csv_input=data/test_labels.csv  --output_path=test.record

  python generate_tfrecord.py --csv_input=data/test_labels.csv  --output_path=data/test.record --image_dir=images/
