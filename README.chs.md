Chinese Converter
=================

此工具是用来转换繁体中文与简体中文档案。基本上，由繁入简或由简至繁应该都可以，但目前只测试过繁至简的转换。

由于此工具使用了 MS Word 来进行简繁转换，故你的 Windows 作业环境必须有安装 MS Word。
我只在 Word 2013 上测试过。若您发现任何问题，欢迎回报 bugs。

注：此文件的简体中文版 README.chs.md 就是利用此工具产生的。

###使用方法

    ChineseConverter <InputFile> <OutputFile> <ConversionDirection> [DictionaryFile]

**参数:**

 * InputFile: 输入档名。目前仅支持 UTF-8 编码。
 * OutputFile: 输出档名。目前仅支持 UTF-8 编码。若档案已存在，将会被覆盖。
 * ConversionDirection: "t2s" 或 "s2t"，分别表示「繁->简」或「简->繁」。
 * DictionaryFile: 字典文件。每一行代表一个以 '=' 号分隔的简繁术语对应，例如：「面向对象=面向对象」。注：此字典文件系用于前置转换作业，亦即输入档案会先经过此字典文件的转换，然后才喂给 MS Word  进行简繁／繁简转换。


**范例：**

    ChineseConverter README.md README.chs.md t2s cht2chs.dict

###原始码 

完整原始码：<https://github.com/huanlin/Chinese-Converter>

其中的 Dictionary 文件夹是用来存放自定义的简繁术语字典。请注意，这些字典档案只是用来补足 MS Word 未提供的术语，而不是完整的术语对照表。
我打算在这里维护一份自己使用的字典，每次碰到缺的词汇就加进去。如果您也有用这个工具，欢迎协助添加字典文件。

注意：添加词汇至字典文件时，如果其他字典文件已经存在该词汇，则程序在执行转换时，只会取「第一个」词汇对照，而忽略其余重复定义的词汇。

###未来可能加入的功能

 * 支持多个自定义词典文件，以便将字典分类并个别维护。如此便可为不同领域提供不同的字典（例如信息技术、法律、生物等），并且在执行转换时视需要结合多个字典文件。