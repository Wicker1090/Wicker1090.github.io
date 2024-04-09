

<html lang="en">

<head>
	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Simple website</title>
	<title>A wme!</title>
	<style>
		body {			
			background: url("https://cdn.pixabay.com/photo/2018/02/02/17/24/background-3125893_1280.jpg");
			color: white;
			font-family: Helvetica;
			background-size: cover;
			background-position: center center;
			background-repeat: no-repeat;
			background-attachment: fixed;
		}
		p {
			font-size: 24px;
			color: black;
		}
		input {
			border: 0;
			padding: 12px;
			font-size: 18px;
		}
		input[type="submit"] {
			background: limegreen;
			color: black;
		}
		.formBoxL{			
			width: 160px*(scrolled/10);    		
			max-width: 80%;
			left: 10px;
		}
		.formBoxK{			
			width: 1200px;    		
			max-width: 100%;
			left: 10px;
		}
		.squares {
			display: flex;
			
			position:absolute;
			right: 300px;
		}
		.icon1,
		.icon2 {
			width: 500px;
			height: 240px;			
		}
		.icon1 {			
			display: flex;
			flex-wrap: wrap;
			position: relative;
			justify-content: center;		
		}
		.icon2 {			
			border-style: ridge;
			display: flex;
			flex-wrap: wrap;
			align-items: left;
			justify-content: center;
   }
		#box {
    width: 200px;
    height: 200px;
	max-width: 100%;
	position: center;     
 }
#box div{    
    height: 100%;    
    border-radius: 50%;
	aspect-ratio: 1;
	position:absolute;
    background-color: rgb(145, 27, 27);
    
 }
		#Con {
			text-align: center;
			color: purple;
			font-family: Helvetica;
		}
		p {
			font-size: 24px;
			color: black;
		}
	</style>
	<img src="https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/weiter%20(1).png" alt="logo"
		width="300" height="120">
	<p>
		<b>Hi, My name is ... and i like ... and ...</b>
	</p>
	<form>
		<div class="squares">
			<div class="icon1">
				<div class="formBoxL">					
					<label for="Bezeichner">
						<input type="text" id="Bezeichner" placeholder="Art">
				</div>
				<div class="formBoxK">
					<div>
					<label for="Spann">
						<input type="number" placeholder="INT Spannung">
						</div>
				</div>
				<div class="formBoxL">
					<div>
					<label for="Amp">
						<input type="number" id="A" placeholder="Ampere">
						</div>
				</div>
			</div>
			
			<div class="icon2">
				<div class="formBoxK">
					<div>
					<label for="yr">
						<input type="number" id="yr" placeholder="Year" />
						</div>
				</div>
				<div class="formBoxL">
					<div>
					<label for="Anst">
						<input type="text" id="an" placeholder="Anst" />
						</div>
				</div>
				<div class="formBoxK">
					<div>
					<label for="pos">
						<input type="number" id="ps" placeholder="Pos" />
						</div>
				</div>
			</div>
		</div>
		<div>
			<input type="submit" id="btn" value="Send" />
		</div>
		<div id="msg">
		</div>
	</form>
</head>


<body>
	<script>
        window.addEventListener('scroll',()=>{
            const scrolable = document.documentElement.scrollHeight -window.innerHeight;
            const scrolled=window.scrollY;
            console.log(scrolled);
        })
    </script>
	<section id="Con">
		<script>
			let Arts = [];
			const addArt = (ev) => {
				ev.preventDefault();
				let art = {
					bezeichner: document.getElementById('Bezeichner').value,
					year: document.getElementById('yr').value
				}
				Arts.push(art);
				document.forms[0].reset();
				save();
				document.forms[0].reset();
				console.warn('added', { Arts });
				let pre = document.querySelector('#msg pre');
				pre.textContent = '\n' + JSON.stringify(Arts, '\t', 2);
				localStorage.setItem('GetSolution', JSON.stringify(Arts));
			}
			document.addEventListener('DOMContentLoaded', () => {
				document.getElementById('btn').addEventListener('click', addArt);
			});
		</script>
		<script>
			function save() {
				var c = document.createElement("a");
				c.download = "SOSO.txt";
				var t = new Blob([JSON.stringify(Arts)], {
					type: "text/plain"
				});
				c.href = window.URL.createObjectURL(t);
				c.click();
			}
		</script>
	</section>
</body>

</html>
