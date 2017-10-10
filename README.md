## 性能优化记录
* 减少请求的数量：合并js、css、小图片
* 减少请求文件的体积：压缩js、css
* 多个元素的事件绑定使用事件代理
* 使用文档碎片减少文档结构的改变次数，由于每次HTML结构的改变会导致重新渲染
* 页面多个JS的加载，需要使用异步（async）、按需加载（就是只加载这个页面需要的）
* 数据使用提前加载：加载了一版后就偷偷的加载第二版，等触发了再显示；
* 图片使用延时加载：layzload;
* css按需加载；
  ```javascript
  
  function loadCss(url) {
    var link = document.createElement("link");
    link.type = "text/css";
    link.rel = "stylesheet";
    link.href = url;
    document.getElementsByTagName("head")[0].appendChild(link);
  }
  
  ```
  
  ```javascript
function one(initoption){
        this.age=120
    	one.prototype.add=function(){
            this.countryClick()
    	}
    }
    var two =new one(init);
    two.add() // 120
```
* js按需加载：（requireJS、es6模块化）
* 缓存：for循环的长度要缓存；dom节点要缓存；
* css用css3；因为css3的transform改变left、top不会导致重新渲染页面，它变化的是Dom的虚影；
* 能用三等号的就用三等号，由于底层源码对双等号判断了很多逻辑
