### 1.Options  
#### globalConfigPath//全局配置路径  
#### Type: Boolean//布尔类型  
#### Default: false//默认值：false  
Store the config at $CONFIG/package-name/config.json instead of the default $CONFIG/configstore/package-name.json.  
//存储配置是$CONFIG/package-name/config.json而不是默认值$CONFIG/configstore/package-name.json.  
This is not recommended as you might end up conflicting with other tools, rendering the "without having to think" idea moot. 
//这是不推荐的，你可能最终与其他工具冲突，使得”不需思考”的想法没有意义  
### 2.const xdgBasedir = require('xdg-basedir');
### 3.const configDir = xdgBasedir.config || path.join(os.tmpdir(), uniqueString());  
//文件夹的路径
### 4.const makeDirOptions = {mode: 0o0700};  
//创建文件夹的方法
### const writeFileOptions = {mode: 0o0600};  
//写入文件的方法
### 5. const pathPrefix = opts.globalConfigPath ?  
### path.join(id, 'config.json') : path.join('configstore', `${id}.json`);  
//文件的开头部分路径  
### 收获：  
大致理解了读程序的流程  
在读该程序中学习了的很多新的知识点，还有已经以前学过的知识也重新温习了一遍。
