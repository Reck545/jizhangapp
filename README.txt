# 轻松记账APP - 打包APK指南

## 已完成
✅ PWA记账APP已生成（支持离线使用）

## 文件结构
轻松记账APP/
├── index.html       （主应用）
├── manifest.json    （PWA配置）
├── sw.js            （离线缓存）
└── icons/
    ├── icon-192.png
    └── icon-512.png

## 方法一：用 PWABuilder 打包APK（推荐，最简单）

### 步骤：
1. 先部署到GitHub Pages：
   - 打开 https://github.com，注册/登录
   - 新建仓库，比如叫 accounting-app
   - 把整个「轻松记账APP」文件夹里的文件全部上传上去
   - 进入仓库 Settings → Pages → Source 选 main 分支 → Save
   - 等几分钟后就能访问 https://你的用户名.github.io/accounting-app

2. 用 PWABuilder 生成APK：
   - 打开 https://www.pwabuilder.com
   - 输入你上面的网址，点击 Start
   - 选择 Android → Package For Stores
   - 会自动生成 .apk 文件下载

3. 安装到手机：
   - 把下载的 .apk 传到安卓手机
   - 允许安装未知来源应用
   - 安装即可使用！

## 方法二：用 Bubblewrap CLI（需要Node.js）

如果方法一不行，可以本地打包：
1. 安装 JDK 11+ 和 Android SDK
2. npm install -g @anthropic/bubblewrap
3. bubblewrap init --manifest https://你的域名/manifest.json
4. bubblewrap build

## 方法三：用 Capacitor（推荐开发者）

1. npm init -y
2. npm install @capacitor/core @capacitor/cli
3. npx cap init 记账 com.accounting.app --web-dir=.
4. npx cap add android
5. npx cap sync
6. 用 Android Studio 打开 android 文件夹 → Build APK

## 功能
- 支出/收入记录（15+分类）
- 月预算管理与进度条
- 支出分类饼图 + 月度趋势图
- 年度汇总（柱状图+饼图+月度概览）
- 分类排行榜
- 数据导出/导入备份
- 离线可用（无需网络）
