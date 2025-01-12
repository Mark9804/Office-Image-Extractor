# DocumentImageExtractor

提取多类文档中的图片。/ Extract images embedded in various kinds of documents.

[English](https://github.com/Mark9804/OfficeImageExtractor/blob/master/README_en.md)

## 功能

提取Office 2007及更新的Office程序创建的文档（docx, pptx, xlsx）以及PDF中的图片。

## 原理

Office 2007及更新的Office文档会将媒体文件保存至`[对应格式]\media` 路径当中。脚本的核心代码是将Office07-2016文档以zip压缩包形式解压，将对应路径下的图片进行移动。

\* 格式 - 路径名对应关系：

| 文档格式（07-2016） | 对应路径     |
| ------------------- | ------------ |
| Word                | ~\word\media |
| PowerPoint          | ~\ppt\media  |
| Excel               | ~\xl\media   |

Adobe PDF使用XREF进行标识，需要读取图像元数据然后使用pillow还原。

## 使用

###  1. 命令行调用

`python DocumentImageExtractor.py 文件绝对路径`

###  2. 使用可执行程序

将对应文件拖到[构建的可执行程序](https://github.com/Mark9804/OfficeImageExtractor/releases)上方并松开鼠标。

**程序执行完毕后会自动打开存放有媒体的文件夹。**文件夹与源文件的目录相同并且名称相同（没有后缀）。

## TODO

- [ ] 增加真正的批量文件支持
- [x] Mac移植
- [ ] 支持Office 97-2003文档\*\*
- [x] 跨平台脚本
- [x] PDF文档支持

\*\* Office 97-2003文档储存媒体文件的方式不同于Office 2007+版本。我还不知道是这些文档如何储存媒体文件的。
