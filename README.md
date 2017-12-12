# configstore-

Easily load and persist config without having to think about where and how  
//轻松加载 并且 保存配置信息 不用考虑在哪里以及如何  

Config is stored in a JSON file located in $XDG_CONFIG_HOME or (~ /.config.)  
//configstore配置存储的路径 在$XDG_CONFIG_HOME或者是在~/.config中的JSON文件中

Example: (~/.config/configstore/some-id.json)   
//例如 此路径

If you need this for Electron, check out electron-store instead.  

## Usage  
const Configstore = require('configstore'); //引入模块  
const pkg = require('./package.json');//引入npm 

// create a Configstore instance with an unique ID e.g.   
   创建一个具有唯一ID的configstore实例     

// Package name and optionally some default values   
   包的名称，和可选的一些默认值   

const conf = new Configstore(pkg.name, {foo: 'bar'});//创建对象，新建属性和属性值  

console.log(conf.get('foo')); //get方法访问属性  
//=> 'bar'  

conf.set('awesome', true);//给对象添加属性以及属性值  
console.log(conf.get('awesome'));  
//=> true  

// Use dot-notation to access nested properties  
conf.set('bar.baz', true); //用.符号来访问嵌套的属性  
console.log(conf.get('bar'));  
//=> {baz: true}  

conf.delete('awesome');//删除某属性  
console.log(conf.get('awesome'));  
//=> undefined  

## API  

### Configstore(packageName, [defaults], [options])  
Returns a new instance.  
//返回一个新的实例  

### packageName  
Type: string  
//字符串类型  
//包的名字  
Name of your package.  

### Defaults 
Type: Object  
//对象类型  
Default config.  
//默认配置  

### Options    
globalConfigPath
//全局配置路径  
Type: Boolean //布尔类型  
Default: false//默认：false  
Store the config at $CONFIG/package-name/config.json instead of the default $CONFIG/configstore/package-name.json. This is not recommended as you might end up conflicting with other tools, rendering the "without having to think" idea moot.  
//存储配置是$CONFIG/package-name/config.json而不是默认值$CONFIG/configstore/package-name.json.  
这是不推荐的，你可能最终与其他工具冲突，使得”不需思考”的想法没有意义  

### Instance
//例如  
You can use dot-notation in a key to access nested properties.  
// 你可以在a中用 . 符号来访问嵌套的属性  

### .set(key, value)    
.set(键，值)   
Set an item. 设置一个项目

### .set(object)  
Set multiple items at once.  
//一次设置多个项目  

### .get(key)  
Get an item.//获得一个项目  

### .has(key)  
Check if an item exists //.检查项目是否存在  
 
### .delete(key)   
Delete an item.//删除一个项目  

### .clear()  
Delete all items. //清除所有项目  

### .size  
Get the item count. //获取项目数量  

### .path 路径  
Get the path to the config file. Can be used to show the user where the config file is located or even better open it for them.
//获取配置文件的路径，可以向用户显示配置文件的位置，甚至更好的打开项目。  

### .all  
Get all the config as an object or replace the current config with an object:  
//获取所有配置作为对象或者用对象替代当前配置  
conf.all = {  
	hello: 'world'  
};  

## License //执照  
BSD license  
Copyright Google 版权谷歌  

## 关键词  
配置， 存储， 存储， conf， 配置， 设置， 首选项， JSON， 数据， 坚持， 持久性， 保存  

