<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>DCC138 Exemplo01</title>
</head>
<body>
  <h1>DCC138 Exemplo01</h1>
  <canvas></canvas>
  <p>por Laís Santos</p>
  
  <script>
    let canvas = document.querySelector("canvas");
    let ctx = canvas.getContext("2d");
    canvas.width = 480;
    canvas.height = 320;
    let x = 150;
    let y = 100;
    let t0;
    let dt;
    requestAnimationFrame(desenha);

    function desenha(t){
      t0 = t0 ?? t;
      dt = (t - t0)/1000;
      //Desenha Fundo
      ctx.fillStyle = "black";
      ctx.fillRect(0, 0, canvas.width, canvas.height);

      //Atualiza estados
      x = x + 100*Math.sin(t/500)*dt;
      y = 100 + 1500*Math.cos(t/200)*dt;

      //Desenha elementos
      ctx.fillStyle = "white";
      ctx.fillRect(x, y, 20, 20);   

      requestAnimationFrame(desenha);
      t0 = t;
    }
    
  </script>
</body>
</html>
