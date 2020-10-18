<template>
	<div class="login-content">
		<form>
			<h2 class="mb-3">My<span>Company</span></h2>
			<div class="form-group">
				<label for="email">Email</label>
				<input type="email" class="form-control" v-model="email"> 
			</div>
			<div class="form-group">
				<label>Password</label>
				<div class="input-group">
					<input class="form-control" :type="visibility" v-model="password">
					<div class="input-group-addon" v-if="visibility == 'password'" @click="showPassword">
						<i class="fa fa-eye-slash" aria-hidden="true"></i>
					</div>
					<div class="input-group-addon" v-if="visibility == 'text'" @click="hidePassword">
						<i class="fa fa-eye" aria-hidden="true"></i>
					</div>
				</div>
			</div>
			<small>By sigining up for my course prep. you agree to our <a href="#">Terms of use</a> and <a href="#">Privacy Policy.</a></small>
			<div class="d-block">
				<button type="submit" class="btn btn-success btn-block mt-3" :disabled="isDisabled">Sign Up</button>
			</div>
			<div class="separator-item"><span>or</span></div>
			<p class="text-center font-weight-600">Sign up with</p>
			<div class="social-login-buttons-block">
				<a href="#">
				<img src="assets/images/google.png">
				</a>
				<a href="#">
				<img src="assets/images/fb.png">
				</a> 
				
			</div>
			<p class="text-center mt-3">Already have an account?<a href="#" class="text-success font-weight-bold">Login</a></p>
		</form>
	</div>
</template>

<style scope>
	:disabled {
	    cursor: not-allowed! important;
	}
	.font-weight-600 {
		font-weight: 600;
	}
	
	.login-content{
		display: flex;
		justify-content: flex-start;
		align-items: center;
		padding: 5rem 0px 0px 0px;
	}
	.login-content form{
		width: 360px;
		margin: 0 auto;
		display: block;
	}
	.login-content h2{
		text-align: center;
		font-weight: 400;
	}
	.login-content h2 span{
		color: #1b9b86;
	}
	.input-group-addon i{
		cursor: pointer;
	}
	.btn-success{
		background-color: #1b9b86 !important;
		border-color: #1b9b86!important;
		font-weight: 500;
		cursor: pointer;
	}
	.separator-item {
	    width: 100%;
	    display: block;
	    text-align: center;
	    position: relative;
	    width: 100%;
	    margin: 36px 0 22px 0;
	    height: 1px;
	}
	.separator-item:before {
	    width: 100%;
	    content: "";
	    height: 1px;
	    display: block;
	    background-color: #e0e0e0;
	    position: absolute;
	    top: 0;
	}
	.separator-item span {
	    background-color: #fff;
	    position: absolute;
	    top: -16px;
	    margin-left: -17px;
	    padding: 4px;
	    color: #808080;
	    border: 1px solid #e0e0e0;
	    width: 32px;
	    height: 32px;
	    border-radius: 30px;
	    line-height: 22px;
	    text-transform: uppercase;
	    font-size: 12px;
	    font-weight: 700;
	}
	.social-login-buttons-block {
	    width: 50%;
	    margin: 0 auto;
	    text-align: center;
	}

	.social-login-buttons-block a:last-child {
	    margin-right: 0;
	}
	.social-login-buttons-block a {
	    color: #fff!important;
	    margin-right: 20px;
	}
	.social-login-buttons-block a img{
		width: 25%;
	}
</style>

<script type="text/javascript">
	module.exports = { 
		data() {
			return {
				email: "",
				password: "",
				visibility: "password"
			}
		},

		methods: {
			showPassword() {
				this.visibility = "text";
			},
			hidePassword() {
				this.visibility = "password"
			}
		},

		computed: {
            isDisabled() {
                if(this.email == "" || this.password == "")
                {
                    return true;
                } else {
                    return false;
                }
                
            }
        }
	};
</script>