
<html lang="en">
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
<head>
</head>
    <style>
        body {
            background: url("https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/Background.png");
            color: white;
            font-family: Helvetica;
            background-size: cover;
            background-position: center center;
            background-repeat: no-repeat;
            background-attachment: fixed;
            border-bottom-style: dotted;
        }
        p{
            border-color:red;
            border-block-color: yellow;
            border-bottom-style: dotted;
        }
        h1{
             border-color:red;
            border-block-color: yellow;
            border-block-style:dotted;
            border-bottom-style: dotted;
        }
        div {
            border-color:red;
            max-width: 1440px;
            height: 145px;            
            align-items: center;
            margin-bottom: 90px;
            border-block-color: yellow;
            border-bottom-style: dotted;
        }
        .formBox{
            max-width: 140px;
            input{
                width:70%;
            }         
        }
        .Logo{
            margin-left: 10%;
            margin-right: 30%;                              
        }
        .doau{
            height: 10px;
            margin-top: 2%;       
            margin-left: 5%;
            margin-right: auto;
            width: 100%;
            height: 5%;
            margin-bottom: 20px;
            grid-auto-columns: auto;            
        }
        .dzau{
            display:flex;                       
            margin-bottom: 30px;
            margin-top: 2%;  
            height: 40px;
            input{
                width: 100px;
                height: 20px;
            }                  
        }
        .center{
            display: block;
            margin-left: 5%;
            margin-right: auto;            
        }       
        .small{            
            height: 50px;
            padding-top: 20px;
            input{
                width:190px;
            }
        }
    </style>
    <form class="dzau">
    <div class="dzau">           
        <input class="dazu" type="text" id="name" placeholder="Name" >       
        <input class="dazu" type="text" id="keyword" placeholder="Paswort" >
    </div>
</form>
    <div>
        <p class="Logo"> <img            
                src="https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/LOGO11.png"
                width="300" height="140">
        </p>
    <h1>
        <b>JSON</b>
    </h1>
<body>
    <form clas="small">
        <div class="doau">           
            <input class="formBox" type="text" id="Bezeichner" placeholder="Art"  >
            <input type="number" id="U" placeholder="U" class="formBox" ></div>
        <div class ="doau">
            <input type="number" id="A" placeholder="A" class="formBox" >
            <input type="text" id="au" placeholder="Au" class="formBox" ></div>       
        <div class ="doau">
            <input type="text" id="an" placeholder="An" class="formBox" >
            <input type="number" id="ps" placeholder="P" class="formBox" ></div>  
        <div class ="doau">
            <form ><input type="submit" id="btn" value="Send" >      
    <div id="msg">
    </div>
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

