# tennis_detection 

This repository show how to use google drive and google colab to train my tennis detection model.

## directory structure

```
google drive
  |-colab
    |-tennis-detection/
      |-data/
        |-train.record
        |-val.record
        |-tennis_label_map.pbtxt
      |-models/
        |-ssdlite_mobilenet_v2_coco/
          |-output/
          |-pre_training/
          |-training/
            |-pipeline.config
```

Pipeline.config, label map, train.record and val.record are files we need to train this model.
