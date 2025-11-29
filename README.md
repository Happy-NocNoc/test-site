# nocfree-site 

此目录包含由仓库根目录构建生成的生产静态文件（HTML、CSS、JS、assets）。`nocfree-site` 被视为一个独立可部署的静态站点项目，直接部署即可对外提供服务。

## 说明
- **位置**：`/nocfree-site`
- **内容**：Vite 构建后的静态文件，已经过打包和压缩，适合放到静态主机（如 Vercel、Netlify、GitHub Pages、S3 + CloudFront）或通过静态文件服务器直接托管。

## 如何部署（示例）

本目录可以直接上传到静态托管服务或用本地静态服务器测试：

使用 `http-server`（需先安装）：

```bash
npx http-server . -p 5000
```

或使用 Python 自带的简单服务器：

```bash
python3 -m http.server 5000
```

然后在浏览器打开 `http://localhost:5000`。

## 如何生成 / 更新 `nocfree-site`

请不要直接在 `nocfree-site` 内修改文件。所有源代码位于仓库根目录的 `src/`（及相关配置文件）。修改源代码后，在仓库根目录运行构建命令重新生成 `nocfree-site`：

```bash
npm run build
```

本仓库的 `package.json` 中的构建命令为：

```
tsc -b && vite build
```

构建产物会输出到本 `nocfree-site` 目录。

## 开发者提示
- 若在部署时遇到路由或 404 问题（单页应用），请在托管服务上启用 SPA 回退（rewrite to `index.html`）。
- 保留 `nocfree-site` 为生成目录：不要把源代码直接放入此目录，也不要在此目录进行版本控制上的长期修改。

## 许可与来源
此目录的内容由仓库根目录源代码构建生成。有关源代码、许可和贡献请参阅仓库根目录的 `README.md`。
