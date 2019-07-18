"# tennis_detection" 

create tfrecord by imagenet data:

```
python .\models\research\inception\inception\data\process_bounding_boxes.py data\Annotation\ > data\tennis_ball.csv
python .\models\research\inception\inception\data\build_imagenet_data.py --train_directory=.\data\train --validation_directory=./data/validation --output_directory=.\data\tfrecords\ --bounding_box_file=.\data\tennis_ball.csv --labels_file=.\data\tennis_labels.txt --imagenet_metadata_file=.\data\tennis_metadata.txt --train_shards=1 --validation_shards=1 --num_threads=1
```

run on windows
```
python .\models\research\object_detection\legacy\train.py --logtostderr --train_dir=.\output\ --pipeline_config_path=.\data\faster_rcnn_resnet101_tennis.config
```

export model
```
python .\models\research\object_detection\export_inference_graph.py --input_type=image_tensor --pipeline_config_path=.\data\faster_rcnn_resnet101_tennis.config --trained_checkpoint_prefix=output\model.ckpt-0 --output_directory=output
```