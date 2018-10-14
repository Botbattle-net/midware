## 用户文档

### 服务器脚本（暂未启用）

服务器会调用你的脚本中名为 `getNumbers` 的函数 

参数为 `history`
```js
{
    "goldenNums": [
        12.6,
        9.2,
        3.2
    ],
    "userActs": {
        "frank": [100.0, 0.0],
        "jack": [1.11514, 15.51],
        "tom": [2.33, 3.4]
    }
}
```

返回值为 `act`
```js
[34.2, 1.7]
```
#### 样例

```python
from typing import Dict, List
import random
def getNumbers(history):
    goldenNums: List[float] = history["goldenNums"]
    userActs: Dict['name', [float, float]] = history["userActs"] 
    return [random.uniform(0, 100) for _ in range(2)]
```

### 本地脚本

下载 [参赛脚本](https://raw.githubusercontent.com/Botbattle-net/BOTBattle.net/deploy/tools/submit-tools/submit.py) 与你的参赛程序放在同一目录下.

运行参赛脚本, 根据提示设置, 或直接修改 [配置文件](https://github.com/Botbattle-net/BOTBattle.net/blob/deploy/tools/submit-tools/settings.json)

你的参赛程序会在每回合开始时被调用一次, 本回合的信息存放在目录下的 [data_last.json](https://github.com/Botbattle-net/BOTBattle.net/blob/deploy/tools/submit-tools/data_last.json) 中, 你的程序需要尽快将结果运算出来, 并写入目录下的 [rsl_last.json](https://github.com/Botbattle-net/BOTBattle.net/blob/deploy/tools/submit-tools/rsl_last.json) 中, 具体格式及含义见文件.