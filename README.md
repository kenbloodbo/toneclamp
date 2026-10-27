# toneclamp

**检查提示词里的语气要求是否自相矛盾或无法落地。**

`toneclamp` —— 找出语气类要求（正式、口语、简洁、详尽）并检测互相矛盾与无法执行的情况

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`toneclamp.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install kenbloodbo-toneclamp
```

装完直接用命令名调用：

```bash
toneclamp --help
```

也可以不用安装，直接把 `toneclamp.py` 拷走用——它只依赖标准库。

## 为什么需要它

语气要求经常和长度要求联动，工具会同时看这两类约束的交叉

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 提示词语气约束 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python toneclamp.py --file input.txt
python toneclamp.py --text "示例内容"
python toneclamp.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 正则匹配会有漏报与误报——它是筛子，不是裁判。
- 不提供修复方案，也不重写内容。

## 跑测试

```bash
python test_toneclamp.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/kenbloodbo/toneclamp>

---

## 关于作者

kenbloodbo 做提示词语气约束相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://kenbloodbo.github.io>
- 仓库：<https://github.com/kenbloodbo/toneclamp>

## 许可

MIT，见 [LICENSE](LICENSE)。
