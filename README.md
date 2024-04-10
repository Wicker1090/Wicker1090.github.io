<html lang="en">


    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.5">

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
            max-width: 1200;            
            justify-content: center;
            align-items: center;
        }
        #div{
            min-height: auto;
        }
        .border-block {
            writing-mode: Horizontal-tb;
        }
        .logo {
            width: 280px;
            height: 120px;
            display: flex;
            justify-content: center;
            align-items: center;

        }
        h1,
        h2 {
            display: flex;
            justify-content: center;
            text-align: center;
            color: blueviolet;
        }
        main {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }
        input {
            border: 0;
            padding: 5px;
            font-size: 18px;
            border: 5%
        }
        input[type="submit"] {
            background: limegreen;
            color: black;
        }
        img{
        display:block;}
        div {
            flex-basis: 40%;
            height: 50px;
            margin-bottom: 0.5rem;
        }

        @media (min-width: 200px) {
            main {
                flex-wrap: nowrap;
            }

            div {
                flex-basis: 20%;
            }
        }
    </style>
    <head>
    <div id="#div">
    </div>
    <div>
        <p class="border-block"> <img class="logo"
                src="https://raw.githubusercontent.com/Wicker1090/Wicker1090.github.io/main/Images/weiter%20(1).png" />
        </p>
    </div>
    <div>
    </div>
    <div>
        <h1>
            <b>JSON</b>
        </h1>
    </div>
    <div>
    </div>
</head>
<body>
    <form class="exampleText">
        <main>
            <div></div>
            <div>
                <label for="Bezeichner">
                    <input type="text" id="Bezeichner" placeholder="Art">
                    <label for="Spann">
                        <input type="number" id="U" placeholder="U">
                        <label for="Amp">
                            <input type="number" id="A" placeholder="A">
            </div>
            <div>
                <label for="yr">
                    <input type="text" id="au" placeholder="Au" />
                    <label for="Anst">
                        <input type="text" id="an" placeholder="An" />
                        <label for="pos">
                            <input type="number" id="ps" placeholder="P" />
            </div>
            <div></div>
        </main>
    </form>
    <div></div>
    <div>
        <form class="exampleText"> <input type="submit" id="btn" value="Send" /> </form>
    </div>
    </div>
    <div id="msg">
    </div>
</body>
<script>
    window.addEventListener('scroll', () => {
        const scrolable = document.documentElement.scrollHeight - window.innerHeight;
        const scrolled = window.scrollY;
        console.log(scrolled);
    })
</script>
<section>
    <script>
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
