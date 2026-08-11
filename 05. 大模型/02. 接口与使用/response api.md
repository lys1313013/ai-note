

text
input
model
store
tools
stream
include
reasoning
tool_choice
instructions
client_metadata
prompt_cache_key
parallel_tool_calls

input  

|         |      |      |
| ------- | ---- | ---- |
| role    |      |      |
| type    |      |      |
| content |      |      |

content

|      |      |      |
| ---- | ---- | ---- |
| text |      |      |
| type |      |      |
|      |      |      |





最简调用参数

```json
{
  "model": "glm-5.2",
  "input": "你好，请介绍一下自己。"
}
```





| 文件格式 | 处理方式                                                     | 是否调用 MinerU |
| -------- | ------------------------------------------------------------ | --------------- |
| `.pdf`   | 直接解析；超过 200 页时自动拆分，所有分片成功后合并 Markdown | 是              |
| `.ofd`   | Python `easyofd` 转为临时 PDF，再解析为 Markdown             | 是              |
| `.jpg`   | 图片直接上传解析为 Markdown                                  | 是              |
| `.docx`  | Python `python-docx` 直接提取正文、标题、表格和图片          | 否              |
| `.doc`   | LibreOffice 转临时 DOCX，再由 `python-docx` 转 Markdown      | 否              |
| `.wps`   | LibreOffice 转临时 DOCX，再由 `python-docx` 转 Markdown      | 否              |
| `.xlsx`  | Python `openpyxl` 直接读取工作表、单元格及公式               | 否              |
| `.xls`   | LibreOffice 转临时 XLSX，再由 `openpyxl` 转 Markdown         | 否              |
| `.et`    | LibreOffice 转临时 XLSX，再由 `openpyxl` 转 Markdown         | 否              |





参考文档：

https://cloud.tencent.com/document/product/1823/133813
