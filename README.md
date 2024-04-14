
<html lang="en">

<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background: url("https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/Background.png");
            color: white;
            font-family: Helvetica;
            background-size: cover;
            background-position: center center;
            background-repeat: no-repeat;
            background-attachment: fixed;
        }        
        div {
            max-width: 600px;
            height: 80px;
            justify-content: center;
            align-items: center;
            margin-bottom: 90px;
            border-block-color: yellow;

        }
        .Logo{
            border-block-color: yellow;
            background-color: red;
            justify-content: center;
            display: block;
            margin-left: auto;
            margin-right: auto;
            width: 50%;
        }
    </style>
    <div>
        <p class="Logo"> <img            
                src="https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/LOGO.png"
                width="300" height="140">
        </p>
    <h1>
        <b>JSON</b>
    </h1>
</head>
<body>
    <form>
        <div>
            <label for="Bezeichner">
                <input type="text" id="Bezeichner" placeholder="Art" class="formBox" >
                <label for="Spann">
                    <input type="number" id="U" placeholder="U" class="formBox" />
        <div>
            <label for="Amp">
                <input type="number" id="A" placeholder="A" class="formBox" >
                <label for="yr">
                    <input type="text" id="au" placeholder="Au" class="formBox" />
        <div>
            <label for="Anst">
                <input type="text" id="an" placeholder="An" class="formBox" >
                <label for="pos">
                    <input type="number" id="ps" placeholder="P" class="formBox" />    
    <div>
        <form ><input type="submit" id="btn" value="Send" />      
    <div id="msg">
    </div>    
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
        c.download = "SOSO";
        var d = new Date(2013, 12, 5, 16, 23, 45, 600);
        var t =  new File([JSON.stringify(Arts)], "Draft1.txt", {type: "text/plain", lastModified: d})
        //new Blob([JSON.stringify(Arts)], {
        //    type: "text/plain"
       // });
        c.href = window.URL.createObjectURL(t);
        c.click();
    }
</script>

