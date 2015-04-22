支付宝账单分类+下拉刷新+加载更多很炫有木有。一个控件，对应三种功能，所以我就要开始做了。
先放出效果图：
![123](http://a1.eoeandroid.com/attachment/forum/201504/14/142437gujsslwjaeb9yzaz.gif)
==============================================================
就这样啦！
先来讲讲历史：
首先看见了这个：

![123](https://github.com/emilsjolander/StickyListHeaders/raw/master/demo.gif)

https://github.com/emilsjolander/StickyListHeaders

作者写的不错啊，方便简洁。但是这个只能拿来做通讯录之类的啊？能不能扩展呢？百度一下，刚好看见了这个帖子：
http://www.eoeandroid.com/thread-537899-1-1.html

然后发现老鼠君又有创新性建议了@dkmeteor 
所以我就用了这两个开源框架MERGE一下，做出了这个出来。
https://github.com/Trinea/android-demo
https://github.com/emilsjolander/StickyListHeaders
============================================================
另外百度一下，发现老鼠君也有上传一个，被他建议的作者也有上传一个，这里就给出地址，用哪个，大家随意吧。
老鼠君帖子：

![123](http://a1.eoeandroid.com/attachment/forum/201408/08/004204mbdk9yejdu2ad992.gif)

http://www.eoeandroid.com/thread-539835-1-1.html

github:

https://github.com/dkmeteor/pull-to-refresh-sticky-list

被建议的朋友帖子：

![123](https://github.com/tongcpp/PullToRefresh-PinnedSection-ListView/raw/master/screen0.png)

http://blog.csdn.net/tongcpp/article/details/40372521

github:

https://github.com/tongcpp/PullToRefresh-PinnedSection-ListView

====================================================================
用法：

stickyList = (StickyListHeadersListView) findViewById(R.id.list);
        MyAdapter adapter = new MyAdapter(this);
        stickyList.getWrappedList().setAutoLoadOnBottom(true);
        stickyList.getWrappedList().setOnDropDownListener(new DropDownListView.OnDropDownListener() {

            @Override
            public void onDropDown() {
                Toast.makeText(DealActiviry.this,"头",Toast.LENGTH_LONG).show();
//                关闭头
//                stickyList.getWrappedList().onDropDownComplete();

            }
        });
        stickyList.getWrappedList().setOnBottomListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                Toast.makeText(DealActiviry.this,"尾",Toast.LENGTH_LONG).show();
//                关闭尾
//                stickyList.getWrappedList().onBottomComplete();
            }
        });
        stickyList.getWrappedList();
        stickyList.setAdapter(adapter);
MyAdapter参考StickyListHeaders 的用法说明，写法不变，用了里面的Layout和arrays,头尾布局已经写进了LIB里，所以不用。

https://github.com/emilsjolander/StickyListHeaders

相关定义参考这个文章

http://www.trinea.cn/android/dropdown-to-refresh-and-bottom-load-more-listview/


没有一定基础的朋友最好3个都别用



