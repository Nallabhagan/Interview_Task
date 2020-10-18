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