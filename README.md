# vue-json-schema-form
基于 Vue ElementUi JsonSchema快速构建一个带完整校验的form表单.

## 快速体验
* [演示demo](https://form.lljj.me/ "Vue JSON Schema Form Demo")
* [查看文档](https://vue-json-schema-form.lljj.me/ "Vue JSON Schema Docs")
* [源代码](https://github.com/lljj-x/vue-json-schema-form "Vue JSON Schema github")
* [使用场景 - 前端可视化编辑演示](https://form.lljj.me/vue-editor.html)
* [不支持部分和更新计划](https://vue-json-schema-form.lljj.me/zh/guide/todo.html)

![](https://7.luochongfei.top/vue-json-schema-form.gif?1)

``` bash
# 安装
npm install --save @lljj/vue-json-schema-form

# 或者：
yarn add @lljj/vue-json-schema-form
```

```vue
<template>
    <VueForm
        v-model="formData"
        :schema="schema"
    >
    </VueForm>
</template>

<script >
    //  使用
    import VueForm from '@lljj/vue-json-schema-form';

    export default {
        name: 'Demo',
        components: {
            VueForm
        },
        data() {
            return {
                formData: {},
                schema: {
                    type: 'object',
                    required: [
                        'firstName'
                    ],
                    properties: {
                        firstName: {
                            type: 'string',
                            title: 'First name',
                            default: 'Jun'
                        },
                        lastName: {
                            type: 'string',
                            title: 'Last name'
                        },
                    }
                }
            };
        }
    };
</script>
```

## 运行Demo
```ssh
# 安装依赖
yarn install

# 运行demo页 （同时运行 vue-editor，schema-form-eidtor）
yarn run demo:dev

# formEditor http://127.0.0.1:8800/
# 活动编辑器 http://127.0.0.1:8800/vue-editor.html

# 运行demo页 (单个 schema-form-eidtor)
yarn run demo:dev --dir=index

# 运行demo页 (单个 vue-editor)
yarn run demo:dev --dir=vue-editor

```

## 相关资料
[JSON Schema](https://json-schema.org/understanding-json-schema/index.html) |
[Vue](https://cn.vuejs.org/) |
[Element Ui](https://element.eleme.io/)

### 为何开发
原本是在很久前公司流产的项目类似淘宝店铺装修，也可以叫做前端可视化编辑。为了解决数据配置表单的通用性，所以使用json-schema描述数据结构，动态生成表单。

这样做的好处除了解决在每个配置表单的重复工作，服务端也可以基于同一份schema保持和前端一致的校验规则，不过对于使用 vue elementUi并未找到合适库可以直接使用，所以在后面一段时间决定自己实现一个 ..

## License
Apache-2.0
