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
    bg.animationSpeed = 0.13
    bg.play()
    gameScene.addChild(bg)    
```
> Este método es útil cuando las imagenes de la animación son pesadas o grandes.

- A partir de un atlas
```javascript 
    var liukang_s = new AnimatedSprite(sheet_liu.animations['liu_stance']);
    liukang_s.animationSpeed = 0.2;
    liukang_s.play();
    liukang_s.loop = true;
    gameScene.addChild(liukang_s)
```
> Se cargan las imágenes desde que se abre el documento

## Propiedades 
- **Tamaño**<br>
Para obtener el tamaño en pixeles del sprite se usa las propiedades **sprite.width** y **sprite.height**

- **Posición**<br>
Los valores de posición se usan mediante coordenadas cartesianas (x, y), siendo la esquina superior izquiera el punto (0,0). Por defecto, agregar un sprite se ubica en la posición (0,0), si queremos cambiar su posición lo podemos hacer con las propiedades **x** y **y**, por ejemplo, para hubicarlo en el centro podemos hacerlo de la sigueinte forma:

```javascript 
    scorpio.x = (w / 2) - (scorpio.width / 2);
    scorpio.y = (h / 2) - (scorpio.height / 2);
```
> También es posible usar sprite.position.set(x, y)

Si retornamos la posición de un sprite nos da la ubicación del punto de la esquina superior derecha del mismo, esto se puede cambiar con la propiedad **pivot**

- **Escalado** <br>
Para cambiar el tamaño de un sprite se puede usar **sprite.width** y **sprite.height** asignado valores fijos, o se puede hacer mas eficientemente usando la propiedad **sprite.scale.x** y **sprite.scale.y**.

Para reducir el tamaño a la mitad :
```javascript 
    scorpio.scale.x = 0.5;
    scorpio.scale.y = 0.5;
```
> También es posible usar scorpio.scale.set(x, y)

- **Rotación** <br>
La rotación se hace a traves de la propiedad **sprite.rotation**, se asigna un valor en radianes.
```javascript 
    scorpio.rotation  = 0.5;
```
Para cambiar el punto desde donde se rota se puede hacer de dos forma, usando la propiedad **anchor** o **pivot**. La diferencia es que con anchor podemos asigar un valor entre 0 y 1 que corresponde a un valor porcentual, y con pivot damos un valor en pixeles.

```javascript 
    scorpio.anchor.x = 0.5;
    scorpio.anchor.y = 0.5;

    scorpio.pivot.set(10, 10)
```



## Referentes:
- [AnimatedSprites](https://pixijs.download/dev/docs/PIXI.AnimatedSprite.html "AnimatedSprites")