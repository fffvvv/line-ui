<template>
  <main>
    <section>
      <h1>
        Button 按钮
      </h1>
    </section>
    <section>
      <h1>基础用法</h1>
      <div class="line-row">
        <Button type="main">主要按钮</Button>
        <Button type="button">默认按钮</Button>
        <Button type="link">链接按钮</Button>
        <Button type="text">文本按钮</Button>
      </div>
      <div class="line-row">

      </div>
    </section>
    <section>
      <h1>
        Sizes
      </h1>
      <div>
        <div class="line-row">
          <Button type="main" size="lg">超大按钮</Button>
          <Button type="main" size="md">很大按钮</Button>
          <Button type="main" size="sm">大按钮</Button>
          <Button type="main" size="xs">中按钮</Button>
        </div>
        <div class="line-row">
          <Button size="lg">超大按钮</Button>
          <Button size="md">很大按钮</Button>
          <Button size="sm">大按钮</Button>
          <Button size="xs">中按钮</Button>
        </div>
        <div class="line-row">
          <Button type="link" size="lg">超大按钮</Button>
          <Button type="link" size="md">很大按钮</Button>
          <Button type="link" size="sm">大按钮</Button>
          <Button type="link" size="xs">中按钮</Button>
        </div>
        <div class="line-row">
          <Button type="text" size="lg">超大按钮</Button>
          <Button type="text" size="md">很大按钮</Button>
          <Button type="text" size="sm">大按钮</Button>
          <Button type="text" size="xs">中按钮</Button>
        </div>
      </div>
    </section>
    <section>
      <h1>点击事件</h1>
      <Button @click="onClick">点我</Button>
    </section>
    <section>
      <h1>样式</h1>
      <div>
        <div class="line-row">
          <Button type="main">原始按钮</Button>
          <Button >原始按钮</Button>
          <Button type="link">原始按钮</Button>
          <Button type="text">原始按钮</Button>
        </div>
        <div class="line-row">
          <Button theme="normal" type="main">普通样式</Button>
          <Button theme="normal">普通样式</Button>
          <Button theme="normal" type="link">普通样式</Button>
          <Button theme="normal" type="text">普通样式</Button>
        </div>
        <div class="line-row">
          <Button theme="success" type="main">成功</Button>
          <Button theme="success">成功</Button>
          <Button theme="success" type="link">成功</Button>
          <Button theme="success" type="text">成功</Button>
        </div>
        <div class="line-row">
          <Button theme="warning" type="main">警告</Button>
          <Button theme="warning">警告</Button>
          <Button theme="warning" type="link">警告</Button>
          <Button theme="warning" type="text">警告</Button>
        </div>
        <div class="line-row">
          <Button theme="danger" type="main">错误</Button>
          <Button theme="danger">错误</Button>
          <Button theme="danger" type="link">错误</Button>
          <Button theme="danger" type="text">错误</Button>
        </div>
      </div>
    </section>
    <section>
      <h1>禁用状态</h1>
      <div>
        <Button disabled>禁用按钮</Button>
        <Button type="link" disabled>禁用链接按钮</Button>
        <Button type="text" disabled>禁用按钮</Button>
      </div>
    </section>
    <section>
      <h1>加载中</h1>
      <div>
        <Button loading>加载中</Button>
        <Button>加载完毕</Button>
      </div>
    </section>
  </main>
</template>
<script lang="ts">
import Button from "../lib/Button.vue";

export default {
  components: {Button},
  setup() {
    const onClick = () => {
      alert('点了')
    };
    return {onClick};
  },
};
</script>
