<!-- ///////////////////////// 模塊說明 ///////////////////////// -->
## 【one way data flow DOME】

- vue-project\src\components\Content.vue
- vue-project\src\components\Menu.vue
- [[重構倒數第03天] - One-Way Data Flow 單向資料流](https://ithelp.ithome.com.tw/articles/10273655)

## 【安裝 SCSS】

- [CSS 预处理器](https://cn.vitejs.dev/guide/features.html#css)

```HTML
npm add -D sass
```

### [Skeleton](https://ithelp.ithome.com.tw/articles/10260925)

- [DOME](https://codepen.io/MikeCheng1208/pen/PomyJNa)

### [依賴注入](https://cn.vuejs.org/api/composition-api-dependency-injection.html#provide)

- provide() 接受两个参数：第一个参数是要注入的 key，可以是一个字符串或者一个 symbol，第二个参数是要注入的值。
- [[重構倒數第26天] - 你可能不需要Vuex (You might not need Vuex)](https://ithelp.ithome.com.tw/articles/10260315)
- 用 readonly 函數包起來，就是要避免外面 inject 的時候不小心改到 state 的資料
- [Vue 3 中的 Provide 與 Inject](https://uu9924079.medium.com/vue-3-%E4%B8%AD%E7%9A%84-provide-%E8%88%87-inject-a1da5b3fc28c)

### HTML5 拖曳功能測試

- DOME => src\components\DragAndDropAPI.vue
- 套件 => src\components\vue_draggable_next_dome.vue"
- [vue.draggable.next => vue3](https://github.com/SortableJS/vue.draggable.next)

``` html
npm i -S vuedraggable@next
import draggable from 'vuedraggable'


<draggable v-model="myArray" tag="transition-group" item-key="id">
  <template #item="{element}">
      <div> {{element.name}} </div>
  </template>
</draggable>
```

- [vue.draggable.next DOME](https://sortablejs.github.io/Vue.Draggable/#/simple)

### 原生HTML5彈窗DOME

- DOME => src\components\Dialog.vue
- [HTML原生弹窗dialog标签](https://blog.csdn.net/lfl976/article/details/121942324)


--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
<!-- ///////////////////////// 系統預設 ////////////////////// -->

# vue-project

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```
