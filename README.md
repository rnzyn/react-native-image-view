# react-native-image-view
##功能介绍 
1.支持图片下载前显示默认图片，下载完成后替换成下载后图片

2.支持图片下载时显示加载动画

3.支持点击，圆角，添加子节点等功能

4.特别处理安卓环境下同时设置了默认图片和下载图片后，点击时会显示默认图片的问题

5.支持图片本地缓存

6.支持自定义加载进度

支持安卓及iOS 7.0及以上。

##如何安装
```bash
npm install mkp-react-native-image-view --save
```
##依赖
- [url-parse](https://github.com/unshiftio/url-parse) URL处理
- [crypto-js](https://github.com/brix/crypto-js) md5
- [react-native-fs](https://github.com/johanneslumpe/react-native-fs) 文件系统

##如何使用
```javascript
import MKPLoadImageView from "react-native-image-view";

<MKPLoadImageView
            imageSource={{uri:"http://imga1.pic21.com/bizhi/140116/06682/01.jpg"}}
            style={{margin:100,width:100,height:100,borderRadius:50,overflow:"hidden"}}
            clickHandle={()=>{}}>
</MKPLoadImageView>
```

##属性说明

Any [`Image` property](http://facebook.github.io/react-native/docs/image.html) and the following:

| 属性 | 描述 | 默认值 |
|---|---|---|
|**`imageSource`**|(可选） 图片资源,支持本地图片和网络图片，只有设置此属性才会显示下载进度|{uri:`imageUrl`}／require(`imagePath`)|
|**`backImageSource`**|(可选）背景图，可选，持本地图片和网络图片,建议使用本地图片,只设置该属性不会显示下载进度|*None*|
|**`style`**|(可选) 样式|*style={{width:200,height:200}}*|
|**`onPress`**|(可选) 点击事件|*None*|
|**`customIndicator`**|(可选) 自定义图片下载进度指示器|*None*|
|**`indicatorType`**|(可选) 默认图片下载进度指示器样式|*circle*|
|**`data`**|(可选) 用于点击事件数据回传|*None*|
|**`loadCallBack`**|(可选) 下载进度回调函数|*None*|
|**`hiddenProgress`**|(可选) 隐藏下载进度条|*false*|
|**`clearCaheWillUnmount`**|(可选) 设置true时，当Image对象销毁的时候删除掉本地缓存图片|*false*|


## Demo

####exmaple1
![image-progress-demo](https://github.com/kunkunbobo/Test/blob/master/Asset/1.gif)
```
<MKPLoadImageView
defaultImageSource = {require('./assets/default.png')}
imageSource={{uri:'http://imga1.pic21.com/bizhi/140116/06682/01.jpg'}}
style={{margin:100,width:200,height:200,borderRadius:100,overflow:"hidden"}}
indicatorProps={{color:'red',style:{margin:10,flex:1}}}/>
```

####exmaple2
![image-progress-demo](https://github.com/kunkunbobo/Test/blob/master/Asset/2.gif)
```
<MKPLoadImageView
defaultImageSource = {require('./assets/default.png')}
imageSource={{uri:'http://imga1.pic21.com/bizhi/140116/06682/01.jpg'}}
style={{margin:100,width:200,height:200,borderRadius:100,overflow:"hidden"}}
indicatorProps={{color:'red',style:{margin:10,flex:1}}}
indicatorType="line"
onPress={()=>{}}/>
```

####exmaple3
![image-progress-demo](https://github.com/kunkunbobo/Test/blob/master/Asset/4.gif)
```
<MKPLoadImageView
defaultImageSource = {require('./assets/default.png')}
imageSource={{uri:'http://imga1.pic21.com/bizhi/140116/06682/01.jpg'}}
style={{margin:100,width:200,height:200,borderRadius:100,overflow:"hidden"}}
hiddenProgress={true}/>
```

####exmaple4
![image-progress-demo](https://github.com/kunkunbobo/Test/blob/master/Asset/5.gif)
```
<MKPLoadImageView
defaultImageSource = {require('./assets/default.png')}
imageSource={{uri:'http://imga1.pic21.com/bizhi/140116/06682/01.jpg'}}
style={{margin:100,width:200,height:200,borderRadius:100,overflow:"hidden"}}
hiddenProgress={true}
onPress={()=>{}}/>
```








