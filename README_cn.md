[English](README.md) | 简体中文

![image](snapshot.png)

# hlmdl.js
[![Gitpod ready-to-code](https://img.shields.io/badge/版本-1.0.0-green)](https://gitee.com/q695290484/hl-model.js)
[![Gitpod ready-to-code](https://img.shields.io/badge/文件大小-580KB-orange)](https://gitee.com/q695290484/hl-model.js/releases)

一个简单易用的js，可以在网页上加载和显示HL模型。

允许绑定多个模型。

### 开始使用

使用默认设置:
```html
<div id="test"></div>
<script src="hlmdl.js"></script>
<script>
    // 绑定DOM元素
    let mdl = new HL_MDL("test");
    // 加载模型文件
    mdl.load({url:'asset/jpngirl01.mdl'});
    mdl.loadAttachment({url:'asset/p_cv47.mdl'});
    mdl.loadAttachment({url:'asset/p_wings.mdl'});
    // 实际加载和显示
    mdl.build();
</script>
```

自定义设置:
```html
<div id="test"></div>
<script src="hlmdl.js"></script>
<script>
    // 设置
    let config = {
        gui : false,          // 开启GUI控制面板 默认:false
        enablePan : false,    // 允许平移 默认:false
        enableRotate : true,  // 允许旋转 默认:true
        enableZoom : true,     // 允许缩放 默认:true
        camPosition : [15, 10, -15] // 摄像头位置 默认:[15, 10, -15]
    }
    // 绑定DOM元素
    let mdl = new HL_MDL("test", config);
    // 加载基础模型
    // url : 必填，模型路径
    // anim : 动作，默认0
    // body : 子模型，如果没设置则全部显示
    mdl.load({url:'asset/jpngirl01.mdl', animation:1, body:[0,2]});
    // 加载附件模型
    mdl.loadAttachment({url:'asset/p_cv47.mdl', body:[0]});
    mdl.loadAttachment({url:'asset/p_wings.mdl', body:[0,3]});
    // 实际加载和显示
    mdl.build({
        success: function(){} // 加载完成后会触发
        ,error: function(err){} // 加载失败会触发
    });
</script>
``` 

### 感谢
这个项目修改自 [hlmv-web](https://github.com/crskycode/hlmv-web)，增加了对透明贴图和骨骼合并等支持。
当然也要感谢 [three.js](https://github.com/mrdoob/three.js)