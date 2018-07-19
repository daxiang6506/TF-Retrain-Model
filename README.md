# Tensorflow Retrain Model with Python3
迁移学习，重新训练模型并输出 `serving model`

## 参考
* [github](https://github.com/googlecodelabs/tensorflow-for-poets-2)  

## Run
* 下载代码
  [github](https://github.com/daxiang6506/TF-Retrain-Model)
* 建立环境
  ```
  docker run -it -p 8881:8888 --link model-server -v $(pwd):/notebooks daxiang6506/tensorflow:1.8.0-py3 /bin/bash
  ```
* 开始训练
  ```
  python3 -m retrain \
    --bottleneck_dir=tf_files/bottlenecks \
    --how_many_training_stelps=100 \
    --model_dir=tf_files/models/ \
    --output_graph=tf_files/retrained_graph.pb \
    --retrained_model=retrained_model/004 \
    --output_labels=tf_files/retrained_labels.txt \
    --image_dir=tf_files/eye/
  ```
  >每类数量不能太少，否则出错

## 修订
* 与原版本相比，增加了输出为 `serving model` 的功能
