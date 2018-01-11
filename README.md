## 性能优化记录
* 减少请求的数量：合并js、css、小图片
* 减少请求文件的体积：压缩js、css
* 多个元素的事件绑定使用事件代理
* 使用文档碎片减少文档结构的改变次数，由于每次HTML结构的改变会导致重新渲染
* 页面多个JS的加载，需要使用异步（async）、按需加载（就是只加载这个页面需要的）
* 数据使用提前加载：加载了一版后就偷偷的加载第二版，等触发了再显示；
* 图片按需加载：
   >  使用layzload;
   >  项目图片分大图片和icon（通过构建工具转成base64）
* css按需加载；
  
  function loadCss(url) {
    var link = document.createElement("link");
    link.type = "text/css";
    link.rel = "stylesheet";
    link.href = url;
    document.getElementsByTagName("head")[0].appendChild(link);
  }
  
* js按需加载：（requireJS、es6模块化）
* 缓存：for循环的长度要缓存；dom节点要缓存；
* css用css3；因为css3的transform改变left、top不会导致重新渲染页面，它变化的是Dom的虚影；
* 均用三等号做判断（除了if(test == null){}），由于底层源码对双等号判断了很多逻辑

### 降频
* setTimeout ,设置固定时间，先清除定时器句柄，再生成定时器对象；

### 计算代码执行时间
```javascript
  // 启动计时器
		console.time('testForEach');
  //TODO
		// 停止计时，输出时间
		console.timeEnd('testForEach');
```
