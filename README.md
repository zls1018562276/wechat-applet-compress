# wechat-applet-compress
微信小程序多图片压缩工具（失败反馈）

微信小程序原生开发：复制dist下的compress.js至自己的项目下
wepy.js框架开发：复制src/components下的compress.wpy文件至自己的项目下

wepy框架父组件引用该组件方式：<br>
```javascript
<template>  
  <view>  
    ......  
    ......  
    <compress  
    :needCompressSize.sync="0.5"  
    :uploadUrl.sync=""  
    :tempFiles.sync=""  
    .....>  
    </compress>  
  </view>  
</template>  
<script>  


import compress from '@/components/compress'

components = {
		compress: compress
}

.......

</script>  

```
参数列表  
<br>


      参数名       |       默认       | 数据类型 | 表述


 needCompressSize |     0.5（MB)     |	Number | 该大小以上的图片会被压缩


    uploadUrl 		|	       空				|  String	| 上传到服务器所需的api接口，默认不提供则返回本地暂存路径


    tempFiles			|	       空		    |  Array	|	需要压缩的图片路径数组（支持线上图片则需要在微信后台设置安全域名


    ctxWidth			|	  800（单位:px）  |  Number | 压缩图片宽度限制，默认800px


    ctxHeight			|	  800（单位:px）  |  Number | 压缩图片高度限制，默认800px


  
压缩方式<br>
  
父组件调用并获取压缩后的图片路径数组<br>
this.$invoke('compress', 'init',(urls) => {<br>
    console.log(urls)<br>
})  
