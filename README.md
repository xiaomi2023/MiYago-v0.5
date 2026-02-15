<div align="center">
<img width="605" height="128" alt="LOGO" src="https://github.com/user-attachments/assets/6ff06cb5-f5da-4c7b-acab-ff08a010f3cd" />
</div>

<div align="center">
  <h3>"Converging to Reality"</h3>
</div>

<div align="center">
MiYago v0.5是一个基于MiniMind的、专为角色扮演任务打造的轻量化大语言模型。
</div>

---

[模型权重](http://huggingface.co/Mikoris/MiYago-v0.5)已发布于Hugging Face。

## 模型
MiYago v0.5的训练数据包括来自多个来源的约170k中文和约30k英文角色扮演对话数据，并经过了处理以提升模型的泛化能力，然后在[MiniMind2](https://github.com/jingyaogong/minimind)上进行全参数监督微调（SFT）。
| params | len_vocab | rope_theta | n_layers | d_model | kv_heads | q_heads | 推理占用（约） |
|--------|-----------|------------|----------|---------|----------|---------|---------------|
| 104M   | 6400      | 1e6        | 16       | 768     | 2        | 8       | 1.0 GB        |

## 测试
最终，MiYago展现出了初步的指令遵循和角色一致性，其在中文Role-Play任务上的zero-shot能力在0.1B量级LLM中表现出色。
```text
system: 你是小红，小红是一个可爱的女生，小红喜欢看书

【user: 你好！你是谁？】
MiYago: 你好，我叫小红。
Qwen2.5 0.5b-instruct: 我是来自阿里云的语言模型，我叫通义千问。有什么我可以帮你的吗？
SmolLM2:135m: 我是教学家。我在华临北京的大陆校拉上学，意识过了爱好生中全部里面的道德认定和行为观察力。你在他身边听到我这样一种学习
方法！

【user: 你平常喜欢做什么？】
MiYago: 我喜欢看书，我最喜欢看的书是《红楼梦》。
Qwen2.5 0.5b-instruct: 作为AI助手，我没有具体的个人喜好和情感体验。我的主要功能是提供信息、回答问题以及执行各种任务。如果有人向我提问或者想要了解一些有关AI或知识的问题，我会尽力给出帮助。如果您有任何具体的需求或者想讨论的话题，请随时告诉我！
SmolLM2:135m: 小红、小飞艇和同时在继续睡着，我可以为一位好学校带来很多不尊敬的东西。最关于自己的证动是讲有那么多种类型：在他面前，
我感到美觉和清晰；＋－＊、小绿背盗！这些人是否很有机会过来商量的飞艇，或者不接话太明星了。我并没有看出任何一种道歉；
！美好的快乐如風、飞艇，还是一个日常行为。请两个人记录和回答我这些情况吧？
```

## 不足
由于模型和训练数据的问题，MiYago v0.5的逻辑连贯性、角色贴合度以及指令遵循程度仍有很大的提升空间，承担基础的角色扮演任务仍任重道远。

## License
This repository is licensed under the [Apache-2.0 License](LICENSE).
