# vee-validate

本文件为项目根目录的中文文档，翻译自 [README.md](README.md)。
部分官方文档已翻译，示例见 [docs/src/pages/guide/zh-CN/overview.mdx](docs/src/pages/guide/zh-CN/overview.mdx)。
另可参考 [docs/src/pages/guide/zh-CN/components/validation.mdx](docs/src/pages/guide/zh-CN/components/validation.mdx) 查看组件章节的翻译示例。

## 特性

- **🍞 简易：** 声明式表单验证，易于上手
- **🧘‍♀️ 灵活：** 支持同步、异步、字段级或表单级验证
- **⚡️ 高效：** 直观的 API 和轻量的体积，助你更快完成表单
- **🏏 精简：** 仅处理复杂表单逻辑，其余完全由你掌控
- **😎 与 UI 无关：** 既可搭配原生元素，也可与各种 UI 库组件结合
- **🦾 渐进式：** 无论简单增强还是复杂项目都适用
- **✅ 内置规则：** 附带 25+ 常用规则，满足大多数需求
- **🌐 国际化：** 内置 45+ 语言包，社区贡献丰富

## 快速开始

### 安装

```sh
yarn add vee-validate # 使用 yarn
npm install vee-validate --save # 使用 npm
```

### Vue 版本支持

| Vue 版本 | vee-validate 版本 | 文档地址 |
| -------- | ---------------- | -------------------------------- |
| `2.x`    | `2.x` 或 `3.x`    | [v2](https://vee-validate.logaretm.com/v2) 或 [v3](https://vee-validate.logaretm.com/v3) |
| `3.x`    | `4.x`            | [v4](https://vee-validate.logaretm.com/v4) |

### 使用方式

下面展示了在 Vue 应用中使用 Composition API 创建表单并进行验证的示例：

```vue
<script setup>
import { useForm } from 'vee-validate'

function required(value) {
  return value ? true : '此字段为必填'
}

const { defineField, handleSubmit, errors } = useForm({
  validationSchema: {
    field: required,
  },
})

const [field, fieldProps] = defineField('field')

const onSubmit = handleSubmit((values) => {
  console.log(values)
})
</script>

<template>
  <form @submit="onSubmit">
    <input v-model="field" v-bind="fieldProps" />
    <span>{{ errors.field }}</span>
    <button>提交</button>
  </form>
</template>
```

更多信息可查看 [英文文档](README.md)。欢迎社区协助补充其余文档的中文翻译。
