<h3 id="d7S2O">Vue3 插槽的使用</h3>
1. 作用域插槽（子组件会影响到父组件）

```vue
<div>
	<slot :arr="arr">gggggggggg
  </slot>
</div>

<script setup>
    let arr = ref([1, 2,3])
</script>
```

```vue
import child from './child.vue'
<div>
  <child >
    <template v-slot="scope"> <!-- v-slot 放在template标签上 -->
      {{ scope.arr }}
    </template>
  </child>
</div>
```



2. 具名插槽（父组件会影响到子组件的值）

```vue
<div>
  <slot name="W-qh"></slot>
  <slot name="he"></slot>
</div>
```

```vue
<child>
  <template v-slot:W-qh>W-qh</template>
  <template v-slot:he>he</template>
</child>
```



3. 默认插槽（父组件会影响到子组件的值）

```vue
<div>
  <slot></slot>
</div>
```

```vue
<child>
	hi
</child>
```





后端：node-rsa crypto



前端：jsencrypto

error:0200009F:rsa routines::pkcs decoding error： 只用修改加密的长度

[https://blog.csdn.net/dark_cy/article/details/133603332](https://blog.csdn.net/dark_cy/article/details/133603332)



pinia: [https://wenku.csdn.net/answer/724dd79502f84fd18c7c2f351c2972c0](https://wenku.csdn.net/answer/724dd79502f84fd18c7c2f351c2972c0)

再main.ts中

```typescript
import { createApp } from "vue";
import "./style.css";
import App from "./App.vue";
import router from "./router";
import { createPinia } from "pinia";
import './assets/iconfont/download/font/iconfont.js'
let pinia: any = createPinia()
createApp(App).use(router).use(pinia).mount("#app");
```



<h3 id="GHCLU">Vuex 在  Vue3中的使用</h3>
1. 用 router.push 跳转的页面 Vuex 数据会丢失。解决：用 vuex-persistedstate 插件

