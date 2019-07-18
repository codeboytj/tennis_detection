"# tennis_detection" 

create tfrecord by imagenet data:

```
python .\models\research\inception\inception\data\process_bounding_boxes.py data\Annotation\ > data\tennis_ball.csv
python .\models\research\inception\inception\data\build_imagenet_data.py --train_directory=.\data\train --validation_directory=./data/validation --output_directory=.\data\tfrecords\ --bounding_box_file=.\data\tennis_ball.csv --labels_file=.\data\tennis_labels.txt --imagenet_metadata_file=.\data\tennis_metadata.txt --train_shards=1 --validation_shards=1 --num_threads=1
```