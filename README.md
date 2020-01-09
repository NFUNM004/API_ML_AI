# 汉语通APP
|  项目名称   |  汉语通APP |
| --- | --- |
| 项目负责人    |  陈丹莉   |
|  项目进度   |   进行中  |


### 价值主张：
第二语言学习时需要语言理论知识的指导，对语法规则进行理解和把握。但汉语往往以意合为主，语法关系丰富，表意灵活。正是因为这个原因，外国人在学习汉语的过程中常常弄不清句子语法结构和词语词性，能说但稀里糊涂，也不能写的问题。市面上的汉语学习APP大多都是注重汉语拼音的学习，对句型语法的学习较少。汉语通APP通过分析句子的的句法结构信息，助于用户分辨句子结构，助力他们更好地进行汉语学习。

### 核心价值： 
实现一个帮助外国人汉语学习辅助APP。用户能够通过输入文本或上传图片输入中文句子，软件对句子进行词语词性、句子语法结构分析，并提高句子词语的词性分析、句子结构的练习，助他们更好理解汉语句子。


### 加值宣言：
本APP运用人工智能自然语言处理技术，通过词法分析识别出文本串中的词性，帮助用户辨别词语词性；通过依存句法分析分析句子的的句法结构信息，有助于用户分辨句子结构；通过通用文字识别技术，识别用户上传的图像中的文本。

### 用户痛点：
- 了解汉语的词性、句子的结构等，对汉语听说和写作都是一个很重要的打基础的过程。但汉语相比其它语言，具有词汇量大，句式复杂的特点，许多刚接触汉语或正在学习汉语的外国人，常常会陷入迷茫。
- 学习汉语时，“头发”、“一头牛”、“我在这头，妻子在那头”，明明是同一个字，但是在词性上又不太一样，到底它们分别是什么词性呢？这让用户十分困惑。
- 弄不清楚句子的主谓宾、定状补，查资料太复杂看不懂，想要一种简单的、针对“我”疑惑的这个句子进行解释的方法。
- 用户觉得自己在词语词性、句式结构上需要加强，想通过一些APP或资料进行练习，但是找不到。

### 人工智能概率性与用户痛点：
- 用户输入的文本语序颠倒或有歧义时，词性识别和句子结构识别能出现结果，但结果准确度会受影响。大部分语序颠倒的情况用户能够通过结果对句子词语的划分进行自我判断。
- 文字识别可能受图片清晰度和图片中字体清晰度、样式等影响，识别出错的可能性相比词性识别和句子结构识别更高。

### 需求列表
|   序号  |   标题  |  使用场景   |    重要程度 |
| --- | --- | --- | --- |
|  1 | 词语词性识别| 用户想知道一句话中词语的词性分别是什么，输入一个词语或一句话，软件告知用户词语的词性  |   最重要  |
|  2 |句子结构识别|  一句主谓宾的句子，但用户无法分辨哪个词是谓语，哪个词是宾语，希望能够通过软件了解句子的结构和词语间的关系  |  最重要   |
|  3 |  文字识别  |  在不认识某些字或字太大，不想打字的情况下，用户需要一个方便快捷的方式输入文字，用此方法识别图片中的文字，实现快捷输入   |  一般   | 

