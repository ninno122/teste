<title>flor</title>

<canvas width="600" height="400"></canvas>

<script>
//    Programa desenhar flor na tela

//    Trazer o canvas lá do HTML para o JS
        var tela = document.querySelector('canvas');
        var pincel = tela.getContext ('2d');

//    preenchimento do fundo
        pincel.fillStyle = 'lightskyblue';
        pincel.fillRect(0, 0, 600, 400);

//  função criar círculo
    function desenharCirculo(x, y, raio, cor) {
        pincel.fillStyle = cor;
        pincel.beginPath();
        pincel.arc(x, y, raio, 0, 2 * 3.14);
        pincel.fill();
    }

//  função criar haste
    function desenharHaste(x, y, a, b, cor){
        pincel.fillStyle = cor;
        pincel.fillRect(x, y, a, b);
    }

//    função criar flor (x, y)
    function desenharFlor(x,y){
        desenharCirculo(x, y+20, 10, 'orchid');
        desenharCirculo(x, y, 10, 'khaki');
        desenharCirculo(x, y-20, 10, 'violet');
        desenharCirculo(x-20, y, 10, 'mediumorchid');
        desenharCirculo(x+20, y, 10, 'blueviolet');
        desenharHaste(x-1, y+30, 2, 120, 'seagreen');
    }

    desenharFlor(300, 200);

//    repetir flor (for)
    for(var x = 0; x <= 650; x = x + 70){

            desenharFlor(x-15, 260);
            desenharFlor(x+20, 310);
            desenharFlor(x-15, 355);
    }

</script>
