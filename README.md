<!DOCTYPE html>

<html lang="en">
	<head>
		<meta charset="utf-8">
			<meta http-equiv="X-UA-Compatible" content="IE=edge">
				<meta name="viewport" content="width=device-width, initial-scale=1.0">
					<title>Simple website</title>
					<title>A wme!</title>
					<style>
						body {
						text-align: center;
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
						#Con {
						text-align: center;
						color: purple;
						front color: purple;
						font-family: Helvetica;
						}
						p {
						font-size: 24px;
						color: black;
						}
					</style>
					<img src="https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/weiter%20(1).png" alt="logo" width="300" height="120">
						<p>
							<b>Hi, My name is ... and i like ... and ...</b>
						</p>
						<form>
							<div class="formBox">
								<label for="Bezeichner">Art</label>
								<input type="text" id="Bezeichner" placeholder="Art">									
								</div>
							<div>
								<input type="number" placeholder="INT Spannung">
								</div>
							<div>
								<label>Ampere</label>
								<input type="number" id="A" placeholder="Ampere">
								</div>
							<div class="formBox">
								<label for="yr">Year</label>
								<input type="number" id="yr" placeholder="Year" />
							</div>
							<div>
								<button type="submit" id="btnSave" onclick="save()">SAVE</button>
								<input type="submit" id="btn" value="Send" />
								<input type="text" onfocus="save()">
							</div>
							<div id="msg">
							</div>
						</head>

	
	<body onload="save()">
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
				console.warn('added', { Arts });
				let pre = document.querySelector('#msg pre');
				pre.textContent = '\n' + JSON.stringify(Arts, '\t', 2);
				localStorage.setItem('GetSolution', JSON.stringify(Arts));
				}
				document.addEventListener('DOMContentLoaded', () => {
				document.getElementById('btn').addEventListener('click', addArt);
				});
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