## 原型
### 产品架构图
![架构图.JPG](https://upload-images.jianshu.io/upload_images/9779994-86624c3cdd1e691f.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 产品原型
- 词性分析功能流程
![流程图1.JPG](https://upload-images.jianshu.io/upload_images/9779994-f3b07051f775fccc.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![流程2.JPG](https://upload-images.jianshu.io/upload_images/9779994-d269095dd2a32f9b.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 句法分析功能流程
![句法流程1.JPG](https://upload-images.jianshu.io/upload_images/9779994-a0765a2a5a856ff3.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![句法流程2.JPG](https://upload-images.jianshu.io/upload_images/9779994-7f394d853bfe0bc6.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 练习功能流程
![练习.JPG](https://upload-images.jianshu.io/upload_images/9779994-a83a6ceabd1e3fae.JPG?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


### 原型文档
- [“汉语通”原型文档](http://nfunm004.gitee.io/api_hanyutong_app/#g=1&p=%E4%BA%A7%E5%93%81%E6%9E%B6%E6%9E%84%E5%9B%BE)
- [“汉语通”原型文档下载](https://gitee.com/NFUNM004/api_hanyutong_app/blob/master/%E6%B1%89%E8%AF%AD%E9%80%9Aapp.rp)

---
## API

### API调用：

#### 词法识别API：

- 百度词法分析API调用代码:
```python
from aip import AipNlp
APP_ID = 'my ID'
API_KEY = 'my api_key'
SECRET_KEY = 'my SECRET_KEY'
client = AipNlp(APP_ID, API_KEY, SECRET_KEY)
text = "我有一头牛"
client.lexer(text)
```

- 识别结果:
```
{'log_id': 4567722688321243111,
 'text': '我有一头牛',
 'items': [{'loc_details': [],
   'byte_offset': 0,
   'uri': '',
   'pos': 'r',
   'ne': '',
   'item': '我',
   'basic_words': ['我'],
   'byte_length': 2,
   'formal': ''},
  {'loc_details': [],
   'byte_offset': 2,
   'uri': '',
   'pos': 'v',
   'ne': '',
   'item': '有',
   'basic_words': ['有'],
   'byte_length': 2,
   'formal': ''},
  {'loc_details': [],
   'byte_offset': 4,
   'uri': '',
   'pos': 'n',
   'ne': '',
   'item': '一头牛',
   'basic_words': ['一', '头', '牛'],
   'byte_length': 6,
   'formal': ''}]}
```

- 清华大学词法分析器（THU Lexical Analyzer for Chinese，THULAC）调用代码：

```python
import thulac  
thu1 = thulac.thulac() 
text = thu1.cut("我有一头牛", text=True) 
print(text)
```

- 识别结果
```我_r 有_v 一_m 头_q 牛_n ```

- 讯飞词法分析 API 调用代码：

```python
import time
import urllib.request
import urllib.parse
import json
import hashlib
import base64
url ="http://ltpapi.xfyun.cn/v1/pos"
x_appid = "my id"
api_key = "my key"
TEXT="我有一头牛。"

def main():
    body = urllib.parse.urlencode({'text':TEXT}).encode('utf-8')

    param = {"type": "dependent"}
    x_param = base64.b64encode(json.dumps(param).replace(' ', '').encode('utf-8'))
    x_time = int(int(round(time.time() * 1000)) / 1000)
    x_checksum = hashlib.md5(api_key.encode('utf-8') + str(x_time).encode('utf-8') + x_param).hexdigest()
    x_header = {'X-Appid': x_appid,
                'X-CurTime': x_time,
                'X-Param': x_param,
                'X-CheckSum': x_checksum}
    req = urllib.request.Request(url, body, x_header)
    result = urllib.request.urlopen(req)
    result = result.read()
    print(result.decode('utf-8'))
    return
if __name__ == '__main__':
    main()

```

- 输出结果：
```
{"code":"0","data":{"pos":["r","v","m","q","n","wp"]},"desc":"success","sid":"ltp0040e017@dx4edf1171d065000100"}
```


- 调用结果分析：
- 经过调用，发现三者词法分析的结果大多一致。除了百度词法分析API在分析句子“我有一头牛”时将“一头牛”划分为名词词组，若用户要求更精准的分析，需参考THULAC和讯飞，“一头牛”三个字应当分别对应数词、量词和名词。
- 三者都难以准确判断如“人要是行，干一行行一行”这种带有歧义或标点符号缺失的句子，需要手动用标点符号将句子分割为“人要是行，干一行，行一行”，才能准确判断。

###  API使用比较分析：
|          | 百度词法分析API                                                                                 |                            THULAC                                         |                 讯飞词法分析API                                          |
| -------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| 准确度   |                                         较高                                                 |                            高                                             |                            高                                             | 
| 判断速度 |                                         快                                              |                                 快                                            |                                     快                                        |
| 成熟程度 | 对领域新词、专有名词的识别有效程度显著，目前百度词法分析在算法效果上领先主流中文词法分析模型 | 集成目前世界上规模最大的人工分词和词性标注中文语料库（含5800万字）训练而成 |以哈工大社会计算与信息检索研究中心研发的 “语言技术平台（LTP）” 为基础，提供高效精准的简体中文自然语言处理服务                               |
| 价格     | 可免费调用50w次，5QPS/天；付费后能提升秒查询率和售后客服的效率，也可购买定制版               | 未知，商业合作需要邮箱进行交涉                                             |   免费调用：分词、词性标注每日服务量各500次，提升限额价格未知        |


---


#### 依存句法分析API：

- 百度依存句法分析API代码调用：
```python
from aip import AipNlp
APP_ID = 'my ID'
API_KEY = 'my api_key'
SECRET_KEY = 'my SECRET_KEY'
client = AipNlp(APP_ID, API_KEY, SECRET_KEY)
text = "智能化时代的来临，使汽车从一次性交付产品成为可以无限迭代的智能终端"
client.depParser(text);
options = {}
options["mode"] = 1
client.depParser(text, options)
```

- 调用结果：
```python
{'log_id': 3077095668848504904,
 'text': '智能化时代的来临，使汽车从一次性交付产品成为可以无限迭代的智能终端',
 'items': [{'postag': 'vn',
   'head': 2,
   'word': '智能化',
   'id': 1,
   'deprel': 'ATT'},
  {'postag': 'n', 'head': 3, 'word': '时代', 'id': 2, 'deprel': 'DE'},
  {'postag': 'u', 'head': 4, 'word': '的', 'id': 3, 'deprel': 'DE'},
  {'postag': 'vn', 'head': 6, 'word': '来临', 'id': 4, 'deprel': 'TOP'},
  {'postag': 'w', 'head': 4, 'word': '，', 'id': 5, 'deprel': 'WP'},
  {'postag': 'v', 'head': 0, 'word': '使', 'id': 6, 'deprel': 'HED'},
  {'postag': 'n', 'head': 6, 'word': '汽车', 'id': 7, 'deprel': 'DBL'},
  {'postag': 'p', 'head': 12, 'word': '从', 'id': 8, 'deprel': 'ADV'},
  {'postag': 'b', 'head': 10, 'word': '一次性', 'id': 9, 'deprel': 'ADV'},
  {'postag': 'v', 'head': 11, 'word': '交付', 'id': 10, 'deprel': 'ATT'},
  {'postag': 'n', 'head': 8, 'word': '产品', 'id': 11, 'deprel': 'POB'},
  {'postag': 'v', 'head': 6, 'word': '成为', 'id': 12, 'deprel': 'DBL'},
  {'postag': 'v', 'head': 15, 'word': '可以', 'id': 13, 'deprel': 'ADV'},
  {'postag': 'ad', 'head': 15, 'word': '无限', 'id': 14, 'deprel': 'ADV'},
  {'postag': 'v', 'head': 16, 'word': '迭代', 'id': 15, 'deprel': 'DE'},
  {'postag': 'u', 'head': 17, 'word': '的', 'id': 16, 'deprel': 'DE'},
  {'postag': 'n', 'head': 12, 'word': '智能终端', 'id': 17, 'deprel': 'VOB'}]}
 
```

- 讯飞依存句法分析API代码调用：
```python
import time
import urllib.request
import urllib.parse
import json
import hashlib
import base64

url ="http://ltpapi.xfyun.cn/v1/dp"
x_appid = "my id"
api_key = "my key"
TEXT="智能化时代的来临，使汽车从一次性交付产品成为可以无限迭代的智能终端。"

def main():
    body = urllib.parse.urlencode({'text':TEXT}).encode('utf-8')
    param = {"type": "dependent"}
    x_param = base64.b64encode(json.dumps(param).replace(' ', '').encode('utf-8'))
    x_time = int(int(round(time.time() * 1000)) / 1000)
    x_checksum = hashlib.md5(api_key.encode('utf-8') + str(x_time).encode('utf-8') + x_param).hexdigest()
    x_header = {'X-Appid': x_appid,
                'X-CurTime': x_time,
                'X-Param': x_param,
                'X-CheckSum': x_checksum}
    req = urllib.request.Request(url, body, x_header)
    result = urllib.request.urlopen(req)
    result = result.read()
    print(result.decode('utf-8'))
    return

if __name__ == '__main__':
    main()
```

- 输出结果：
```
{"code":"0","data":{"dp":[{"parent":1,"relate":"ATT"},{"parent":3,"relate":"ATT"},{"parent":1,"relate":"RAD"},{"parent":5,"relate":"SBV"},{"parent":3,"relate":"WP"},{"parent":-1,"relate":"HED"},{"parent":5,"relate":"DBL"},{"parent":11,"relate":"ADV"},{"parent":10,"relate":"ATT"},{"parent":10,"relate":"ATT"},{"parent":7,"relate":"POB"},{"parent":5,"relate":"VOB"},{"parent":11,"relate":"VOB"},{"parent":14,"relate":"ATT"},{"parent":17,"relate":"ATT"},{"parent":14,"relate":"RAD"},{"parent":17,"relate":"ATT"},{"parent":12,"relate":"VOB"},{"parent":5,"relate":"WP"}]},"desc":"success","sid":"ltp0040902d@dx23571171cf3ea00100"}
```

### API使用比较分析
|          | 百度词法分析API                                                                               |                 讯飞词法分析API                                          |
| -------- | -------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| 准确度   |                                         较高                                                 |                            高                                             |                            高                                             | 
| 判断速度 |                                         快                                              |                                 快                                            |                                     快                                        |
| 成熟程度 | 对领域新词、专有名词的识别有效程度显著，目前百度词法分析在算法效果上领先主流中文词法分析模型 | 集成目前世界上规模最大的人工分词和词性标注中文语料库（含5800万字）训练而成 |以哈工大社会计算与信息检索研究中心研发的 “语言技术平台（LTP）” 为基础，提供高效精准的简体中文自然语言处理服务                               |
| 价格     | 可免费调用50w次，5QPS/天；付费后能提升秒查询率和售后客服的效率，也可购买定制版               | 未知，商业合作需要邮箱进行交涉                                             |   免费调用：分词、词性标注每日服务量各500次，提升限额价格未知        |


### 使用后风险报告 
- 自然语言分析API市场竞争程度中等，较多大型企业都有进行尝试，但做得十分出色的较少。随着汉语热不断兴起、人工智能审核中文文本的市场地提升、语言分析模型地精进等，此类API拥有较大的未来发展可能性。
- 大部分词语词性分析、依存语法分析API对于输入的文本都有字数限制。
