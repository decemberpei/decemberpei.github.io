这里有一份OpenVINO中使用推理引擎的python API调用NCS2做推理的性能优化BKM分享：
[https://software.intel.com/zh-cn/articles/performance-optimization-for-inference-using-intel-neural-compute-stick-2-with-openvino](https://software.intel.com/zh-cn/articles/performance-optimization-for-inference-using-intel-neural-compute-stick-2-with-openvino)

另外，这里有相关的参考代码（同步API，异步API，多线程，多进程，多NCS2等）实现，以及一些性能测试数据：
[https://github.com/decemberpei/openvino-ncs2-python-samples](https://github.com/decemberpei/openvino-ncs2-python-samples)

代码的依赖:
1. Linux + OpenVINO 2018R5（如果是其他OpenVINO版本，有可能需要对代码稍加改动）
2. OpenVINO[安装](https://software.intel.com/en-us/articles/OpenVINO-Install-Linux)时配置好了NCS2设备
