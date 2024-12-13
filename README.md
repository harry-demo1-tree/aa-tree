---

# pandas：强大的Python数据分析工具包

|   |   |
|---|---|
| 测试 | ![CI - 测试](https://github.com/pandas-dev/pandas/actions/workflows/unit-tests.yml/badge.svg) ![覆盖率](https://codecov.io/github/pandas-dev/pandas/coverage.svg?branch=main) |
| 包版本 | ![PyPI 最新发布](https://img.shields.io/pypi/v/pandas.svg) ![PyPI 下载量](https://img.shields.io/pypi/dm/pandas.svg?label=PyPI%20下载量) ![Conda 最新发布](https://anaconda.org/conda-forge/pandas/badges/version.svg) ![Conda 下载量](https://img.shields.io/conda/dn/conda-forge/pandas.svg?label=Conda%20下载量) |
| 元数据 | ![由NumFOCUS支持](https://img.shields.io/badge/powered%20by-NumFOCUS-orange.svg?style=flat&colorA=E1523D&colorB=007D8A) ![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3509134.svg) ![许可证 - BSD 3条款](https://img.shields.io/pypi/l/pandas.svg) ![加入Slack](https://img.shields.io/badge/join_Slack-information-brightgreen.svg?logo=slack) |

## 这是什么？
**pandas** 是一个Python库，提供快速、灵活和富有表现力的数据结构，旨在简化处理“关系型”或“标记型”数据的工作，并且既简单又直观。它致力于成为在Python中进行实际的、**现实世界**数据分析的基础高级构建模块。此外，它还有更宏大的目标，即成为所有语言中可用的最强大和灵活的开源数据分析/操作工具。它已经在朝着这个目标大步前进。

## 目录

- [主要功能](#主要功能)
- [获取方式](#获取方式)
- [依赖项](#依赖项)
- [从源代码安装](#从源代码安装)
- [许可](#许可)
- [文档](#文档)
- [背景](#背景)
- [获得帮助](#获得帮助)
- [讨论与开发](#讨论与开发)
- [贡献于pandas](#贡献于pandas)

## 主要特点
以下是pandas擅长的一些事情：

- 轻松管理[缺失数据](https://pandas.pydata.org/pandas-docs/stable/user_guide/missing_data.html)，包括浮点数和其他非浮点数据中的`NaN`、`NA`、或`NaT`
  - 结构大小的可变性：可以从DataFrame和其他高维对象中[插入和删除列](https://pandas.pydata.org/pandas-docs/stable/user_guide/dsintro.html#column-selection-addition-deletion)
  - 自动和显式的[数据对齐](https://pandas.pydata.org/pandas-docs/stable/user_guide/dsintro.html#intro-to-data-structures)，对象可以明确地对齐到一组标签上，或者用户可以忽略这些标签，让`Series`、`DataFrame`等自动在计算中为你对齐数据
  - 强大而灵活的[分组运算](https://pandas.pydata.org/pandas-docs/stable/user_guide/groupby.html#group-by-split-apply-combine)，用于执行分割-应用-组合操作，既可以聚合也可以转换数据
  - 简化了将其他Python和NumPy数据结构中不规则或不同索引的数据转换为DataFrame对象的过程
  - 基于智能标签的[切片](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#slicing-ranges)、[花式索引](https://pandas.pydata.org/pandas-docs/stable/user_guide/advanced.html#advanced)以及大型数据集的子集选择
  - 数据集的直觉式[合并](https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html#database-style-dataframe-or-named-series-joining-merging)和[连接](https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html#joining-on-index)
  - 数据集的灵活[重塑](https://pandas.pydata.org/pandas-docs/stable/user_guide/reshaping.html)和[Pivot表格](https://pandas.pydata.org/pandas-docs/stable/user_guide/reshaping.html)
  - 支持[层次化](https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html#hierarchical-indexing-multiindex)轴标签（允许每个刻度有多个标签）
  - 强大的IO工具，用于加载来自[平面文件](https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html#csv-text-files)（CSV和定界）、[Excel文件](https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html#excel-files)、[数据库](https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html#sql-queries)的数据，以及保存/加载至超高速的[HDF5格式](https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html#hdf5-pytables)
  - 针对[时间序列](https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#time-series-date-functionality)的功能：日期范围生成、频率转换、移动窗口统计、日期偏移和滞后

## 获取方式
源代码当前托管在GitHub上：
https://github.com/pandas-dev/pandas

最新发布的稳定版的二进制安装程序可在[Python包索引（PyPI）](https://pypi.org/project/pandas)和[Conda](https://anaconda.org/conda-forge/pandas)上找到。

```sh
# Conda 安装
conda install -c conda-forge pandas

# 或者通过PyPI安装
pip install pandas
```

每个版本之间的更改记录可以在[这里](https://pandas.pydata.org/pandas-docs/stable/whatsnew/index.html)找到。完整的更改详情，请参阅GitHub上的提交日志：https://github.com/pandas-dev/pandas。

## 依赖项
- [NumPy - 支持大型多维度数组和矩阵及高级数学函数的库](https://www.numpy.org)
- [python-dateutil - 提供标准datetime模块的强大扩展](https://dateutil.readthedocs.io/en/stable/index.html)
- [pytz - 将Olson时区数据库引入Python，实现准确跨平台的时间区计算](https://github.com/stub42/pytz)

查看[完整安装说明](https://pandas.pydata.org/pandas-docs/stable/install.html#dependencies)以了解所需、推荐和支持的最低版本依赖项。

## 从源代码安装

要从源代码安装pandas，除上述常规依赖项外，您还需要[Cython](https://cython.org/)。可以通过PyPI安装Cython：

```bash
pip install cython
```

在克隆git仓库后找到此文件所在的`pandas`目录中执行以下命令安装：

```bash
pip install .
```

如果您希望进行[开发模式安装](https://pip.pypa.io/en/latest/cli/pip_install/#install-editable)，可使用：

```bash
python -m pip install -ve . --no-build-isolation -Ceditable-verbose=true
```

请查看完整的[源代码安装指南](https://pandas.pydata.org/docs/dev/development/contributing_environment.html)。

## 许可证

[BSD 3许可协议](LICENSE)

## 文档

官方文档托管在[PyData.org](https://pandas.pydata.org/pandas-docs/stable/)上。

## 背景

`pandas`项目始于2008年在[AQR](https://www.aqr.com/)（一家量化对冲基金公司），自那时起一直处于活跃开发状态。

## 获取帮助

对于使用上的问题，最佳去处是[Stack Overflow](https://stackoverflow.com/questions/tagged/pandas)。
此外，一般性的问题和讨论也可以在[pydata邮件列表](https://groups.google.com/forum/?fromgroups#!forum/pydata)中进行。

## 讨论与开发

大多数开发讨论在GitHub的这个仓库内通过[GitHub问题跟踪器](https://github.com/pandas-dev/pandas/issues)进行。

另外，[pandas-dev邮件列表](https://mail.python.org/mailman/listinfo/pandas-dev)可用于处理专门的讨论或设计问题，并有一个[Slack频道](https://pandas.pydata.org/docs/dev/development/community.html?highlight=slack#community-slack)，用于快速解答开发相关疑问。

面向维护者的社区会议经常举行，对公众开放，同时每月有新贡献者会议，以支持新加入的贡献者。

更多关于沟通渠道的信息可在[贡献者社区](https://pandas.pydata.org/docs/development/community.html)页面找到。

## 为pandas贡献

[![开源助手](https://www.codetriage.com/pandas-dev/pandas/badges/users.svg)](https://www.codetriage.com/pandas-dev/pandas)

欢迎所有贡献，包括但不限于问题报告、bug修复、文档改进、增强功能以及想法。

详细的贡献指南位于**[贡献者指南](https://pandas.pydata.org/docs/dev/development/contributing.html)**中。

如果您想开始参与pandas代码库的工作，请转到GitHub的“问题”标签页，浏览有趣的议题。有很多标记为[Docs](https://github.com/pandas-dev/pandas/issues?labels=Docs&sort=updated&state=open)和[适合初学者的好问题](https://github.com/pandas-dev/pandas/issues?labels=good+first+issue&sort=updated&state=open)可以作为起点。

您还可以参与问题排查，这可能包括重现错误报告或请求关键信息，如版本号或复现步骤。如果想开始排查问题，一个简单的入门方法是[在CodeTriage订阅pandas](https://www.codetriage.com/pandas-dev/pandas)。

或许在使用pandas的过程中，您自己有了改进建议，或者在查找文档时觉得“这可以做得更好”……您可以采取行动！

在[邮件列表](https://groups.google.com/forum/?fromgroups#!forum/pydata)或[Slack](https://pandas.pydata.org/docs/dev/development/community.html?highlight=slack#community-slack)上提问，我们都乐于回答。

作为项目的贡献者和维护者，预计您会遵守pandas的的行为准则。更多信息可在：[贡献者行为准则](https://github.com/pandas-dev/.github/blob/master/CODE_OF_CONDUCT.md)

---

[返回顶部](#table-of-contents)

