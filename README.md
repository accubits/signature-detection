# Signature Detection

## Requirements
1. Python 3.6
2. tensorflow v.1.7.0
## Training the model
Prepare the training dataset by segregating the images to categories, real or fake in this case. The folder structure looks like below.

  
      ├── tf_files          
      │   ├── signatures   
      │       ├── real      
      │       ├── fake            
      └── ...
      
To begin the training process, execute the following script,

```
python -m scripts.retrain \
--bottleneck_dir=/tf_files/bottlenecks \
--model_dir=/tf_files/inception \
--output_graph=/tf_files/retrained_graph.pb \
--output_labels=/tf_files/retrained_labels.txt \
--image_dir /tf_files/signatures
```
## Testing the model
To test the model run,
```
python -m scripts.label_image --graph=tf_files/retrained_graph.pb --image=< path to test image>
```
