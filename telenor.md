### Image
download image and resize to 300x300 pixel. Create folder by category
```
images/cat_0
images/cat_1
images/cat_n
```
take time 5-10hr

10,000 images is enough.

### Prepare
create mapping.txt from exel file

    /kaidee/create_mapping.py


### Build model

1. Create h5 file with

 `mise/collect_states_parallelpy /images  /path/to/output/states`

    **Result:**
    ```
    /path/to/output/states/cat_0.h5
                         /cat_1.h5
                         .
                         .
                         /cat_N.h5
    ```

2. Build model

  `misc/transfer_learning.py /mnt/states/`

  **Result**
  ```
  transfer_classifier_SOMETHING.pb
  ```
  time 5-10hr


## How to run worker with this model
      CUDA_VISIBLE_DEVICES=0 python transfer_classifier.py --classifier /path/to/model/transfer_classifier_epochs_500_batch_2048_ratios_0.8_0.1_0.1_learning_rate_0.0001_hidden_size_512.pb --mapping /path/to/mapping.txt


## Test model
you can check states of model by
  `misc/transfer_stats.py /path/to/model.pb /path/to/states`
