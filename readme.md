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

4. 执行程序
```bash
bash infer.sh
```