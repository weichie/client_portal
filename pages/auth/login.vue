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
               id="password"
               label="Password"
               type="password"
               v-model="formData.password"
            />

            <button class="btn btn-block btn-lg btn-primary">
               login
            </button>

            <nuxt-link to="/auth/register">create an account</nuxt-link>
         </form>
      </div>
   </div>
</template>

<script>
import inputField from '@/components/inputField'

export default {
   name: 'Login',
   components: {
      inputField
   },
   data(){
      return {
         formData: {  },
      }
   },
   methods: {
      loginUser(){
         console.log('run Login Script');
      }
   }
}

// old jquery
// function customLogin(userlogin, userpass){
// 	$("ul.error-list").empty();
// 	var url = "/custom/login_user.php";
// 	var login_data = {
// 		user_login: userlogin,
// 		user_password: userpass,
// 	}
//
// 	$.ajax({
// 		type: "POST",
// 		url: url,
// 		data: login_data,
// 		success: function(data){
// 			var result = JSON.parse(data);
// 			if(result.ID){
// 				localStorage.setItem('loggedin_user', result.data.user_email);
// 				localStorage.setItem('quiz_user', result.data.user_email);
// 				$('.login-start').hide();
// 				$('#quiz-intro').hide();
// 				$('#step-1').fadeIn();
// 				$('#current-step').text(1);
// 				$('.steps strong').hide();
// 				$('.step-counter, .current-steps').fadeIn();
// 				$('.quiz-bg.bg-2').addClass('active');
// 				$('.quiz-bg.bg-1').removeClass('active');
// 			}else{
// 				$('ul.error-list').append('<li>Wrong username or password</li>');
// 			}
// 		},
// 		error: function(err){
// 			$('ul.error-list').append('<li>Wrong username or password</li>');
// 			console.log('Connection error: ${err}');
// 		}
// 	});
// }
</script>
