<template>
  <div :class="prefixCls">
    <!-- <NLayoutHeader bordered :class="`${prefixCls}-header`">
      <NFlex>
        <NButton type="success"> 导出代码 </NButton>
      </NFlex>
    </NLayoutHeader> -->
    <NLayout position="absolute" :class="`${prefixCls}-ontainer`" has-sider>
      <!--  左侧组件区域开始  -->
      <NLayoutSider content-style="padding: 10px;" :native-scrollbar="false" bordered>
        <FormLeft />
      </NLayoutSider>
      <!--  左侧组件区域结束  -->
      <!--  中间画布区域开始  -->
      <NLayout
        content-style="padding: 0 24px; height: 100%; background-color: #f4f5f5;"
        embedded
        :native-scrollbar="false"
      >
        <FormContent />
      </NLayout>
      <!--  中间画布区域结束  -->
      <!--  右侧属性控制区域开始  -->
      <NLayoutSider class="generate-flow-code-right" :native-scrollbar="false" bordered> right </NLayoutSider>
      <!--  右侧属性控制区域结束  -->
    </NLayout>
  </div>
</template>

<script setup lang="ts">
  import FormLeft from './components/FormLeft/index.vue';
  import FormContent from './components/FormContent/index.vue';

  import { useDesign } from '@/hooks/useDesign';

  const { prefixCls } = useDesign('generate-form');
</script>

<style scoped lang="less">
  @prefix-cls: ~'@{namespace}-generate-form';

  .@{prefix-cls} {
    &-header {
      padding: 20px;
    }
  }
</style>
