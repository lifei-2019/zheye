<template>
  <ul>
    <li v-for="column in list" :key="column.id">
      <img :src="column.avatar" :alt="column.title" height="30" width="30">
      <h5>{{column.title}}</h5>
      <p>{{column.description}}</p>
      <a href="#">进入专栏</a>
    </li>
  </ul>
</template>

<script lang="ts">

import { defineComponent, PropType } from 'vue'

export interface ColumnProps {
  id:number;
  title:string;
  avatar:string;
  description:string;
}

export default defineComponent({
  name: 'ColumnList',
  props: {
    list: {
      // 把构造函数断言成类型 需要借用PropType，这样整个模版中都能实现
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup (props) {
    // props.list[0].id
  }
})
</script>
