## 实现一个二维码让 iOS 和 Android 用户自动跳转到对应下载链接

### 技术方案
要实现一个二维码让 iOS 和 Android 用户自动跳转到对应下载链接，核心是通过使用一个中间跳转页面（落地页），该页面根据 JavaScript 检测用户的设备类型进行重定向。

步骤：

* 生成一个指向我们服务器的跳转页面的URL，并将该URL生成二维码。
* 当用户扫描二维码后，访问该跳转页面。
* 跳转页面通过User-Agent判断用户设备是iOS还是Android，然后重定向到相应的应用商店下载链接（或应用内页面）。

### 如何复用
1. 把 index.html 拉下来
2. 替换两处跳转链接：
   ```js
    // Android
    window.location.href = "https://your-pgyer-url";

    // iOS
    const appUrl = "itms-beta://testflight.apple.com/join/YOUR_TF_ID";
   ```
3. 根据指导将代码部署到 GitHub Pages
4. 把短链发给用户，或者通过在线二维码生成器生成一个二维码发给用户
