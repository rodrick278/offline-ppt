---
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: false
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS (experimental)
css: unocss
download: true
---
# offline 组件化与快速搭建

2022.08.09

---
layout: two-cols
---
<template v-slot:default>

# 🎈 背景与痛点

<br/>

 - 重复大量的 offline 需求
 - 前端人员不足
 - 重复可抽象的操作
 - 组件与数据耦合
 - 由后端同学完成会有学习成本

</template>

<template v-slot:right>
<br/><br/>
<img src="/firstbg.png"/>

</template>


---
layout: center
---

# 常见组件类型划分

---
layout: two-cols
---
<template v-slot:default>

# 📃菜单&路由 JSON 配置化

<img src="/layout.png"/>

</template>
<template v-slot:right >
<v-click>
<br/><br/>

```json {all|2-6|7-14|all}
{
  key: 'key1',
  icon: 菜单图标,
  name: '名称',
  breadName: '面包屑1',
  authCode: '权限code',
  children: [ // 子级
    {
      key: '',
      href: '/xx || https://xxx.com',
      name: '',
      breadName: '面包屑1/面包屑2',
      authCode: '',
      notMenu: bool, // 是否非菜单级路由(如编辑页等
    },
  ],
}
```
</v-click>
</template>


<style>
.slidev-code-wrapper {
  margin-left: 20px !important;
}
</style>

---

# 📃 展示页

<img src="/table.png"/>

<div class="flex mt-8">
  <ul v-click class="ml-26">
    <li class="font-bold">Search Form
      <ul class="font-normal">
      <li>label</li>
      <li>value</li>
      <li>validate</li>
      <li>...</li>
    </ul>
    </li>
  </ul>
  <ul v-click class="ml-54">
    <li class="font-bold">Table
      <ul class="font-normal">
      <li>字段展示</li>
      <li>操作
        <ul>
          <li>编辑 -> 跳转route带参</li>
          <li>删除</li>
        </ul>
      </li>
    </ul>
    </li>
  </ul>
</div>

---
layout: two-cols
---

# 📃 新增/编辑页

<br />

 - 区分新增编辑
 - 获取详情信息
 - 表单组件渲染
 - 校验后提交

::right::

<img src="/edit.png"/>

---


# 📃 图表

常用的图标库基本都有一套自己的 option,
基础的配置很简单,
但是复杂的样式会有较高的学习成本

<img v-click-hide src="/chart.png"/>
<img v-after class="max-h-full" src="/chartOption.png"/>

<style>
.slidev-vclick-hidden {
  display: none
}
</style>

---

# 🎨 样式定制

 - 基于 Antd 的样式变量

 <img class="max-h-80" src="/antdcss.png"/>


[Link](https://github.com/ant-design/ant-design/blob/master/components/style/themes/default.less)

---
layout: two-cols
---

# 🔩 复杂但通用的业务定制

利用不同颗粒度**物料**管理定制化需求

<br/>

- 📄 **组件** - 功能确定且具有复杂度和通用性
    - 部门人员树组件
    - 地区联动器
    - ...
- 📑 **区块** - 功能确定且具有复杂度和通用性
- 📰 **页面模板** - 整体页面定制化



::right::

 <img class="mt-20" src="/components.png"/>

---
layout: center
---
# 方案

---

# 👨‍💻配置化方案
市面上的产品: [AMIS](https://aisuda.bce.baidu.com/amis/zh-CN/docs/index)

 <img v-click-hide class="h-100"  src="/amis.png"/>


<v-after>

 - **缺点**
    - 扩展性被JSON限制
    - 复杂交互难以描述
    - 配置越多 对于文档的要求越高

</v-after>


<style>
.slidev-vclick-hidden {
  display: none
}
</style>

---

# 🎈 畅想

<img class="max-h-[90%]" src="/frame1.png"/>

---

# 🎈 畅想

<img class="max-h-[90%]" src="/frame2.png"/>



