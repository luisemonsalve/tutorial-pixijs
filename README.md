# 3. AnimatedSprites

Los [AnimatedSprites](https://pixijs.download/dev/docs/PIXI.AnimatedSprite.html "AnimatedSprites") son una forma sencilla de mostrar una animación representada por una lista de texturas.

## Crear un AnimatedSprite
Hay dos formas muy utilizadas para crear un AnimatedSprite 
- A partir de imagenes cargadas

```javascript 
    let bgImages = ["src/bg/bg0.jpg", "src/bg/bg1.jpg", "src/bg/bg2.jpg", "src/bg/bg3.jpg", "src/bg/bg4.jpg",
            "src/bg/bg5.jpg", "src/bg/bg6.jpg", "src/bg/bg7.jpg"
        ];
    let textureArray = [];

    for (let i = 0; i < bgImages.length; i++) {
        let texture = resources[bgImages[i]].texture;
        textureArray.push(texture);
    };

    var bg = new AnimatedSprite(textureArray);
```
> Este método es útil cuando las imagenes de la animación son pesadas o grandes.

- A partir de un atlas
```javascript 
    sheet_liu = resources["src/atlas-liukang.json"].spritesheet;
    var liukang_s = new AnimatedSprite(sheet_liu.animations['liu_stance']);
```
> Se cargan las imágenes desde que se abre el documento

## Propiedades 
- **Velocidad de animación**<br>
Para controlar la velocidad con la que se anima el sprite se usa la propiedad **sprite.animationSpeed**.

- **Controlar animación**<br>
Para reproducir la animación se usa **sprite.play()**, y para pararla **sprite.stop()**.

- **Repeticiones** <br>
Por defecto la animación tiene el loop activo, si queremos que se reproduca una sola vez podemos usar la propiedad loop de la siguiente forma **sprite.loop = false**. Si se pause despues de cada reproducción se puede usar la función onLoop de la siguiente forma:

```javascript 
    sprite.onLoop = function () {
        sprite.stop();
    };
```

## Referentes:
- [AnimatedSprites](https://pixijs.download/dev/docs/PIXI.AnimatedSprite.html "AnimatedSprites")