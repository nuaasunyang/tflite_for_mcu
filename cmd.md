## Step1、训练模型
train.py -> 生成*.tflite 的flatbuffer序列化文件

## Step2、通过tflite的py接口验证模型有效性
evaluate.py
需要编译interpreter_wrapper_pybind.so,这借助bazel来编译
bazel build //tensorflow/lite/micro/python/interpreter/src:tflm_runtime

## Step3、通过调用tflite的Cpp接口来使用模型
make -f tensorflow/lite/micro/tools/make/Makefile hello_world
需要修改tflite_micro/tensorflow/lite/micro/examples/hello_world/Makefile.inc中的模型路径

## 剩余工作
交叉编译tflite的cpp库