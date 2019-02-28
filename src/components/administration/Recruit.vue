<template>
	<div class="recruit">
		<div class="recruitContent">
			<div class="sharingTitle">
				<h3>人事管理</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>招聘统计</h3>	
				</div>
				<div class="recruitTable">
					<table class="sharingTable">
						<tr>
							<th>面试人</th>
							<th>面试时间</th>
							<th>面试职位</th>
							<th>面试官</th>
							<th>面试结果</th>
							<th>备注</th>
						</tr>
						<tr class="sharingTablecolor_one">
							<td><input type="text" value=""></td>
							<td><input type="text" value=""></td>
							<td><input type="text" value=""></td>
							<td><input type="text" value=""></td>
							<td>
								<select name="">
									<option value="successful">面试成功</option>
									<option value="failure">面试失败</option>
								</select>
							</td>
							<td><button @click="RecruitMarkDialogVisible =true">详情</button></td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td>&nbsp;</td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<select name="">
									<option value="successful">面试成功</option>
									<option value="failure">面试失败</option>
								</select>
							</td>
							<td><button>详情</button></td>
						</tr>
						<tr class="sharingTablecolor_one">
							<td>&nbsp;</td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<select name="">
									<option value="successful">面试成功</option>
									<option value="failure">面试失败</option>
								</select>
							</td>
							<td><button>详情</button></td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td>&nbsp;</td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<select name="">
									<option value="successful">面试成功</option>
									<option value="failure">面试失败</option>
								</select>
							</td>
							<td><button>详情</button></td>
						</tr>
						<tr class="sharingTablecolor_one">
							<td>&nbsp;</td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<select name="">
									<option value="successful">面试成功</option>
									<option value="failure">面试失败</option>
								</select>
							</td>
							<td><button>详情</button></td>
						</tr>
						<tr class="sharingTablecolor_two">
							<td>&nbsp;</td>
							<td></td>
							<td></td>
							<td></td>
							<td>
								<select name="">
									<option value="successful">面试成功</option>
									<option value="failure">面试失败</option>
								</select>
							</td>
							<td><button>详情</button></td>
						</tr>
					</table>
					<div class="AddSubmission"><button>保存</button></div>
				</div>
				<RecruitMark :RecruitMarkDialogVisible.sync="RecruitMarkDialogVisible"></RecruitMark>
			</div>
		</div>
	</div>
</template>

<script>
import RecruitMark	from '@/components/studentfiles/RecruitMark'
import axios from 'axios';
import Cookies from 'js-cookie'
export default {
  	name: 'recruitmark',
  	components:{
  		RecruitMark
  	},
  	data(){
  		return{
  			RecruitMarkDialogVisible:false,
  			recruit:{
  				recruitName:'',
  				recruitDate:'',
  				recruitPosition:'',
  				recruitInterview:'',
  				InterviewResult:'',
  				
  			}
  		}
  	},
  	methods:{
  		AddRecruit(){
  			var cookieId=Cookies.get("cookieId");
  			axios.post("/api/index.php/Api/Personnel/recruit",{
  				
  				admin_id:cookieId	
  			}).then(({data})=>{
  				console.log(data);
  			})
  		}
  	},
  	created(){
  		this.AddRecruit();
  	}
}
</script>

<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.recruit{
  		width:1200px;
  		margin: 0 auto;
  		position:relative;
  		.recruitContent{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.recruitTable{
  				width: 100%;
  				table{
  					width:912px;
  					td{
						width: 100px;
						height:40px;
						padding: 2px;
						input{
							width:100%;
							height:100%;
							border: 0;
						}
					}
  					select{
  						border:none;
  						outline: none;
  						font-size: 16px;
  						color: #333;	
  					}
  				}
  			}
  		}
  	}
	
</style>
<style>
	.AddSubmission{
		width: 100%;
		text-align: center;
	}
	.AddSubmission button{
		width: 148px;
		height: 35px;
		background: #9BC248;
		line-height:35px;
		text-align: center;
		border-color: #9BC248;
		color: #fff;
		font-size: 16px;
		margin: 15px 0;
		border: 0;
		border-radius: 5px;
	}
</style>