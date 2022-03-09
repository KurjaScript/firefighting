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
        <div class="tank-field-top">
            <div class="company-name">
                <el-tooltip class="item" effect="dark" placement="top">
                    <div class="tank-field-name">{{currentCompanyData.areaName}}</div>
                </el-tooltip>
                <div class="tank-field-title" v-show="currentCompanyData.danger_source_info">{{currentCompanyData.danger_source_info}}</div>
            </div>
            <div class="garden-name">
                <el-tooltip class="item" effect="dark" :content="gardenInfo.garden_address" placement="top">
                    <div class="garden-address">{{gardenInfo.garden_address}}</div>
                </el-tooltip>
            </div>
        </div>
    </div>
</template>
<script>
export default{
    data(){
        return {
            currentCompanyData:{
                areaName: '中通服咨询设计研究院',
                danger_source_scale: '四级',
                danger_source_info: '三级',
            },
            gardenInfo:{
                garden_address: '新城科技园',

            }
        }
    },

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
.tank-field_top {
    height: 49px;
    width: 400px;
    display: flex;
    flex-direction: column;
    top: 31px;
    font-size: 20px;
    font-family: Microsoft YaHei;
    font-weight: bold;
    line-height: 40px;
    margin-left: 10px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
.company-name {
    height: 49px;
    width: 400px;
    display: flex;
    flex-direction: column;
    top: 31px;
}
.tank-field-name {
    width: 380px;
    height: 40px;
    font-size: 20px;
    font-family: Microsoft YaHei;
    font-weight: bold;
    line-height: 40px;
    margin-left: 10px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
.garden-name {
    display: flex;
    flex-direction: row;
    height: 40px;
    align-items: center;
}
.garden-address {
    font-size: 16px;
    width: 367px;
    height: 20px;
    margin-left: 10px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    font-weight: 400;
}




</style>