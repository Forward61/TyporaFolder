wechat开发者工具

https://developers.weixin.qq.com/ebook?action=get_post_info&docid=000846df9a03909b0086a50025180a



1.openId失败（点击获取openid，失败后，需要上传并部署：）

<img src="https://i.loli.net/2021/02/04/UE7b814ztZpyTDs.png" alt="image-20210126111418516" style="zoom:50%;" />



2。微信里请求必须是https.注意配置https证书。和nginx配置。



3.微信发起请求request和响应赋值setData()

从这个例子我们可以看到3个点：
1.渲染层和数据相关。
2.逻辑层负责产生、处理数据。
3.逻辑层通过 Page 实例的 setData 方法传递数据到渲染层。

**setData函数用于将数据从逻辑层渲染到视图层（异步），同时改变对应的this.data的值（同步）**。

 var that = this

**必须用setData赋值**

**that**.setData({
          resdata: res.data
        })

，参考

<u>此外需要注意以下3点：</u>

1. <u>直接修改 Page实例的this.data 而不调用 this.setData 是无法改变页面的状态的，还会造成数据不一致。</u>
2. <u>由于setData是需要两个线程的一些通信消耗，为了提高性能，每次设置的数据不应超过1024kB。</u>
3. <u>不要把data中的任意一项的value设为undefined，否则可能会有引起一些不可预料的bug。</u>

# 微信小程序：setData方法详解和注意事项

# https://cloud.tencent.com/developer/article/1673414



```javascript
findAll(){
    var that = this
    console.log('进入findAll方法')
    wx.request({
      
      url: 'https://www.ifreedom61.xyz/vbapi/vb/findAll', //仅为示例，并非真实的接口地址
      
      header: {
      'content-type': 'application/json' // 默认值
      },
      success (res) {

        console.log(res.data)
        resdata : res.data[0]
        motto:res.data[0].name
        that.setData({
          resdata: res.data
        })
        console.log('motto的值：' +that.data.motto) 
        console.log('resdata的值：' + that.data.resdata)
      }
      })
```

4.

## 渲染层和逻辑层

首先，我们来简单了解下小程序的运行环境。小程序的运行环境分成渲染层和逻辑层，其中 WXML 模板和 WXSS 样式工作在渲染层，JS 脚本工作在逻辑层。

小程序的渲染层和逻辑层分别由2个线程管理：渲染层的界面使用了WebView 进行渲染；逻辑层采用JsCore线程运行JS脚本。一个小程序存在多个界面，所以渲染层存在多个WebView线程，这两个线程的通信会经由微信客户端（下文中也会采用Native来代指微信客户端）做中转，逻辑层发送网络请求也经由Native转发，小程序的通信模型下图所示。

![img](https://res.wx.qq.com/wxdoc/dist/assets/img/4-1.ad156d1c.png)

5.页面

一个页面是分三部分组成：界面、配置和逻辑。界面由WXML文件和WXSS文件来负责描述，配置由JSON文件进行描述，页面逻辑则是由JS脚本文件负责。一个页面的文件需要放置在同一个目录下，其中WXML文件和JS文件是必须存在的，JSON和WXSS文件是可选的。

默认pages字段的第一个页面路径为小程序的首页。
