English | [简体中文](README_cn.md)

![image](snapshot.png)

# hlmdl.js
[![Gitpod ready-to-code](https://img.shields.io/badge/version-1.0.0-green)](https://gitee.com/q695290484/hl-model.js)
[![Gitpod ready-to-code](https://img.shields.io/badge/Size-580KB-orange)](https://gitee.com/q695290484/hl-model.js/releases)

An easy to use, lightweight JavaScript tool to display HL model files on website. 

It allows to load a MDL with attachments.

### Getting Started

Using default config:
```html
<div id="test"></div>
<script src="hlmdl.js"></script>
<script>
    // Display MDL on a DOM element with id
    let mdl = new HL_MDL("test");
    // Load MDL file
    mdl.load({url:'asset/jpngirl01.mdl'});
    mdl.loadAttachment({url:'asset/p_cv47.mdl'});
    mdl.loadAttachment({url:'asset/p_wings.mdl'});
    // Actual loading & displaying
    mdl.build();
</script>
```

Customize settings:
```html
<div id="test"></div>
<script src="hlmdl.js"></script>
<script>
    // Configs
    let config = {
        gui : false,          // GUI controller, default:false
        enablePan : false,    // allow camera pan, default:false
        enableRotate : true,  // allow camera rotate, default:true
        enableZoom : true,     // allow camera zoom default:true
        camPosition : [15, 10, -15] // camera position default:[15, 10, -15]
    }
    // Display MDL on a DOM element with id
    let mdl = new HL_MDL("test", config);
    // Load player model file (url , start anim sequence, visible bodies)
    // url : required
    // anim : default is 0
    // body : will display all if not set
    mdl.load({url:'asset/jpngirl01.mdl', animation:1, body:[0,2]});
    // Load attachments
    mdl.loadAttachment({url:'asset/p_cv47.mdl', body:[0]});
    mdl.loadAttachment({url:'asset/p_wings.mdl', body:[0,3]});
    // Actual loading & displaying
    mdl.build({
        success: function(){} // load successfully, it will be triggered
        ,error: function(err){} // or failed, it will be triggered
    });
</script>
``` 

### Thanks
This project is originlly from [hlmv-web](https://github.com/crskycode/hlmv-web)

Also thanks to [three.js](https://github.com/mrdoob/three.js)
