<template>
	<div class="addstaff">
		<div class="addstaffContent">
			<div class="sharingTitle">
				<h3>员工管理</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>添加员工</h3>
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
						<h3>所属班级:</h3>
						<li class="style">全部</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
					</ul>
				</div>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>员工管理</h3>
				</div>
				<div class="addstaffInformation">
					<div class="addstaffInformationTitle">
						<span>|</span>
						<h3>员工基本信息</h3>
					</div>
					<div class="addstaffInformationDetailed">
						<div>
							<span>姓名</span>
							<input type="" name="" id="" value="" placeholder="张三"/>
							<span>出生日期</span>
							<el-date-picker v-model="value1" type="date" placeholder="选择日期"></el-date-picker>
							<span>性别</span>
							<el-radio v-model="radio1" label="1">男</el-radio>
  							<el-radio v-model="radio1" label="2">女</el-radio>
						</div>
						<div>
							<span>联系方式</span>
							<input type="text" />
							<span>家庭住址</span>
							<input type="" name="" id="" value="" />
						</div>
						<div>
							<span>学历</span>
							<select name="">
								<option value="">大专</option>
								<option value="">本科</option>
								<option value="">研究生</option>
							</select>
							<span>学历类型</span>
							<el-radio v-model="radio2" label="1">单招</el-radio>
  							<el-radio v-model="radio2" label="2">统招</el-radio>
  							<span>教证</span>
							<el-radio v-model="radio3" label="1">有</el-radio>
  							<el-radio v-model="radio3" label="2">无</el-radio>
						</div>
					</div>
				</div>
				<div class="addstaffInformation">
					<div class="addstaffInformationTitle">
						<span>|</span>
						<h3>员工入职信息</h3>
					</div>
					<div class="addstaffInformationDetailed">
						<div>
							<span>入职日期</span>
							<el-date-picker v-model="value2" type="date" placeholder="选择日期"></el-date-picker>
							<span>所在园区</span>
							<select name="">
								<option value="">第一幼儿园</option>
								<option value="">第二幼儿园</option>
								<option value="">第三幼儿园</option>
							</select>
							<span>所在班级</span>
							<select name="">
								<option value="">一小班</option>
								<option value="">二小班</option>
								<option value="">三小班</option>
							</select>
						</div>
						<div>
							<span>任职岗位</span>
							<select name="">
								<option value="">主任</option>
								<option value="">见习园长</option>
								<option value="">分园长</option>
							</select>
							<span>薪酬类型</span>
							<select name="">
								<option value="">管理人员</option>
								<option value="">教职人员</option>
								<option value="">伙食人员</option>
							</select>
							<span>薪酬级别</span>
							<select name="">
								<option value="">管理人员</option>
								<option value="">教职人员</option>
								<option value="">伙食人员</option>
							</select>
						</div>
						<div>
							<span>薪酬标准</span>
							<select name="">
								<option value="">管理人员</option>
								<option value="">教职人员</option>
								<option value="">伙食人员</option>
							</select>
						</div>
					</div>
				</div>
				<div class="addstaffInformation">
					<div class="addstaffInformationTitle">
						<span>|</span>
						<h3>员工入职信息</h3>
					</div>
					<div class="addstaffInformationDetailed">
						<div>
							<span>转正日期</span>
							<el-date-picker v-model="value3" type="date" placeholder="选择日期"></el-date-picker>
							<span>转岗日期</span>
							<el-date-picker v-model="value4" type="date" placeholder="选择日期"></el-date-picker>
							<span>准证岗位</span>
							<select name="">
								<option value="">管理人员</option>
								<option value="">教职人员</option>
								<option value="">园长</option>
							</select>
						</div>
						<div>
							<span>离职日期</span>
							<el-date-picker v-model="value5" type="date" placeholder="选择日期"></el-date-picker>
						</div>
					</div>
				</div>
				<div class="addstaffSave">
					<button>保存</button>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
  	name: 'addstaff',
  	data() {
     	return {
     		radio1: '1',
     		radio2: '1',
     		radio3: '1',
        	pickerOptions1: {
          		disabledDate(time) {
            		return time.getTime() > Date.now();
          		},
          		shortcuts: [{
            		text: '今天',
            		onClick(picker) {
              			picker.$emit('pick', new Date());
            		}
          		}, {
            		text: '昨天',
            		onClick(picker) {
              			const date = new Date();
              			date.setTime(date.getTime() - 3600 * 1000 * 24);
              			picker.$emit('pick', date);
            		}
          		}, {
            		text: '一周前',
            		onClick(picker) {
              			const date = new Date();
              			date.setTime(date.getTime() - 3600 * 1000 * 24 * 7);
              			picker.$emit('pick', date);
            		}
          		}]
        	},
        	value1: '',
        	value2: '',
        	value3: '',
        	value4: '',
        	value5: '',
      	};
    }
}
</script>

<style scoped lang="scss">
	/*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.addstaff{
  		width:1200px;
  		margin: 0 auto;
  		position:relative;
  		.addstaffContent{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.addstaffInformation{
  				width: 100%;
  				.addstaffInformationTitle{
  					width:100%;
  					line-height:60px;
  					span{
  						display: inline-block;
  						margin-left: 15px;
  						font-size: 24px;
  						color: #9BC248;
  					}
  					h3{
  						display: inline-block;
  						color: #333;
  						font-size: 18px;
  						font-weight: normal;
  					}
  				}
  				.addstaffInformationDetailed{
  					margin-left: 30px;
  					div{
  						margin: 10px 0;
  					}
  					span{
  						margin-left: 30px;
  						margin-right: 5px;
  					}
  					input{
  						width: 170px;
  						height: 40px;
  						border: 1px solid #dcdcdc;
  						border-radius: 5px;
  						text-indent: 10px;
  					}
  					select{
  						width:170px;
  						height: 40px;
  						border: 1px solid #dcdcdc;
  						border-radius: 5px;
  					}
  				}
  			}
  			.addstaffSave{
  				width:100%;
  				text-align: center;
  				margin: 50px 0;
  				button{
  					width:286px;
  					height:50px;
  					background: #9BC248;
  					color: #fff;
  					font-size: 18px;
  					border-radius: 8px;
  					border: none;
  				}
  			}
  		}
  	}
</style>
<style>
	.addstaff .el-date-editor--date{
		width: 170px !important;
	}
</style>