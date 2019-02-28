<template>
	<div class="taskmanagement">
		<div class="taskmanagementContent">
			<div class="sharingTitle">
				<h3>园所经营</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>任务管理</h3>
				</div>
				<div class="distribution">
					<ul class="park">
						<h3>选择指标:</h3>
						<el-checkbox-group v-model="checkList">
						    <el-radio v-model="radio" label="1">招生指标</el-radio>
  							<el-radio v-model="radio" label="2">退园指标</el-radio>
  							<el-radio v-model="radio" label="3">利润指标</el-radio>
						</el-checkbox-group>
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
					<ul class="park">
						<h3>所属班级:</h3>
						<li class="style">全部</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
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
					</div>			
				</div>
				<div class="percentage">
					<div class="rate">
						<div class="security">							
							<i></i>
							<h5>安全率</h5>						
							<span>
								时间&nbsp;&nbsp;2018/05/20
							</span>
						</div>
						<div class="complaint">
							<span class="estimate">
								预计家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
							<span class="actual">
								实际家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
						</div>
						<button class="preservation">保存</button>
					</div>
					<div class="rate">
						<div class="security">
							<i></i>
							<h5>家长投诉率</h5>
							<span>
								时间&nbsp;&nbsp;2018/05/20
							</span>
						</div>
						<div class="complaint">
							<span class="estimate">
								预计家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
							<span class="actual">
								实际家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
						</div>
						<button class="preservation">保存</button>
					</div>
					<div class="rate">
						<div class="security">
							<i></i>
							<h5>利润指标达成率</h5>
							<span>
								时间&nbsp;&nbsp;2018/05/20
							</span>
						</div>
						<div class="complaint">
							<span class="estimate">
								预计家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
							<span class="actual">
								实际家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
						</div>
						<button class="preservation">保存</button>
					</div>
					<div class="rate">
						<div class="security">
							<i></i>
							<h5>管理指标达成率</h5>
							<span>
								时间&nbsp;&nbsp;2018/05/20
							</span>
						</div>
						<div class="complaint">
							<span class="estimate">
								预计家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
							<span class="actual">
								实际家长投诉率
								<input type="text" placeholder="10%"/>
							</span>
						</div>
						<button class="preservation">保存</button>
					</div>
				</div>
			</div>
		
		</div>
	</div>	
</template>

<script>
export default {
  	name: 'taskmanagement',
  	data () {
    	return {
    		checkList: ['复选框 A'],
    		radio:'',
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
}
</script>

<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.taskmanagement{
  		width: 1200px;
  		margin: 0 auto;
  		position: relative;
  		.taskmanagementContent{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.percentage{
  				width:912px;
  				margin-top:1px;
  				.rate{
  					width: 100%;
					height: 162px;
					position: relative;
					border-bottom: 1px solid #dcdcdc;
					.security{
						width: 100%;
						height: 40px;
						text-align: left;
						line-height: 40px;
						i{
							display: inline-block;
							width: 2px;
							height: 18px;
							font-style: normal;
							background: #9BC248;
							margin-left: 15px;
							padding-top: 2px;
						}
						h5{
							display: inline-block;
							font-size: 18px;
							color: #222;
							font-weight: normal;
							margin-left: 10px;
						}
						span{
							float: right;
							margin-right: 15px;
							input{
								width: 107px;
								height: 20px;
								border: 1px solid #dcdcdc;
								border-radius: 4px;
								outline:none;
								text-indent: 10px;
							}
						}
					}
					.complaint{
						width: 100%;
						text-align: left;
						.estimate{
							display: inline-block;
							margin-left: 15px;
							font-size: 16px;
							color: #666;
							input{
								display: inline-block;
								width: 80px;
								height: 20px;
								font-size: 16px;
								color: #333;
								text-align: center;
								border: 1px solid #dcdcdc;
								border-radius: 5px;
								margin-left: 5px;
							}
						}
						.actual{
							display: inline-block;
							width: 212px;
							margin-left: 180px;
							input{
								display: inline-block;
								width: 80px;
								height: 20px;
								font-size: 16px;
								color: #333;
								text-align: center;
								border: 1px solid #dcdcdc;
								border-radius: 5px;
								margin-left: 5px;
							}
						}						
					}
					.preservation{
						width: 100px;
						height: 38px;
						background: #9bc248;
						border-radius: 4px;
						font-size: 18px;
						color: #fff;
						border: none;
						position: absolute;
						bottom: 20px;
						right: 15px;
					}
  				}
  			}
  		}
  	}
</style>
<style>
	.taskmanagement .el-button--text{
		color: #9BC248;
		font-size: 18px;
	}
	.taskmanagement .el-date-editor--daterange{
		height: 32px;
		margin-top: 10px;
	}
	.taskmanagement .el-input{
		width: 180px;
		height: 32px;
	}
	.taskmanagement .el-input__inner{
		height: 32px;
	}
	.taskmanagement .el-button{
		padding: 5px 10px;
		height: 32px;
	}
	.taskmanagement .departureStyle{
		margin-left: 45px;
	}
	.taskmanagement .el-checkbox-group{
		margin-left: 15px !important;
	}
	.taskmanagement .el-radio__input.is-checked+.el-radio__label{
		color: #9BC248;
	}
	.taskmanagement .el-radio__input.is-checked .el-radio__inner{
		border-color:#9bc248;
		background: #9bc248;
	}
	.taskmanagement .el-radio__inner:hover {
     border-color: #9BC248; 
	}
</style>