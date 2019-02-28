<template>
	<div class="Moving">
		<div class="moving">
			<div class="sharingTitle">
				<h3>经营</h3>
			</div>
			<div class="moving_content">
				<div class="header">
					<h3>通知公告</h3>
				</div>
				<div class="content">
					<div class="title"><span>标题 :</span><input type="text" v-model="Info.inform_title"></div>
					<div class="content1">
						<span>内容 :</span>
						<textarea v-model="Info.inform_desc"></textarea>
					</div>
					<div class="choose">
						<span>图片:</span>
						<div class="Uploadcontainer" v-for="(Infos,index) in Info.inform_photo" :key="index">
							<el-upload
				  				:action="Info.inform_photo"
							    list-type="picture-card"
							    :on-preview="handlePictureCardPreview"
							    :on-remove="handleRemove" style="margin-left: 45px;margin-right: 15px;">
						  		<i class="el-icon-plus"></i>
							</el-upload>
							<el-dialog :visible.sync="dialogVisible">
							  <img width="100%" :src="dialogImageUrl" alt="">
							</el-dialog>
						</div>
					</div>
					<!--<div class="btn"><button>提交</button></div>-->
					<div class="choose1">
						<span>通知选择 :</span>
						<select name="" class="choose2">
							<option value="1" v-for="(Infos,index) in Info.inform_type" :key="index">全部</option>
						</select>
					</div>
					<div class="btn" @click="getNotice"><button>提交</button></div>
				</div>
			</div>
		</div>
	</div>
</div>
</template>

<script>
import axios from 'axios';
import Cookies from 'js-cookie'
	export default{
		name:"Moving",
		data() {
	      return {
	        dialogImageUrl: '',
			dialogVisible: false,
			// 标题
			Info : {
				admin_id:'',
				inform_title:'',
				inform_desc:'',
				inform_status:'',
				inform_photo:'123',
				inform_type:''
			}
	      };
		},
		created() {
			this.getNotice ()
		},
	    methods: {
			// 调用接口	
		 async getNotice () {
			  var cookieId=Cookies.get("cookieId");
			  const {data:res} = await axios.post("/api/index.php/Api/student/student_add",{
				  admin_id:this.Info.admin_id,
				  inform_title:this.Info.inform_title,
				  inform_desc:this.Info.inform_desc,
				  inform_status:this.Info.inform_status,
				  inform_photo:this.Info.inform_photo,
				  inform_type:this.Info.inform_type,
				  admin_id:cookieId
			  })
			  console.log(res);
			  

		  },
	      handleRemove(file, fileList) {
	        console.log(file, fileList);
	      },
	      handlePictureCardPreview(file) {
	        this.dialogImageUrl = file.url;
	        this.dialogVisible = true;
	      }
	    }
	}
</script>

<style scoped>
	*{
		margin:0;
		padding:0;
	}
	.Moving{
		width: 1200px;
		margin: 0 auto;
		position: relative;
		background: #f2f5f5;
		
	}

	.moving{
		height:1200px;
		width:914px;
		position: absolute;
		top: 0;
		left: 285px;
		/*margin:0 auto;*/
		/*background: #cccccc;*/
		
	}
	.moving_content{
		border:1px solid #CCCCCC;
		border-radius: 10px;
		margin-top:22px;
		height: 926px;
		/*background: red;*/
	}
	.header{
		width:914px;
		height:68px;
	}
	.header h3{
		line-height: 68px;
		font-size:30px;
		color:#353535;
		font-family: "MicrosoftYaHeiLight";
		padding-left:30px;
		text-align: left;
	}
	.content{
		width:914px;
		height:852px;
		border-top:1px solid #CCCCCC;
		background: #F2F2F2;
		font-size:26px;
		color:#353535;
		font-family: "MicrosoftYaHeiLight";
	}
	.content .title{
		height:31px;
		margin-left:85px;
		margin-top:26px;
		text-align: left;
	}
	.title span{
		text-align: left;
		float: left;
		/*margin-top:0*/
	}
	.title input{
		width:277px;
		height:31px;
		border:1px solid #CCCCCC;
		border-radius: 6px;
		margin-left:38px;
		background: #ffffff;
	}
	.content textarea{
		width:622px;
		height:179px;
		border:1px solid #CCCCCC;
		border-radius: 6px;
		margin-left:38px;
		background: #ffffff;
		border-radius: 6px;
		/*margin-top:34px;*/
	}
	.content .content1{
		/*height:179px;*/
		margin-left:85px;
		margin-top:50px;
		text-align: left;
	}
	.content1 span{
		float: left;
		/*margin-top:-50px;*/
	}
	.choose{
		height:150px;
		margin-left:85px;
		margin-top:34px;
		/*background: red;*/
		display: flex;
		/*background: red;*/
	}
	.choose span{
		float: left;
	}
	.choose .el-upload{
		margin-left:0;
	}
	 .el-upload--picture-card{
		margin: 0 10px !important;
	}
	.Uploadcontainer{
		width:220px;
		height: 148px;
		overflow: hidden;
		margin-left:20px;
  	}
	.choose1{
		height:42px;
		margin-left:30px;
		margin-top:34px;
		/*background: red;*/
	}
	.choose1 .choose2{
		width:280px;
		height:34px;
		border-radius: 6px;
		padding-left:10px;
		margin-top:0px;
		margin-left:400px;
	}
	.choose1 span{
		float:left;
		font-size:26px;
		color:#353535;
		line-height:42px;
		font-family: "MicrosoftYaHeiLight";
	}
	.btn{
		width:160px;
		height:44px;
		margin:0 auto;
	}
	.btn button{
		width:160px;
		height:44px;
		background:#157efb ;
		color:#ffffff;
		text-align: center;
		border-radius: 6px;
		border:0;
		margin-top:140px;
	}
</style>