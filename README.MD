# Hrees

Hrees é uma pequena biblioteca de física 2D em JavaScript para simulações simples em canvas. Ela permite gerenciar objetos (retângulos e círculos) e partículas, aplicando gravidade, colisões, fricção e rotação.

---

## Funcionalidades

- Simulação de gravidade.
- Colisões com paredes e chão.
- Colisões simples entre retângulos.
- Sistema de partículas com vida útil, gravidade e movimento.
- Fricção e elasticidade personalizáveis.
- Suporte a objetos retangulares e circulares.
- Rotação de objetos.

---

## Instalação

Basta incluir o arquivo `Hrees.js` no seu projeto e criar uma instância da classe:

```html
<script src="Hrees.js"></script>
<script>
  const canvas = document.getElementById('SeuCanvaAqui');
  const ctx = canvas.getContext('2d');
  const hrees = new Hrees(0.98); // valor da gravidade opcional

  // Adicionar Objetos
  hrees.addObject({
    x: 100,
    y: 50,
    width: 60,
    height: 60,
    color: 'green',
    type: 'rect'
  });

  // Círculo
  hrees.adObject({
    x: 300,
    y: 50,
    radius: 30,
    color: 'blue',
    type: 'circle'
  });

  // Adicionar partículas
  hrees.addParticle({
    x: 200,
    y: 200,
    vx: 2,
    vy: -2,
    size: 5,
    color: 'yellow'
  })

  // Atualizar e renderizar

  function GameLoop() {
    ctx.clearRect(0,0, canvas.width, canvas.height);

    hrees.update();
    hrees.render(ctx);

    requestAnimationFrame(GameLoop);
}

GameLoop();


</script>
