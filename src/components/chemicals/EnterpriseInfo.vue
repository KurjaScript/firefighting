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
.container-header {
    display: flex;
    height: 14px;
    padding: 10px 19px 0 20px;
    box-sizing: border-box;
    justify-content: space-between;
}
.container-line {
    width: 410px;
    height: 1px;
    background: rgba(0, 255, 222, 0.3);
    position: relative;
}
    .container-line::before {
        position: relative;
        content: "";
        width: 10px;
        height: 3px;
        top: -1px;
        left: 0;
        background: #00ffde;
    }
    .container-line::after {
        position: relative;
        contain: "";
        width: 10px;
        height: 3px;
        top: -1px;
        right: 0;
        background: #00ffde;
    }
</style>