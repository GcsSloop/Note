# Mac 在当前位置打开终端

在工作中，经常需要在某个文件目录下运行终端，在 window 上可以直接在地址栏输入 cmd，就可以在当前位置打开终端了，而在 Mac 上则比较麻烦？

### 1. 使用系统服务

**选中文件夹 -> 右键 -> 新建位于文件夹位置的终端窗口**。

![QQ20190702-223903@2x](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/2019-07-03-012703.jpg?gcssloop)

> 如果你的右键没有这个选项，可以到 **系统偏好设置 -> 键盘 -> 快捷键 -> 服务** 找到这个选项并勾选。
>
> ![QQ20190702-222931@2x](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/2019-07-03-012705.jpg?gcssloop)

当然，有时候它也并不是很好用，例如我们需要到一个空目录中拉去一个 Git 仓库，那么我们新建窗口的时候还要回退到上一级目录再开启窗口岂不是很麻烦？

### 2. 使用第三方应用

后来我发现了一个小应用，可以放在 finder 菜单栏中，点击一下就可以直接在当前位置打开终端。

他就是 OpenInTerminal： **https://github.com/Ji4n1ng/OpenInTerminal**

![](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/main-open-in-terminal.gif)

它可以直接在终端或者编辑器中直接打开当前目录，还算一个不错的小应用。

但是有一天我在恢复了一次系统之后，它就没办法在我的系统上工作了，打开就闪退，所以暂时就用不了它了。

### 3. 自定义应用

利用 Mac 自带的 **自动操作** 自己创建一个应用。

#### 3.1 打开自动操作

![QQ20190703-082705@2x](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/2019-07-03-012701.jpg?gcssloop)

#### 3.2 新建，选择类型为应用程序

![QQ20190703-082356@2x](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/2019-07-03-012706.jpg?gcssloop)

#### 3.3 选择 AppleScript

**实用工具 -> 运行 AppleScript** ,将其拖动到右侧工作区域。

![QQ20190703-083028-HD](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/QQ20190703-083028-HD.gif)

### 3.4 输入脚本内容

```javascript
on run {input, parameters}
tell application "Finder"
	if exists Finder window 1 then
		set theWindow to window 1
    set thePath to (POSIX path of (target of theWindow as alias))
		tell application "Terminal"
			do script "cd " & quoted form of thePath & ";clear"
			activate
		end tell
    else
        set currentDir to desktop as alias
    end if
end tell
end run
```

脚本含义：

1. 通过 Finder 获取当前激活的窗口
2. 获取当前激活窗口的路径
3. 打开终端
4. 在终端中模拟 cd 命令跳转到当前路径然后清屏
5. 保持终端运行

> 通过修改脚本，也可以打开其它应用程序，具体可以去查阅一下 AppleScript 使用方法。

#### 3.5 保存应用程序呢

使用快捷键 **⌘(command) + S** 或者使用菜单 **文件 -> 存储** 来保存应用程序。

![QQ20190703-082356@2x](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/2019-07-03-12702.jpg?gcssloop)

#### 3.6 更换图标

如果你觉得图标难看的话，可以 image2Icon 来为应用换一个图标。

http://www.img2icnsapp.com/

我这里直接使用了 OpenInTerminal 的图标。

#### 3.7 添加到工具栏

在一个窗口中打开应用程序所在位置，然后打开另一窗口。

在第一个窗口的工具栏右键，选择自定义工具栏。然后把第二个窗口的应用拖上去。

![QQ20190703-085625-HD](http://gcsblog.oss-cn-shanghai.aliyuncs.com/blog/QQ20190703-085625-HD.gif)

这样就全部完成了。

### 4. 结语

我是因为 OpenInTerminal 工具在我这里无法使用，所以自己想办法搞了一个工具，如果大家不喜欢折腾的话，直接使用 OpenInTerminal 就可以了。

其实 Mac 上的**自动操作**可以做很多事情，如果利用好的话可以节省很多时间。

### 相关链接

- [OpenInTerminal](https://github.com/Ji4n1ng/OpenInTerminal)
- [Image2Icon](http://www.img2icnsapp.com/)
- [AppleScript](https://developer.apple.com/library/archive/documentation/AppleScript/Conceptual/AppleScriptLangGuide/introduction/ASLR_intro.html#//apple_ref/doc/uid/TP40000983-CH208-SW1)
- [打开终端(AppleScript版本)](http://gcsblog.oss-cn-shanghai.aliyuncs.com/app/%E6%89%93%E5%BC%80%E7%BB%88%E7%AB%AF.zip)