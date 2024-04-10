<html lang="en">
<meta charset="utf-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
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
    div {
        max-width: 600px;
        height: 40px;
        justify-content: center;
        align-items: center;
        margin-bottom: 30px;
    }
</style>
<head>
    <div>
        <p class="border-block"> <img class="logo"
                src="https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/weiter%20(1).png"
                width="300" height="150" />
        </p>
    </div>
    <h1>
        <b>JSON</b>
    </h1>
</head>
<body>
    <form>
        <div>
            <label for="Bezeichner">
                <input type="text" id="Bezeichner" placeholder="Art" class="formBox" />
                <label for="Spann">
                    <input type="number" id="U" placeholder="U" class="formBox" />                    
        </div>
        <div>
            <label for="Amp">
                <input type="number" id="A" placeholder="A" class="formBox" />
            <label for="yr">
                <input type="text" id="au" placeholder="Au" class="formBox" />               
            </div>
            <div>
        <label for="Anst">
            <input type="text" id="an" placeholder="An" class="formBox" />
            <label for="pos">
                <input type="number" id="ps" placeholder="P" class="formBox" />
            </div>
    </form>
    <div></div>
    <div>
</body>
<script>
    window.addEventListener('scroll', () => {
        const scrolable = document.documentElement.scrollHeight - window.innerHeight;
        const scrolled = window.scrollY;
        console.log(scrolled);
    })
    let Arts = [];
    const addArt = (ev) => {
        ev.preventDefault();
        let art = {
            B: document.getElementById('Bezeichner').value,
            U: document.getElementById('U').value,
            A: document.getElementById('A').value,
            An: document.getElementById('au').value,
            Au: document.getElementById('an').value,
            Y: document.getElementById('ps').value
        }
        Arts.push(art);
        document.forms[0].reset();
        save();
        console.warn('added', { Arts });
        let pre = document.querySelector('#msg pre');
        pre.textContent = '\n' + JSON.stringify(Arts, '\t', 6);
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
