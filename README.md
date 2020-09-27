# 4. Movimiento y velocidad

A continuación se describen los comandos y funciones para agregar movimiento a los sprites

## Agregar movimiento a un Sprite
Para agregar movimiento a un sprite se debe usar la propiedad **vx** o **vy**, y en la función gameloop se debe actualizar el estado de la posición según esta propiedad.

```javascript 
function play(delta) {    
     scorpio.x += scorpio.vx
     scorpio.y += scorpio.vy
}
```

## Eventos de teclado
Para el uso de eventos de teclado usaremos una función que se definió desde el inicio, donde definimos que tecla y que se ejecuta cuando se presiona o se libera.
```javascript 
    let right = keyboard("ArrowRight"),
        left = keyboard("ArrowLeft"),
        space = keyboard(" "),
        x = keyboard("x");

    right.press = () => {
        isWalking = true;
        scorpio.vx = 2;
    };
    right.release = () => {
        isWalking = false;
        scorpio.vx = 0;
    };
```

## Referentes:
- [AnimatedSprites](https://pixijs.download/dev/docs/PIXI.AnimatedSprite.html "AnimatedSprites")