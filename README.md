# IMSDK
targetSdkVersion 23
1.项目gralde文件下添加maven { url "https://raw.githubusercontent.com/AlfredZHOU/IMSDK/master/" }  

2.在主module下gralde文件下添加implementation 'com.hnjy.im:imsdk:版本号'。  
若有冲突或重复包，可自行添加exclude去除。  
如下：implementation ('com.hnjy.im:imsdk:1.0.2'){  
      exclude  group:'com.android.support'  
 }   
 
3.项目Application中初始化ImSdk.init(getApplicationContext());  

4.开始聊天，可调用ImSdk.jump()方法，并且携带必要参数。  
如下：ImSdk.setAppId("应用ID")  
          .setlUsrId("聊天对象ID")  
          .setlUserName("聊天对象名称")  
          .setlAvatar("聊天对象头像")   
          .setrUsrId("用户ID")  
          .setrUserName("用户名称")  
          .setrAvatar("用户头像")  
          .jump(activity/context);  
            
5.监听聊天界面内的事件处理。用户可通过registerCallBack方法注册到Imsdk。  
  1）消息已读回调：ReadCallBack  
  2）查看工单详情：WorkOrderCallBack  
  3）查看商品详情：GoodsCallBack  
  
6.配置Mainfest.xml,如下：  
  <activity  
      android:name="com.hnjy.im.sdk.eim.activity.im.ChatActivity"  
      android:launchMode="singleTop"  
      android:screenOrientation="portrait"  
      android:windowSoftInputMode="adjustPan|stateHidden"></activity>  
  <activity android:name="com.hnjy.im.sdk.eim.activity.im.IMWebVActivity"></activity>  
