# localazy

https://localazy.com/

https://localazy.com/docs/cli/the-basics

## Localazy CLI 的使用

### 授权

https://localazy.com/docs/cli/authorization

https://localazy.com/console/apps

在`CLI`运行目录下创建`localazy.json`配置文件:

```json
{
  "writeKey": "your-apps-write-key", 
  "readKey": "your-apps-read-key"  
}
```

也可以在命令行中指定`key`:

```
localazy [command] -r your-read-key -w your-write-key
```

### 安装

#### NPM

> 运行 Localazy CLI 需要 Node.js v18.20.7+ 和 NPM v6+。

```
npm install -g @localazy/cli
```

#### macOS

```
> brew tap localazy/tools
> brew install localazy
```

```
> brew upgrade localazy
```

#### Windows

https://localazy.com/docs/cli/installation#windows

[下载exe](https://dist.localazy.com/windows/windows-v2.0.7.zip)

### 运行

https://localazy.com/docs/cli/command-line-options

```
localazy [command] [options] [groups]
```

#### 下载资源文件

在`localazy.json`中配置好下载规则, 

```
{
    ...
    "download": {
        "folder": ".download/android",
        "files": {
            "output": "${lang}/${file}"
        }
    }
}
```

然后执行:

```
localazy download
```

#### 上传文件

在`localazy.json`中配置好规则, 

```
{
    ...
    "upload": {
        "type": "android",
        "folder": "localazy_android",
        "files": {
            "pattern": "**.xml",
            "lang": "zh-Hans-CN"
        }
    }
}
```

然后执行:

```
localazy upload
```

测试上传请使用`localazy upload -s`命令.

