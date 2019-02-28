<template>
	<div class="report">
		<div class="reportContent">
			<div class="sharingTitle">
				<h3>园所经营</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>财务报表</h3>
				</div>
				<div class="distribution">
					<ul class="park">
						<h3>所属园区:</h3>
						<li class="style">全部</li>
						<li>星光幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
					</ul>
					<ul class="park">
						<h3>所属园区:</h3>
						<li class="style">全部</li>
						<li>星光幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
					</ul>
					<div class="sharingTime">
						<div class="sharingDate">
							<span class="demonstration">时间</span>
						    <el-date-picker
						      v-model="value6"
						      type="daterange"
						      range-separator="~"
						      start-placeholder="开始日期"
						      end-placeholder="结束日期">
						    </el-date-picker>
						</div>
						<div class="sharingInput">
							<el-row>
								<el-input
								    placeholder="请输入内容"
								    prefix-icon="el-icon-search"
								    v-model="input21">
								</el-input>
								<el-button class="departureStyle">搜索</el-button>
							</el-row>
						</div>
					</div>
				</div>
				<div class="bill">
					<div class="bill_one">
						<div class="one_1">
							<h3 class="mony">12323元</h3>
							<span class="text">边界利益</span>
						</div>
						<div class="one_2">
							<h3 class="mony">12323元</h3>
							<span class="text">边界利益</span>
						</div>
						<div class="one_1">
							<h3 class="mony">12323元</h3>
							<span class="text">边界利益</span>
						</div>
					</div>
					<div class="bill_one">
						<div class="one_1">
							<h3 class="mony">12323元</h3>
							<span class="text">边界利益</span>
						</div>
						<div class="one_2">
							<h3 class="mony">12323元</h3>
							<span class="text">边界利益</span>
						</div>
						<div class="one_1">
							<h3 class="mony">12323元</h3>
							<span class="text">边界利益</span>
						</div>
					</div>
				</div>
				<div class="histogram">
					<div id="myChart_one" :style="{width: '882px', height: '466px'}"></div>
					<div id="myChart_two" :style="{width: '882px', height: '466px'}"></div>
					<div id="myChart_three" :style="{width: '882px', height: '466px'}"></div>
					<div id="myChart_fout" :style="{width: '882px', height: '466px'}"></div>
					
				</div>
			</div>
			
		</div>
	</div>
</template>

<script>
export default {
  	name: 'report',
  	data () {
    	return {
    		input21: '',
    		pickerOptions2: {
	          		shortcuts: [{
	//          		text: '最近一周',
	    				onClick(picker) {
				      		const end = new Date();
				     		const start = new Date();
				     		start.setTime(start.getTime() - 3600 * 1000 * 24 * 7);
				     		picker.$emit('pick', [start, end]);
			    		}
			  		}, {
	//          		text: '最近一个月',
					    onClick(picker) {
					      	const end = new Date();
					      	const start = new Date();
					      	start.setTime(start.getTime() - 3600 * 1000 * 24 * 30);
					      	picker.$emit('pick', [start, end]);
					    }
					}, {
	//          		text: '最近三个月',
	    				onClick(picker) {
	      					const end = new Date();
	      					const start = new Date();
	     		 			start.setTime(start.getTime() - 3600 * 1000 * 24 * 90);
	      					picker.$emit('pick', [start, end]);
	    				}
	  				}]
				},
				value6: ''
    	}
  	},
	//柱状图样式
	mounted(){
    	this.drawLine('myChart_one','应收 金额/元');
    	this.drawLine('myChart_two','返费 金额/元');
    	this.drawLine('myChart_three','变动费 金额/元');
    	this.drawLine('myChart_fout','固定费 金额/元');
  	},
  	methods: {
  		//第一个柱状图
    	drawLine(reportMyID,title){
        	// 基于准备好的dom，初始化echarts实例
        	let myChart = this.$echarts.init(document.getElementById(reportMyID))
        	// 绘制图表
        	myChart.setOption({
		 		color: ['#a1cb46'],
				title: {
		            text: title,
		            x: '16',
		            y: '20',
		            itemGap: 30,
		            backgroundColor: '#fff',
		            textStyle: {
		              	fontSize: 24,
		              	fontWeight: 'bolder',
		              	color: 'rgb(51,51,51)'
		            }
		        },
//		        legend: {
//			        x:'285',
//			        y:'20',
//			        data:['应收金额','应收净额','占比'],
////			        alin
//			        textStyle:{
//			        	fontSize:20,
//			        	color:'#333333'
//			        }
//			    },
		    	grid: {
			    	top:'20%',
			        left: '2%',
			        right: '2%',
			        bottom: '3%',
			        containLabel: true
		    	},
		    	xAxis : [
			        {
			            type : 'category',
			            data : ['应收托费', '应收伙食费', '应收定金', '应收监控', '抵定金', '应收车费', '应收伙食费'],
			            axisTick: {
			                alignWithLabel: true
			            },
			            axisLabel: {
	                        show: true,
	                        textStyle: {
	                            color: '#000',
	                            fontSize:16,
	                        }
	            		}
			        }
		    	],
			    yAxis : [
			        {
			            max:'300000',
	            		min:'0',
	            		axisLabel: {
	                        show: true,
	                        textStyle: {
	                            color: '#000',
	                            fontSize:16,
	                        }
	            		}
			        }
			    ],
			    series : [
			        {
			        	name:'应收金额',
			            type:'bar',
			            barWidth: '30%',
			            data:[10000, 52000, 200000, 234000, 190000, 100000, 200000]
			        },
			    ]
		    });
		},
    	//第一个柱状图END
	}
}
</script>
<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.report{
  		width: 1200px;
  		margin: 0 auto;
  		position: relative;
  		.reportContent{
			width: 912px;
			position: absolute;
			top: 0;
			left: 285px;
			.bill{
				width: 100%;
				height: 472px;
				background: #FCFCFC;
				.bill_one{
					width:890px;
					margin:15px auto 0;
					overflow:hidden;
					div{
						float:left;
						text-align: center;
					}
					.one_1{
						width:272px;
						height: 208px;
						background: #fff;
						border-radius: 5px;
						box-shadow: 10px 10px 10px #f2f2f2;
					}
					.mony{
						padding-top: 68px;
						font-size: 36px;
						color: #a1cb46;
					}
					.text{
						display: block;
						font-size: 36px;
						margin-top: 30px;
						color: #181818;
					}
					.one_2{
						width: 272px;
						height: 208px;
						background: #fff;
						border-radius: 5px;
						box-shadow: 10px 10px 10px #f2f2f2;
						margin-left: 35px;
						margin-right: 35px;
					}
				}
			}
		}
  	}
</style>
<style>
	.report .el-button--text{
		color: #9BC248;
		font-size: 18px;
	}
	.report .el-date-editor--daterange{
		height: 32px;
		margin-top: 10px;
	}
	.report .el-input{
		width: 180px;
		height: 32px;
	}
	.report .el-input__inner{
		height: 32px;
	}
	.report .el-button{
		padding: 5px 10px;
		height: 32px;
	}
	.report .departureStyle{
		margin-left: 45px;
	}
</style>
