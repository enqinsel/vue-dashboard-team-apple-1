<script setup>
	const emits = defineEmits(["offPopup"])

	const closeHandler = () => {
		emits("offPopup")
	}
</script>


<template>
	<div class="container">
		<div class="header">
			<h1 class="name">Tolga Eğilmezel</h1>
			<button style="background: url(close.svg)" class="button" @click="closeHandler"></button>
		</div>
		<hr>
		<div class="content">
			<h1 style="text-align:center; padding: 5px;">Her Şeyi</h1>
			<div class="about">
				<img class="icon" src="../../../public/about.svg" alt="">
				<h3>Hakkında</h3>
				<p style="margin-left: 50px;"> 
					He is enthusiastic and self-motivated Front-End Developer & Designer with more than 10+ years experience in developing mid to large-scale websites and web-applications based on web standards.</p>
			</div>
			<div class="website">
				<img class="icon" src="../../../public/website.svg" alt="">
				<h3>Web Sitesi</h3>
				<a href="https://about.me/tolga" target="_blank">about.me/tolga</a>
			</div>
			<div class="socialMedia">
				<img class="icon" src="../../../public/socialmedia.svg" alt="">
				<h3>Sosyal Medya</h3>
				<ul>
					<li><a href="https://www.instagram.com/tolga_egilmezel/"  target="_blank"><img class="linkImg" src="../../../public/insta.svg" alt=""></a></li>
					<li><a href="https://twitter.com/Tolga_Egilmezel"  target="_blank"><img class="linkImg" src="../../../public/twitter.svg" alt=""></a></li>
					<li><a href="https://www.snapchat.com/add/tolga_egilmezel"  target="_blank"><img class="linkImg" src="../../../public/snapchat.svg" alt=""></a></li>
					<li><a href="https://open.spotify.com/user/tolga_egilmezel"  target="_blank"><img class="linkImg" src="../../../public/spotify.svg" alt=""></a></li>
					<li><a href="https://github.com/Tolga-Egilmezel"  target="_blank"><img class="linkImg" src="../../../public/github.svg" alt=""></a></li>
					<li><a href="https://www.linkedin.com/in/tolgaegilmezel/"  target="_blank"><img class="linkImg" src="../../../public/linkedin.svg" alt=""></a></li>
				</ul>
			</div>
			<div class="posta">
				<img class="icon" src="../../../public/email.svg" alt="">
				<h3>E-Posta</h3>
				<a href="">404 Not Found!</a>
			</div>
			<div class="birthDay">
				<img class="icon" src="../../../public/birthday.svg" alt="">
				<h3>Dünyaya Geldi</h3>
				<p>24 Eylül 1983</p>
			</div>
			<div style="text-align:center;" class="slogan">
				<i >"The man who can't catch his age"</i>
			</div>
		</div>
	</div>
</template>

<style scoped>

.icon{
	width: 30px;
	height: 30px;
	float: left;
	margin-right: 20px;
}

.linkImg{
	width: 30px;
	height: 30px;
}

ul{
	margin-left: 50px;
	padding: 5px;
}
.container {
	position: absolute;
	left: 50%;
	top: 50%;
	transform: translate(-50%, -50%);
	padding: 10px;
	width: 600px;
	height: 680px;
	background-color: rgb(255, 255, 255);
	box-shadow: 2px 2px 10px 2px #E84A4A;
	z-index: 100;
}


.header {
	position: relative;
	width: 580px;
	height: 80px;
	
}

.name{
	position: absolute;
	margin-top: 20px;
}
.button{
	position: absolute;
	width: 30px;
	height: 30px;
	margin-left: 550px;
}

.button:hover{
	cursor: pointer;
}

.content {
	position: absolute;
	width: 580px;
	height: auto;
	
	margin-top: 10px;
	
}

.about{
	position: relative;
	
	width: 570px;
	height: auto;
	margin: 5px;
}

.website{
	position: relative;
	
	width: 570px;
	height: auto;
	margin: 5px;
}

.socialMedia{
	position: relative;
	
	width: 570px;
	height: auto;
	margin: 5px;
}

.posta{
	position: relative;
	
	width: 570px;
	height: auto;
	margin: 5px;
}

.birthDay{
	position: relative;
	
	width: 570px;
	height: auto;
	margin: 5px;
}

.slogan{
	position: relative;
	
	width: 570px;
	height: auto;
	margin-top: 20px;
}
</style>