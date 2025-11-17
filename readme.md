## 运行方法
1. 下载llava-med参数
```url
https://huggingface.co/microsoft/llava-med-v1.5-mistral-7b
```
2. 更改infer.sh中的参数
```
    --model "/path/to/llava-med-v1.5-mistral-7b" \ # llava-med base-model存放位置
    --adapters "/path/to/NoduleLLaVA/ckpt/checkpoint-820" \ # lora存档位置
    --dataset "/home/qianq/mycodes/NoduleLLaVA/example" \ # 数据集位置
```
3. 配置环境

根据requirements.txt安装对应的python环境依赖，python3.10

4. 原始代码问题修改：
```bash
  File "/home/qianq/.conda/envs/demo/lib/python3.10/site-packages/swift/llm/template/template/llava.py", line 55, in _encode
    num_image_tokens = (height // self.processor.patch_size) * (
TypeError: unsupported operand type(s) for //: 'int' and 'NoneType'

该文件加入代码->swift/llm/template/template/llava.py line 55
if self.processor.patch_size is None:
    self.processor.patch_size = 14

```

5. 下载ckpt

通过网盘分享的文件：ckpt.zip
链接: https://pan.baidu.com/s/1hkArpiNHSXVFD1xyNm9Vcw 提取码: eeu6
如果链接失效请联系 qianq9720@163.com

6. 执行程序
```bash
bash infer.sh
```