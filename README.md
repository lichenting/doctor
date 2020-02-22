# doctor
本次学习总结
1.实现自定义ToolBar,以下为toolbar的布局文件

2.实现列表下拉刷新 主要运用SwipeRefreshLayout

3.侧滑栏效果 DrawerLayout NavigationView
侧滑栏依据所需要的item进行布局
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <group android:checkableBehavior="single">
        <item
            android:id="@+id/nav_message"
            android:icon="@drawable/message"
            android:title="消息中心" />
       ...
</menu>
4.加载效果 选用ProgressBar 应用在主界面上，当点击主界面一些按钮时加载东西是会出现
以下为在主界面布局中加载效果的代码
<?xml version="1.0" encoding="utf-8"?>
<ProgressBar
            android:id="@+id/progress_bar"
            android:layout_width="match_parent"
            android:layout_height="40dp"
            android:layout_gravity="center"/>
5.悬浮按钮和可交互提示  以下为布局文件代码
<?xml version="1.0" encoding="utf-8"?>
<android.support.design.widget.FloatingActionButton
            android:id="@+id/fab"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="bottom|end"
            android:layout_margin="16dp"
            android:src="@drawable/had"
            app:elevation="8dp"/>
6.具有网络请求与解析   采用JsonObject解析，开启线程发起网络请求
private void parseJSONWithJSONObject(String jsonData){
        try{
            JSONArray jsonArray = new JSONArray(jsonData);
            for(int i=0;i<jsonArray.length();i++){
                JSONObject jsonObject = jsonArray.getJSONObject(i);
                String id = jsonObject.getString("id");
                String name = jsonObject.getString("name");
                String version = jsonObject.getString("version");
                Log.d("MainActivity","id is "+ id);
                Log.d("MainActivity","name id "+ name);
                Log.d("MainActivity","version is "+ version);
            }
        }catch (Exception e){
            e.printStackTrace();
        }
    }
    
            
