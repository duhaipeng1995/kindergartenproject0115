<template>
	<div class="studyFile">
		<div class="studyfile">
			<div class="sharingTitle">
					<h3>学生档案</h3>
			</div>
			<div class="sharingcontent">
				<div class="sharingcontentTitle">
					<h3>目标生源</h3>
					<div class="sharingLink">
						<span>目标生源</span>
						<span>添加生源</span>
					</div>					
				</div>
				<div class="distribution">
					<ul class="park">
						<h3>所属园区:</h3>
						<li class="style">全部</li>
						<li v-for="(item,index) in gardenList" :key="index" @click="ClassList(item.id)">{{item.name}}</li>
						<!--<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>
						<li>第一幼儿园</li>-->
					</ul>
					<ul class="park">
						<h3>所属班级:</h3>
						<li class="style">全部</li>
						<li v-for="(items,index) in classList" :key="index">{{items.name}}</li>
						<!--<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>
						<li>小一班</li>-->
					</ul>
					<div class="sharingTime">
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
				<div class="Studyfiletable">
					<table class="sharingTable">
						<tr>
							<th><input type="radio" /></th>
							<th>学生姓名</th>
							<th>性别</th>
							<th>幼儿年龄</th>
							<th>家长姓名</th>
							<th>家长联系方式</th>
							<th>入园经历</th>
							<th>入园意向</th>
							<th>信息来源</th>
							<th>跟进痕迹</th>
						</tr>
						<tr v-for="(item,index) in StudyfileData" :key="index">
							<td><input type="radio" /></td>
							<td>{{item.name}}</td>
							<td>{{item.sex == 1 ? '男' : '女'}}</td>
							<td>{{item.birthday}}</td>
							<td>{{item.family_name}}</td>
							<td>{{item.addtime}}</td>
							<td>{{item.status == 1 ? '有' : '无'}}</td>
							<td>{{['强烈','正常','放弃'][item.idea]}}</td>
							<td>{{item.s_name}}</td>
							<td>
								<el-row>
								  	<el-button size="mini" round @click="centerDialogVisible = true">填写</el-button>
								  	<el-button size="mini" round @click="FllowRecordDialogVisible = true">查看</el-button>
								  	<el-button size="mini" round>删除</el-button>
								</el-row>
							</td>
						</tr>
					</table>
				</div>
				<FllowMark :centerDialogVisible.sync="centerDialogVisible"></FllowMark>
				<FllowRecord :FllowRecordDialogVisible.sync="FllowRecordDialogVisible"></FllowRecord>
			</div>			
		</div>
	</div>
</template>

<script>
	import FllowMark from '@/components/studentfiles/FllowMark'
	import FllowRecord from '@/components/studentfiles/FllowRecord'
	import axios from 'axios';
	import Cookies from 'js-cookie'
	export default{
		name:"studyfile",
		components:{
			FllowMark,
			FllowRecord
		},
		data() {
	      	return {
	      		input21:'',
	      		centerDialogVisible: false,
	      		FllowRecordDialogVisible: false,
	      		StudyfileData:[],
	      		activeList:[],
		      	gardenList:[],
		      	classList:[],
	      	}
	   },
	   methods:{
	   	targetAddsource(){
	   		var cookieId=Cookies.get("cookieId");
	   		axios.post("/api/index.php/api/student/student_source",{
				admin_id:cookieId
	   		}).then(({data})=>{
				this.StudyfileData=data.data;
				this.StudyfileData.map((current,index) => {
    				switch(current.status){
    					case '0':current.status='强烈'
    					  break
    					case '1':current.status='正常'
    					  break
    					case '2':current.status='放弃'
    					  break
    				}
    			})
	   			console.log(data.data);
	   		})
	   	},
	   	ActiveList(){
    		var cookieId=Cookies.get("cookieId");
    		axios.post("/api/index.php/api/base/getJT",{
//  			garden_id:id,
    			admin_id:cookieId
    		}).then(({data})=>{
    			this.activeList=data.data.class;
    			this.gardenList=data.data.garden;
    			console.log(data);
    			// console.log(data.data.class);
    		})
    	},
    	ClassList(id){
    		var cookieId=Cookies.get("cookieId");
    		axios.post("/api/index.php/api/base/getclass",{
    			garden_id:id,
    			admin_id:cookieId
    		}).then(({data})=>{
    			this.classList=data.data;
//  			console.log(data.data);
    		})
//  			
  
    	}
	   },
	   created(){
	   	this.ActiveList();
	   	this.targetAddsource();
	   }
	}
</script>


<style scoped lang="scss">
  	 /*引入 基础 样式*/
  	@import '../../assets/sass/base.scss';
  	.studyFile{
  		width: 1200px;
  		margin: 0 auto;
  		position: relative;
  		.studyfile{
  			width:912px;
  			position:absolute;
  			top:0;
  			left:285px;
  			.Studyfiletable{
  				width: 100%;
  				margin-top: 20px;
  				table{
  					width:885px;
  					margin: 0 auto 15px;
  				}
  			}
  		}
  	}
</style>
<style>
	.studyFile .el-button--text{
		color: #9BC248;
		font-size: 18px;
	}
	.studyFile .el-date-editor--daterange{
		height: 32px;
		margin-top: 10px;
	}
	.studyFile .el-input{
		width: 180px;
		height: 32px;
	}
	.studyFile .el-input__inner{
		height: 32px;
	}
	.studyFile .el-button{
		padding: 5px 10px;
		height: 32px;
	}
	.studyFile .departureStyle{
		margin-left: 45px;
	}
</style>