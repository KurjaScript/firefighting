/**
* @AreaList.vue
* @description 区域列表
* @ 进行五个区域 - 罐区、储罐、装置、仓库、堆场、污水处理、火炬 的菜单切换，获取当前选中企业的区域数据
* @author fanjiahong
* @update zhangjun 2021/12/17
*/
<template>
    <div class="AreaList animate__animated animate__fadeInLeft">
        <div class="AreaList-cd">
            <div class="gq-group"  v-for="(item,index) in list" :key="index" @click="setActiveItem(index)">
                <div class="ggys gq" :class="{active: current == index }"   v-show="item.state==1">
                    <div>{{item.mc}}</div>
                </div>
                <div class="ggys cg" :class="{cgactive: current == index }" v-show="item.state==0">
                    <div class="gq-title">{{item.mc}}</div>
                </div>
            </div>
        </div>
        <div class="block">
            <el-carousel style="width:480px;" indicator-position="none"  :autoplay="false" arrow="never" ref="cardshow">
                <el-carousel-item v-for="(item,index) in zjlist" :key="index">
									  
                    <components :is="item.zjmc" :currentIndex="index" @closeAreaList="closeAreaList" @setWindowFixedRight="setWindowFixedRight"></components>
                </el-carousel-item>
            </el-carousel>
        </div>
    </div>
</template>
<script>
import AreaListGq from './AreaListGq'
import AreaListCg from './AreaListCg'
import AreaListZz from './AreaListZz'
import AreaListCk from './AreaListCk'
import AreaListDc from './AreaListDc'
import AreaListWs from './AreaListWs'
import AreaListHj from './AreaListHj'
export default {
    components:{
    	AreaListGq,
			AreaListCg,
			AreaListZz,
			AreaListCk,
			AreaListDc,
			AreaListWs,
			AreaListHj
		},
		data(){
        return {
            current: 0,
            list:[
                {
                    id:1,
                    mc:'罐区',
                    state:1,
                },
                {
                    id:2,
                    mc:'储罐',
                    state:0,
                },
                {
                    id:3,
                    mc:'装置',
                    state:1,
                },
                {
                    id:4,
                    mc:'仓库',
                    state:0,
                },
                {
                    id:5,
                    mc:'堆场',
                    state:1,
                },
								{
									id:5,
									mc:'污水处理',
									state:0,
								},
								{
									id:5,
									mc:'火炬',
									state:1,
								}
            ],
            zjlist:[
                {
                    zjmc:"AreaListGq",
                },
                 {
                    zjmc:"AreaListCg",
                },
                 {
                    zjmc:"AreaListZz",
                },
                 {
                    zjmc:"AreaListCk",
                },
                 {
                    zjmc:"AreaListDc",
                },
								{
									zjmc:"AreaListWs",
								},
								{
									zjmc:"AreaListHj",
								},
							
            ]
        }
    },
    methods:{
			// 设置选中状态
			setActiveItem(index){
					this.current = index;
					this.$store.state.currentAreaListIndex = index;
					this.$refs.cardshow.setActiveItem(index);
			},
			// 关闭 区域列表
			closeAreaList() {
					this.$emit('deleteWindowName', ['areaList', 'AreaList']);
					this.$store.state.isAreaListDisplay = false;
					this.$store.state.isAreaListLegendDisplay = false;
					window.map.removeAllOverlays(); // 清除所有标记
			},
			
			// 将当前窗口固定到右边
			setWindowFixedRight() {
				if(this.$store.state.openWindowList.indexOf('areaList') != -1) {
					this.$store.state.floatRightList.push(this.$store.state.openWindowList.pop());
				}
				if(this.$store.state.floatRightList.indexOf('areaList') == -1) {
					this.$store.state.floatRightList.push('areaList')
				}
				let areaListWindow = document.getElementsByClassName("AreaList");
				if(areaListWindow) {
					areaListWindow[0].style.float = 'right';
					areaListWindow[0].style.right = '10px';
					areaListWindow[0].style.left = 'unset';
				}
			}
    }
}
</script>
<style lang="less">
.AreaList{
		float: left;
    position: relative;
    //position: absolute;
    //top: 120px !important;
    top: 20px !important;
    left: 25px;
    /*right: 540px !important;*/
    display: flex;
    .el-carousel__item h3 {
        color: #475669;
        font-size: 14px;
        opacity: 0.75;
        line-height: 150px;
        margin: 0;
    }
    
    .el-carousel__item:nth-child(2n) {
        background-color: rgba(0, 0, 0, 0);
    }
    
    .el-carousel__item:nth-child(2n+1) {
        background-color: rgba(0, 0, 0, 0);
    }
    .el-carousel__container{
        height: 967px;
    }
    .AreaList-cd{
        .gq{
            width: 42px;
            height: 165px;
            margin-top: -33px;
            cursor: pointer;
            background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/active2.png');
        }
        .cg{
            width: 42px;
            height: 165px;
            cursor: pointer;
            margin-top: -33px;
            background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/active1.png');
        }
        .zz{
            width: 42px;
            height: 165px;
            cursor: pointer;
            margin-top: -33px;
            background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/active2.png');
        }
        .ck{
            width: 42px;
            height: 165px;
            cursor: pointer;
            margin-top: -33px;
            background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/active1.png');
        }
        .dc{
            width: 42px;
            height: 165px;
            cursor: pointer;
            margin-top: -33px;
            background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/active2.png');
        }
				.ws{
					width: 42px;
					height: 165px;
					cursor: pointer;
					margin-top: -33px;
					background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/active1.png');
				}
				.hj{
					width: 42px;
					height: 165px;
					cursor: pointer;
					margin-top: -33px;
					background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/active2.png');
				}
        .ggys{
            display: flex;
            justify-content: center;
            align-items: center;
            align-self: center;
            font-size: 18px;
            font-family: Microsoft YaHei;
            font-weight: bold;
            color: #FFFFFF;
            -webkit-writing-mode: vertical-rl;
            writing-mode: vertical-rl;
        }
        .active{
            width: 42px;
            height: 160px;
            margin-top: -33px;
            cursor: pointer;
            background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/bactive.png');
        }
        .active:first-child{
            width: 42px;
            height: 165px;
            // margin-top: -33px;
            cursor: pointer;
            background-image: url('../../../../assets/img/Gansu/Huagong/AreaList/bactive.png');
        }
        .cgactive{
            width: 42px;
            height: 168px;
            cursor: pointer;
            margin-top: -33px;
            transform: rotate(180deg);
            background: url('../../../../assets/img/Gansu/Huagong/AreaList/bactive.png') 0 0 no-repeat;
            .gq-title{
                transform: rotate(180deg);
            }
        }
        
    }
    .AreaList-cd .gq-group:first-child{
        margin-top: 32px;
        
    }
}
</style>
