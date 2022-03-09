<template>
    <div class="ChaifaRoomPop">
        <div class="top">
			<div class="sign-line-one">
				<div class="sign-img"></div>
				<div class="sign-name">{{heightBuildName}}</div>
				<div class="sign-close" >×</div>
			</div>
			<div class="sign-container" v-for="(item, index) in heightBuildData" :key="index">
				<div class="sign-data-show">
					<div class="sign-content ">{{item.key}} </div>
					<div class="sign-contentfh"> | </div>
					<div class="sign-value">{{item.value}}</div>
				</div>
			</div>
			
			<div class="ChaifaRoomPop-main">
                <div class="messagelist" v-for="item in messagelist" :key="item.id">
                    <div class="listgroup">
                        <div class="main-key">{{item.key}}</div>
                        <div class="main-fh">:</div>
                        <div class="main-value">{{item.value}}</div>
                    </div>
                </div>
            </div>
			

		</div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            heightBuildName:'柴发室',
            heightBuildData:[
                {
                    id:1,
                    key:'位置',
                    value:'10层'
                },
                 {
                    id:2,
                    key:'储油量',
                    value:'12m³'
                },
                 {
                    id:3,
                    key:'发电机',
                    value:'2个'
                },
            ],
            messagelist:[
                {
                    id:1,
                    key:'1号柴油发电机',
                    value:'100KW'
                },
                {
                    id:2,
                    key:'2号柴油发电机',
                    value:'100KW'
                },
            ]
        }
    }
}
</script>
<style lang="less" scoped>
.ChaifaRoomPop{
    .sign-fire-alarm{
	display: none;
	margin-top:10px;
	margin-bottom:10px;
	border:1px solid red;
	color: white;
	background: rgba(1, 10, 15, 0.7);
	padding: 5px;
	height: 95px;
	overflow: auto;

}
.fire-alarm-time{
	overflow: auto;
	
}
#fire-alarm-detail-deviceRemark{
	overflow:hidden;
	text-overflow:ellipsis;
	white-space:nowrap;
}
#fire-alarm-detail-partRemark{
	overflow:hidden;
	text-overflow:ellipsis;
	white-space:nowrap;
}
.fire-alarm-detail{
	overflow:hidden;
	text-overflow:ellipsis;
	white-space:nowrap;
	color: red;
}
.fire-alarm-address{
	// border-bottom: 1px solid white;
	color: #FFF;
}

.hgpage {
	//width: 150px;
	display: flex;
	//align-items: flex-end;
	//justify-content: center;
}



.top {
	width: 200px !important;
	//height: 100px  !important;
	/* min-height: 90px; */
	background: rgba(0,0,0,0.6);
	border: 1px solid #00FFCC;
		/*padding-top:10px;*/
	box-sizing: border-box;
	background-size: 100% 100%;
	user-select: none;
	padding:0 10px 10px 10px;
	/*position: absolute;*/
	display: flex;
	flex-direction: column;
	/*margin-top: -20px;*/
	position: relative;
	
	.sign-line-one {
		display: flex;
		flex-direction: row;
		font-size: 16px;
		font-family: Microsoft YaHei;
		font-weight: 700;
		color: #FFF;
		margin:3px 10px 0 0px;
		
		.sign-close {
			position: absolute;
			top: -10px;
			right: 10px;
			font-size: 25px;
			cursor: pointer;
		}
	}
	
	.sign-data-show {
		display: flex;
		flex-direction: row;
		align-items: center;
		
		.sign-content {
			font-size: 16px;
			font-family: Microsoft YaHei;
			font-weight: 400;
			color: #00FFCC;
			margin:3px 10px 0 0px;
			//width: 60px;
			text-align-last: justify;
            width: 50px;
		}
        .sign-contentfh{
            font-size: 16px;
			font-family: Microsoft YaHei;
			font-weight: 400;
			color: #00FFCC;
			margin:3px 10px 0 0px;
			//width: 60px;
			text-align-last: justify;
        }
		
		.sign-value {
			color: #FFF;
		}
		
		
	}
	
	
	
}
.ChaifaRoomPop-main{
    background: rgba(0,0,0,0.7);
    padding: 5px;
    box-sizing: border-box;
    margin-top: 5px;
    .messagelist{
        .listgroup{
            display: flex;
            color: #fff;
            font-size: 16px;
            font-weight: 400;
            margin-bottom: 2px;
            .main-key{
                width: 106px;
                overflow: hidden;
                text-overflow:ellipsis;
                white-space: nowrap;
            }
        }
    }
}
}


</style>