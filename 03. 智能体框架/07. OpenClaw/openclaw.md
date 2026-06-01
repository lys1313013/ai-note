# openclaw


```
npm install -g openclaw@latest
```


```
openclaw onboard --install-daemon
```


```undefined
openclaw configure
```


```
openclaw gateway stop
openclaw gateway restart
```

openclaw status
openclaw dashboard

报错
```text
disconnected (1008): unauthorized: gateway token mismatch
(open a tokenized dashboard URL or paste token in Control UI settings)
```
解决

openclaw dashboard --no-open



斜杠命令

切换模型
```
/model deepseek/deepseek-v4-flash
```