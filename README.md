
<html lang="en">
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            background: url("https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/Ball2400.png");
            color: white;
            font-family: Helvetica;
            background-size: cover;
            background-position: center center;
            background-repeat: no-repeat;
            background-attachment: fixed;
        }
        p{
            border-color:red;
            border-block-color: yellow;
        }
        h1{
            border-color:red;
            border-block-color: blue;
        }
        div {
            border-color:red;
            max-width: 1440px;
            height: 145px;            
            align-items: center;
            margin-bottom: 90px;
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
                src="https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/LOGO300p.png"
                width="140" height="140">
        </p>       
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
            <input type="submit" id="btn" value="Send" >      
    <div id="msg">
    </div>
    </form>
<script>
    let Dat=new Date();
    let hour=Dat.getHours();
    let minute=Dat.getMinutes();
    let secunde=Dat.getSeconds();
    let d = "SOSO"+hour+"/"+minute+"/"+secunde;
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
            n: document.getElementById('au').value,
            u: document.getElementById('an').value,
            P: document.getElementById('ps').value
        }
        Arts.push(art);
        document.forms[1].reset();
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
        let text = d.toString();
        document.getElementById("msg");
        var c = document.createElement("a");
        c.download = d;
        var t =  new File([JSON.stringify(Arts)], "Draft1.txt", {type: "text/plain", lastModified: d})
        //new Blob([JSON.stringify(Arts)], {
        //    type: "text/plain"
       // });
        c.href = window.URL.createObjectURL(t);
        c.click();
    }
</script>

