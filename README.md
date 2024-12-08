# Vue 3 + TypeScript + Vite + Pinia + Element-plus

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Type Support For `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin) to make the TypeScript language service aware of `.vue` types.

If the standalone TypeScript plugin doesn't feel fast enough to you, Volar has also implemented a [Take Over Mode](https://github.com/johnsoncodehk/volar/discussions/471#discussioncomment-1361669) that is more performant. You can enable it by the following steps:

1. Disable the built-in TypeScript Extension
   1. Run `Extensions: Show Built-in Extensions` from VSCode's command palette
   2. Find `TypeScript and JavaScript Language Features`, right click and select `Disable (Workspace)`
2. Reload the VSCode window by running `Developer: Reload Window` from the command palette.

## 如何更新项目中的组件

要检查你的依赖和开发依赖是否有更新的稳定版本，可以使用以下方法：

---

### 方法 1：使用 `npm outdated`
在项目目录下运行以下命令：
```bash
npm outdated
```

这个命令会列出当前依赖、期望版本和最新版本的对比表格，例如：

| Package             | Current | Wanted | Latest | Location               |
|---------------------|---------|--------|--------|------------------------|
| element-plus        | 2.4.1   | 2.4.1  | 2.5.0  | vite-vue-ts-element    |
| vue                 | 3.3.4   | 3.3.4  | 3.4.0  | vite-vue-ts-element    |

- **Current**：你当前安装的版本。
- **Wanted**：与你的 `package.json` 中定义的范围匹配的最高版本。
- **Latest**：NPM 上发布的最新稳定版本。

---

### 方法 2：手动检查稳定版本
你也可以手动检查最新版本：
```bash
npm show <package-name> version
```
例如：
```bash
npm show element-plus version
npm show vue version
npm show vite version
npm show pinia version
```

---

### 方法 3：安装依赖管理工具
使用 `npm-check-updates`（NCU）可以快速检查并更新依赖版本：
1. 安装 `npm-check-updates`：
   ```bash
   npm install -g npm-check-updates
   ```
2. 检查哪些依赖有新版本：
   ```bash
   ncu
   ```
3. 更新 `package.json` 中的版本号到最新版本：
   ```bash
   ncu -u
   ```
4. 安装更新后的依赖：
   ```bash
   npm install
   ```

---

### 近期稳定版本可能的更新（截至当前时间）
通过手动检查，以下依赖可能已有更新版本（假设你的 `npm outdated` 输出类似以下信息）：

| Package                 | Current   | Latest    | Update Command                     |
|-------------------------|-----------|-----------|-------------------------------------|
| `element-plus`          | `2.4.1`   | `2.5.14`  | `npm install element-plus@latest`  |
| `pinia`                 | `2.1.7`   | `2.1.10`  | `npm install pinia@latest`         |
| `vue`                   | `3.3.4`   | `3.4.1`   | `npm install vue@latest`           |
| `@vitejs/plugin-vue`    | `4.2.3`   | `4.3.1`   | `npm install @vitejs/plugin-vue@latest` |
| `vite`                  | `4.4.5`   | `4.5.3`   | `npm install vite@latest`          |

---

### 建议的更新流程
1. 运行以下命令更新所有依赖到最新版本：
   ```bash
   npm install element-plus@latest pinia@latest vue@latest vite@latest @vitejs/plugin-vue@latest
   ```
2. 更新后测试项目运行是否正常（例如 `npm run dev`）。
3. 如果发现不兼容的情况，查看更新日志（Changelog）或迁移指南，按照指引进行调整。
