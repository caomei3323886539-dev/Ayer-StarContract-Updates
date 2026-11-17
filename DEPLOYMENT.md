# APK 更新服务部署说明

## GitHub Pages
Settings → Pages → Build and deployment → Deploy from a branch → main / (root) → Save。

预期网址：https://caomei3323886539-dev.github.io/Ayer-StarContract-Updates/

## GitHub Actions
Settings → Actions → General → Workflow permissions → Read and write permissions（若可用）。

## 发布 APK
Releases → Draft a new release，tag 形如 v5.0.1，上传恰好一个已签名 APK。Release 正文包含一行真实版本码，例如 Android-VersionCode: 501。

发布后 Actions 会计算 APK 的 SHA-256 并更新 update.json。发布前务必验证 APK 的包名、签名与 versionCode。更新器需要在 Android 工程中独立集成，不能仅靠 Pages 实现安装。

不要向仓库提交密钥库、签名密码或私钥。
