#   storage和cookie的区别

HTML5storage提供了一种方式让网站能够把信息存储到你本地的计算机上，并再以后需要的时候进行获取。这个概念和cookie相似，区别是它是为了更大容量存储设计的。Cookie的大小是受限的，并且每次你请求一个新的页面的时候cookie都会被发送过去。HTML5的storage是存储在你的计算机上，网站在页面加载完毕后可以通过Javascript来获取这些数据。 

# 使用方法

1.  window.sessionStorage.name = 'rainman';           // 赋值    
2.  window.sessionStorage.setItem('name','cnblogs');  // 赋值    
3.  window.sessionStorage.getItem('name');            // 取值    
4.  window.sessionStorage.removeItem('name');         // 移除值    
5.  window.sessionStorage.clear();                    // 删除所有sessionStorage    