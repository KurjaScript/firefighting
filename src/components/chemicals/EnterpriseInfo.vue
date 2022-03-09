/8
* @EnterpriseInfo.vue
* @description 企业信息组件
* 包含以下模块及逻辑：
* 1. 企业安全联系人： 点击 控制 企业联系人面板的显隐
* 2. 
*/

<template>
    <div class="enterprise-info">
        <div class="container-header">
            <div class="container-line"></div>
        </div>
    </div>
</template>
<script>
export default{
   
}
</script>
<style lang="less" scoped>
.enterprise-info {
    box-sizing: border-box;
    float: left;
    position: relative;
    overflow-x: hidden;
    top: 20px;
    left: 20px;
    width: 480px;
    height: 976px;
    padding: 0 0 0 10px;
    background: linear-gradient(
        90deg,
        rgba(10, 25, 50, 0.54),
        rgba(3, 40, 53, 0.29)
    );
}
</style>