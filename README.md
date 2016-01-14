# UI—第三弹，沉浸式状态栏

###一、概念：
**沉浸式状态栏”准确来说应该是“透明栏”，英文名“Translucent Bars”，是Android 4.4 新定义的设计规范。简单来说就是在软件打开的时候通知栏和软件顶部颜色融为一体，这样可以使软件和系统本身更加融为一体，同时通知栏的颜色不再是白色、黑色简单的两种了。**

###二、微信公众号：
**关注微信公众号，获取密码，了解更多。**
**微信公众号：jike_android**

![公众号](https://github.com/wch0620/StatusBar/raw/master/WeiXin/qrcode.jpg)

###三、效果图：

![效果图](https://github.com/wch0620/StatusBar/raw/master/ScreenShot/Screenshot5.png)

###四、关键代码：

```
	private void setStatusBarTransparent(){
		 
		if(VERSION.SDK_INT >= VERSION_CODES.KITKAT){
	        //托盘重叠显示在Activity上
	        View decorView = getWindow().getDecorView();	        
	        int uiOptions = View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN 
	        		|View.SYSTEM_UI_FLAG_LAYOUT_STABLE;
	        decorView.setSystemUiVisibility(uiOptions);  
	        decorView.setOnSystemUiVisibilityChangeListener(this);
	        // 设置托盘透明
	        getWindow().addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS);

	    	Log.d("CP_Common","VERSION.SDK_INT =" + VERSION.SDK_INT);
		}else{
	    	Log.d("CP_Common", "SDK 小于19不设置状态栏透明效果");
	    }
		  
	}
```

