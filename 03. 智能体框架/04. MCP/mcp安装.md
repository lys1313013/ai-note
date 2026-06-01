# mcp安装


前置条件


python --version




- 安装 Python 后，运行：`pip install uv`


- 通过运行验证：`uv --version`




验证uv是否安装成功

```
pip show uv
```


如果安装成功，但是uv命令又报错
报错信息：
```
'uv' 不是内部或外部命令，也不是可运行的程序 或批处理文件。
```

添加环境变量

```
%APPDATA%\Python\PythonXX\Scripts
```
> PythonXX替换为实际的路径

添加到Path
