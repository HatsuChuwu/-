# 禁用鼠标离开网页/鼠标失焦监听脚本

## 简介
本脚本旨在禁止网页通过多种方式检测鼠标是否离开页面或窗口失去焦点，有效保护用户操作不被意外中断或记录。通过阻止相关事件监听器、伪造页面可见性状态、拦截特定事件等多种手段，实现对页面检测行为的屏蔽。

## 功能特性
1. **阻止 `mouseout` 和 `mouseleave` 事件监听器**：通过捕获并阻止这两个事件的传播和默认行为，防止网页监听鼠标离开页面的动作。
2. **阻止 `window` 上的 `blur` 和 `focusout` 事件监听器**：同样捕获并阻止这两个事件，防止网页检测窗口失去焦点。
3. **伪造页面可见性状态 (Page Visibility API)**：通过重新定义 `document` 的 `visibilityState` 和 `hidden` 属性，始终返回页面可见状态，防止网页通过该 API 检测页面是否隐藏。
4. **拦截 `visibilitychange` 事件**：捕获并阻止该事件，防止网页在页面可见性发生变化时执行相关操作。
5. **阻止页面检测鼠标坐标超出窗口**：定期模拟鼠标移动事件，每 30 秒触发一次，模拟用户活跃状态，防止网页通过检测鼠标坐标判断用户是否离开页面。
6. **重写旧式的 `window.onblur` 事件处理**：将 `window.onblur` 设置为 `null`，防止网页通过该方式检测窗口失去焦点。
7. **防止通过 `document.hasFocus()` 方法检测页面焦点**：重新定义 `Document.prototype.hasFocus` 方法，始终返回 `true`，防止网页检测页面是否获得焦点。

## 适用范围
本脚本适用于以下网址：
- `https://mooc2-ans.chaoxing.com/*`
- `https://zjy2.icve.com.cn/*`
- `https://mooc1.chaoxing.com/*`
- `https://e.huawei.com/*`
- `https://talent.shixizhi.huawei.com/*`
- `*://*.chaoxing.com/*`
- `*://*.edu.cn/*`
- `*://*.icve.com.cn/*`
- `*://*.course.icve.com.cn/*`
- `*://*.zjy2.icve.com.cn/*`
- `*://*.zyk.icve.com.cn/*`
- `*://*.icourse163.org/*`
- 可自行添加···

## 使用方法
1. 安装脚本：本脚本可在 [Greasy Fork](https://greasyfork.org/zh-CN/scripts/531453-%E7%A6%81%E7%94%A8%E9%BC%A0%E6%A0%87%E7%A6%BB%E5%BC%80%E7%BD%91%E9%A1%B5-%E9%BC%A0%E6%A0%87%E5%A4%B1%E7%84%A6%E7%9B%91%E5%90%AC) 上获取，点击安装按钮即可安装到支持油猴脚本（Tampermonkey）的浏览器中。
2. 启用脚本：安装完成后，在浏览器的油猴脚本管理界面中确保本脚本已启用。

## 技术细节
1. **脚本版本**：`v0.3.1`
2. **脚本命名空间**：`http://tampermonkey.net/`
3. **脚本作者**：Chuwu@https://github.com/HatsuChuwu
4. **许可证**：MIT 许可证
5. **下载链接**：https://greasyfork.org/zh-CN/scripts/531453-%E7%A6%81%E7%94%A8%E9%BC%A0%E6%A0%87%E7%A6%BB%E5%BC%80%E7%BD%91%E9%A1%B5-%E9%BC%A0%E6%A0%87%E5%A4%B1%E7%84%A6%E7%9B%91%E5%90%AC
6. **更新链接**：https://update.greasyfork.org/scripts/531453/%E7%A6%81%E7%94%A8%E9%BC%A0%E6%A0%87%E7%A6%BB%E5%BC%80%E7%BD%91%E9%A1%B5%E9%BC%A0%E6%A0%87%E5%A4%B1%E7%84%A6%E7%9B%91%E5%90%AC.meta.js

## 注意事项
1. 本脚本可能会影响某些依赖鼠标离开或窗口失焦检测的正常功能，请谨慎使用。
2. 由于不同网页的实现方式和兼容性问题，脚本可能无法在所有网页上完全生效。
3. 使用本脚本时，请确保您的操作符合相关网站的使用条款和法律法规。

## 联系作者
如果您在使用过程中遇到问题或有任何建议，欢迎通过作者的 GitHub 页面（https://github.com/HatsuChuwu）与作者联系。 
