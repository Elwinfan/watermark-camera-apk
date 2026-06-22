# 水印相机 APK

专业打卡水印生成工具的Android应用版本。

## 📱 应用信息

- **应用名称**: 水印相机
- **应用ID**: com.elwinfan.watermark
- **版本**: 1.0.0
- **描述**: 专业打卡水印生成工具

## 🚀 快速开始

### 前置要求

- Node.js 18+
- npm 或 yarn
- Android Studio（本地开发）
- JDK 17+

### 本地开发

1. **安装依赖**
   ```bash
   npm install
   ```

2. **同步Android项目**
   ```bash
   npm run android:sync
   ```

3. **打开Android Studio**
   ```bash
   npm run android:open
   ```

4. **在Android Studio中构建APK**

### GitHub Actions 自动构建

推送到 `main` 分支会自动触发构建：

1. **构建Debug APK**
   - 每次push都会构建
   - 在Actions页面的artifacts中下载

2. **构建Release APK**
   - 仅在推送到main分支时构建
   - 在Actions页面的artifacts中下载

## 📁 项目结构

```
watermark-camera-apk/
├── www/
│   └── index.html          # 主HTML文件
├── android/                # Android原生项目
├── .github/
│   └── workflows/
│       └── build-android.yml  # GitHub Actions配置
├── capacitor.config.json   # Capacitor配置
├── package.json           # Node.js依赖
└── README.md              # 项目说明
```

## 🔧 配置说明

### 修改应用信息

编辑 `capacitor.config.json`:

```json
{
  "appId": "com.elwinfan.watermark",
  "appName": "水印相机",
  "webDir": "www"
}
```

### 修改HTML文件

直接编辑 `www/index.html`，修改后运行：
```bash
npm run android:sync
```

## 📦 构建说明

### 本地构建

1. **Debug版本**（测试用）
   ```bash
   cd android
   ./gradlew assembleDebug
   ```
   输出：`android/app/build/outputs/apk/debug/app-debug.apk`

2. **Release版本**（发布用）
   ```bash
   cd android
   ./gradlew assembleRelease
   ```
   输出：`android/app/build/outputs/apk/release/app-release.apk`

### GitHub Actions构建

- 推送代码到GitHub
- 前往 `Actions` 标签页
- 等待构建完成
- 在artifacts中下载APK

## 🔐 应用签名

Release APK需要签名才能发布到应用商店。需要配置：

1. 创建keystore文件
2. 在 `capacitor.config.json` 中配置签名信息
3. 或在Android Studio中配置签名

## 📝 更新日志

### v1.0.0 (2024-06-23)
- 初始版本
- 基础水印相机功能
- 打卡时间、地点、备注配置
- 图片下载和分享功能

## 👨‍💻 开发者

Elwinfan

## 📄 许可证

MIT License

## 🔗 相关链接

- [Capacitor官方文档](https://capacitorjs.com/)
- [Android开发者文档](https://developer.android.com/)
