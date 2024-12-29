<template>
  <a-layout id="components-layout-demo-responsive">
    <a-layout-sider
      breakpoint="lg"
      @collapse="onCollapse"
      @breakpoint="onBreakpoint"
      v-model:collapsed="collapsed"
      :trigger="null"
      collapsible
    >
      <div class="logo"></div>
      <a-menu v-model:selectedKeys="selectedKeys" theme="dark" mode="inline">
        <a-menu-item key="1">
          <user-outlined />
          <span class="nav-text">nav 1</span>
        </a-menu-item>
        <a-menu-item key="2">
          <video-camera-outlined />
          <span class="nav-text">nav 2</span>
        </a-menu-item>
        <a-menu-item key="3">
          <upload-outlined />
          <span class="nav-text">nav 3</span>
        </a-menu-item>
        <a-menu-item key="4">
          <user-outlined />
          <span class="nav-text">nav 4</span>
        </a-menu-item>
      </a-menu>
    </a-layout-sider>
    <a-layout>
      <a-layout-header class="top-nav-bar">
        <menu-unfold-outlined
          v-if="collapsed"
          class="trigger"
          @click="() => (collapsed = !collapsed)"
        />
        <menu-fold-outlined v-else class="trigger" @click="() => (collapsed = !collapsed)" />
      </a-layout-header>
      <a-layout-content>
        <div class="content-box">content</div>
      </a-layout-content>
      <a-layout-footer class="footer-bar"> Ant Design ©2018 Created by Ant UED </a-layout-footer>
    </a-layout>
  </a-layout>
</template>
<script lang="ts" setup>
import {
  MenuFoldOutlined,
  MenuUnfoldOutlined,
  UploadOutlined,
  UserOutlined,
  VideoCameraOutlined,
} from '@ant-design/icons-vue'
import { ref } from 'vue'
const onCollapse = (collapsed: boolean, type: string) => {
  console.log(collapsed, type)
}
const collapsed = ref<boolean>(false)
const onBreakpoint = (broken: boolean) => {
  console.log(broken)
}

const selectedKeys = ref<string[]>(['4'])
</script>
<style scoped>
.top-nav-bar {
  padding: 0;
  background: #fff;
  height: 50px;
  line-height: 50px;
}
.ant-layout-content {
  box-sizing: border-box;
  height: calc(100vh - 100px);
}
.content-box {
  height: 100%;
  margin: 24px 16px 0;
  background-color: #fff;
  padding: 24px;
}
.footer-bar {
  height: 50px;
  text-align: center;
  line-height: 50px;
  padding: 0;
}
#components-layout-demo-responsive .logo {
  height: 32px;
  background: rgba(255, 255, 255, 0.2);
  margin: 16px;
}

.trigger {
  font-size: 18px;
  line-height: 1;
  padding: 0 24px;
  cursor: pointer;
  transition: color 0.3s;
}

.trigger:hover {
  color: #1890ff;
}

.site-layout-sub-header-background {
  background: #fff;
}

.site-layout-background {
  background: #fff;
}

[data-theme='dark'] .site-layout-sub-header-background {
  background: #141414;
}
</style>
