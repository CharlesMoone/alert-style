# alert-弹窗样式
以类的方式实现的弹窗样式

弹窗必须需要包含
message.css
message.js
delete.png-该文件在css中被使用，修改地址请记得修改css中的地址

选择包含
reset.css－非常好用的初始化浏览器样式
＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃＃

结构设计如下
－全局：
  compatible兼容模式｛事件监听，获取event，获取target｝
  
－基类：
  EventBind text:{}
    创建基本弹窗框架
    原型：
      init初始化
      compatible的方法
      insert可使用.连续调用
      showMsg显示弹窗

－子类
  Delete 继承 EventBind
    设置弹窗样式为tip
    调用基类init
    实现alert及removeList方法
  
  Inform 继承 EventBind
    设置弹窗样式为tip
    调用基类init
    实现alert，提供callback功能。

  ImgUpload 继承 EventBind ［此功能针对后台提供数据类型，如不需要可自行删除］
    设置弹窗样式为operation
    调用基类init
    实现alert、canvasShow（有value时）、canvasDisplay（无value时）
    传递方式为使用form－>web server－>iframe－>getImgUpload()，需要在调用页面复写getImgUpload
