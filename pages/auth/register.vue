<template>
   <div class="body-content">
      <div class="auth-container login">
         Use your username to login below
         <form action="" @submit.prevent="loginUser">
            <inputField
               id="username"
               label="Username"
               type="text"
               v-model="formData.username"
            />

            <inputField
               id="email"
               label="Email"
               type="email"
               v-model="formData.email"
            />

            <inputField
               id="firstname"
               label="Firstname"
               type="text"
               v-model="formData.firstname"
            />

            <inputField
               id="lastname"
               label="Lastname"
               type="text"
               v-model="formData.lastname"
            />

            <inputField
               id="website"
               label="Website"
               type="text"
               v-model="formData.website"
            />

            <inputField
               id="password"
               label="Password"
               type="password"
               v-model="formData.password"
            />

            <button class="btn btn-block btn-lg btn-primary">
               registrate account
            </button>

            <nuxt-link to="/auth/login">Login with an existing account</nuxt-link>
         </form>
      </div>
   </div>
</template>

<script>
import inputField from '@/components/inputField'

export default {
   name: 'Register',
   components: {
      inputField
   },
   data(){
      return {
         formData: {  },
      }
   },
}

   // OLD REGISTER
   // function registrateUser(){
	// var useremail = $('#useremail').val();
	// var userpassword = $('#userpass').val();
	// var userpassword2 = $('#userpass2').val();
	// var errors = [];
	// $("ul").empty();
	//
	// if(!isEmail(useremail)){
	// 	errors.push('please provide a valid email address');
	// }
	// if(userpassword == ''){
	// 	errors.push('please enter a password');
	// }else	if(userpassword.length < 7){
	// 	errors.push('Password needs to be at least 7 characters');
	// }
	// if(userpassword !== userpassword2){
	// 	errors.push('The two passwords are not the same');
	// }

	// if(errors.length == 0){
	// 	var url = "/custom/register_user.php";
	// 	var send_data = {
	// 		username: useremail,
	// 		useremail: useremail,
	// 		userpassword: userpassword
	// 	}
	
		// $.ajax({
		// 	type: "POST",
		// 	url: url,
		// 	data: send_data,
		// 	success: function(data){
		// 		var result = JSON.parse(data);
		// 		if(result.success){
		// 			localStorage.setItem('quiz_user', useremail);
		// 			localStorage.setItem('quiz_user_id', result.user_id);
		// 			showQuizResults();
		// 			nextStep(11);
		// 		}else{
		// 			$('ul.error-list').append('<li>${result.message}</li>');
		// 		}
		// 	},
		// 	error: function(err){
		// 		console.log('Connection error: ${err}');
		// 	}
		// });
	// }else{
	// 	for(var error of errors){
	// 		$('ul.error-list').append('<li>${error}</li>');
	// 	}
	// }
// }
</script>
