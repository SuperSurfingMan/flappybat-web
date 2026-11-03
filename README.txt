FlappyBat 网页版 —— 部署包
==========================

【内容】
  game.html   页面入口（含哥特月夜矢量加载动画、letterbox 自适应与存档桥）
  game.js     Emscripten 运行时
  game.wasm   游戏程序（C++ 编译的 WebAssembly）
  game.data   游戏素材（18.5MB，虚拟文件系统）

【运行方式】必须通过 HTTP 访问，不能双击 html（浏览器禁止 file:// 加载 wasm）

  任选其一：
  1) Python（Windows 装 Python 后）：
       cd 本目录
       python -m http.server 8910
     浏览器打开 http://127.0.0.1:8910/game.html

  2) Node.js：
       npx serve -l 8910 .

  3) VS Code：安装 Live Server 插件，右键 game.html → Open with Live Server

【在其它设备上玩（手机/平板/同事电脑）】
  方法 A：同一 Wi-Fi 局域网
       python -m http.server 8910 --bind 0.0.0.0
     其他设备浏览器打开 http://本机局域网IP:8910/game.html
     （查 IP：Windows 命令 ipconfig，取 IPv4 地址）
  方法 B：静态托管（任何人任何地点）
     本目录 4 个文件上传到任意静态托管
     （GitHub Pages / Gitee Pages / Vercel / Netlify 免费档均可），
     得到网址即可分享。

【操作】
  鼠标点击 = 拍翅（手机直接点触屏）
  菜单：开始游戏按钮悬停/点击会分裂出模式按钮
  音频需首次点击后生效（浏览器自动播放策略）

【要求】
  浏览器支持 WebGL 2（2017 年后的浏览器基本都支持）
