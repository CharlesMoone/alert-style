alert-弹窗样式
---
以类的方式实现的弹窗样式

[demo](http://charlesmoone.github.io/alert-style)

弹窗必须需要包含

    <link rel="stylesheet" href="message.css" />
    <script src="message.js"></script>

推荐包含

    <link rel="stylesheet" href="reset.css" />
    
##逻辑
1. 全局：
  compatible兼容模式｛事件监听，获取event，获取target｝
  
2. 基类EventBind创建基本弹窗框架
   + init初始化
   + compatible的方法
   + insert可使用.连续调用
   + showMsg显示弹窗

3. 子类Delete 继承 EventBind
   + 设置弹窗样式为tip
   + 调用基类init
   + 实现alert及removeList方法
  
4. 子类Inform 继承 EventBind
   + 设置弹窗样式为tip
   + 调用基类init
   + 实现alert，提供callback功能。

5. 子类ImgUpload 继承 EventBind(**此功能针对后台提供数据类型，如不需要可自行删除**)
   + 设置弹窗样式为operation
   + 调用基类init
   + 实现alert、canvasShow（有value时）、canvasDisplay（无value时）
   + 传递方式为使用form－>web server－>iframe－>getImgUpload()，需要在调用页面复写getImgUpload


