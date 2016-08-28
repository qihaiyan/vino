# tinyhttpd


`tinyhttpd`是一个超轻量级的 `HTTP Server`

### 使用：

```cmake
make
./tinyhttpd port &
```

### 日志：

**更新于`2016/08/22 01:41:34`**

* `tinyhttpd`仅支持`GET`请求。
* 对于每个`HTTP`请求，`fork`一个进程去处理。

-------
**更新于`2016/08/28 02:21:30`**

* 对于每个请求，不再由单独的进程来处理，而是由同一个进程的多个线程来处理。
* 为了防止僵尸线程`(Zombie Threads)`，创建不需要返回的线程，称之为**独立线程**。

######待解决：修复bug(独立线程返回后主线程也随之退出的问题)。

---------------

**更新于`2016/08/29 00:01:35`**

* 修复子线程执行完毕后导致主线程也随之退出的`bug`。
* 重新实现`do_ls`，使用`popen`读取`ls`程序的输出。


