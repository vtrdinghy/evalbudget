# evalbudget

**规划评测的资源消耗与优先级。**

`evalbudget` —— 按每个评测项的成本与信息量排优先级，给出配额

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`evalbudget.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install vtrdinghy-evalbudget
```

装完直接用命令名调用：

```bash
evalbudget --help
```

也可以不用安装，直接把 `evalbudget.py` 拷走用——它只依赖标准库。

## 为什么需要它

先跑信息量高的评测，而不是先跑便宜的

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测资源预算 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python evalbudget.py --file input.txt
python evalbudget.py --text "示例内容"
python evalbudget.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 预算是静态比例分配，不考虑实际执行顺序。
- 不接真实队列，只做分配表。

## 跑测试

```bash
python test_evalbudget.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/vtrdinghy/evalbudget>

---

## 关于作者

vtrdinghy 做评测资源预算相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://vtrdinghy.github.io>
- 仓库：<https://github.com/vtrdinghy/evalbudget>

## 许可

MIT，见 [LICENSE](LICENSE)。
