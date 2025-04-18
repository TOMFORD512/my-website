---
sidebar_position: 1
---

# 管理文档版本

Docusaurus 可以管理多个文档版本。

## 创建一个文档版本

发布一个版本 1.0 的项目：

```bash
npm run docusaurus docs:version 1.0
```

`docs` 文件夹被复制到 `versioned_docs/version-1.0` 并创建 `versions.json`。

你的文档现在有 2 个版本：

- `1.0` 在 `http://localhost:3000/docs/` 用于版本 1.0 的文档
- `current` 在 `http://localhost:3000/docs/next/` 用于 **即将发布的未发布文档**

## 添加一个版本下拉菜单

为了无缝地跨版本导航，添加一个版本下拉菜单。

修改 `docusaurus.config.js` 文件：

```js title="docusaurus.config.js"
export default {
  themeConfig: {
    navbar: {
      items: [
        // highlight-start
        {
          type: 'docsVersionDropdown',
        },
        // highlight-end
      ],
    },
  },
};
```

文档版本下拉菜单出现在你的导航栏中：

![Docs Version Dropdown](./img/docsVersionDropdown.png)

## 更新一个现有的版本

可以在各自的文件夹中编辑版本化的文档：

- `versioned_docs/version-1.0/hello.md` updates `http://localhost:3000/docs/hello`
- `docs/hello.md` updates `http://localhost:3000/docs/next/hello`
