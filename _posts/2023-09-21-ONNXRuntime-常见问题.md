---
published: false
layout: post
title: "优化篇-常见问题"
categories: 我的AI新书
banner:
  video: https://vjs.zencdn.net/v/oceans.mp4
  loop: true
  volume: 0.8
  start_at: 8.5
  image: https://bit.ly/3xTmdUP
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
excerpt: "优化篇-常见问题"


---

pytorch支持保存整个模型，这样就不需要代码了。
# Save the entire model to PATH
torch.save(model, PATH)

# Load the model from PATH and set eval mode for inference
model = torch.load(PATH)
model.eval()


也可以只保存参数，这样需要重新定义模型，然后让模型去加载参数。


TorchScript：
C++推理
# Export to TorchScript
script = torch.jit.script(model, example)

# Save scripted model
script.save(PATH)


#include <torch/script.h>

...

  torch::jit::script::Module module;
  try {
    // Deserialize the ScriptModule
    module = torch::jit::load(PATH);
  }
  catch (const c10::Error& e) {
    ...
  }

...
ONNX推理：

通过Netron工具查看 inputs and output node names and shapes

ONNXRuntime是由C++开发的，有C++, Python, C#, Java, Javascript, Julia, and Ruby接口。

可以运行在Linux, Mac, Windows, iOS, and Android。


神经网络推理优化constant folding
Constant folding是一种编译器优化技术，它可以在编译时而不是运行时识别和计算常量表达式。常量表达式是指那些只包含常量值或者已知值的变量的表达式。例如，2 + 3 * 4就是一个常量表达式，它的值在编译时就可以确定为14。编译器可以用14来替换这个表达式，从而减少运行时的计算量和代码大小。如果你想了解更多关于constant folding的信息，你可以参考这些网页。


CUDA, TensorRT, OpenVINO, CoreML and NNAPI,这些被称为硬件加速


模型量化



