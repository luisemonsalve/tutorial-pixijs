# 2. Sprites

Los [Sprites](https://pixijs.download/dev/docs/PIXI.Sprite.html "Sprites") son la base para todos los objetos texturizados que se representan en la pantalla.

### Formas de crear un sprite
- Importar directamente la imagen

```javascript 
var scorpio = PIXI.Sprite.from('src/scorpio/stance_01.png');     
```
> En este método se cargan las imágenes cuando se crea el sprite

- Precargar imagen
```javascript 
PIXI.loader
  .add('scorpio','src/scorpio/stance_01.png')
  .load(setup);

function setup() {
  let sprite = new PIXI.Sprite(
    PIXI.loader.resources["scorpio"].texture
  );
}
```
> Se cargan las imágenes desde que se abre el documento

- Cargar imagen desde un atlas
```javascript 
PIXI.loader
  .add('src/atlas-scorpio.json')
  .load(setup);

function setup() {
    scorpioSheet = resources["atlas-scorpio.json"].spritesheet;
    let sprite = new Sprite(scorpioSheet.textures["stance_01.png"]);
}
```

### Mostrar un Sprite
- Cargar la imagen desde el inicio
```javascript 
    loader
       .add('scorpio','src/scorpio/stance_01.png')    
```
- Crear el sprite 
```javascript 
    var scorpio = new Sprite(resources["scorpio"].texture);  
```
- Agregar el sprite al Stage principal 
```javascript 
    gameScene.addChild(scorpio) 
```
> Si queremos eliminarlo podemos usar la función removeChild() de la misma forma que addChild()
### Propiedades 
- *Tamaño*
Para obtener el tamaño en pixeles del sprite se usa las propiedades **sprite.width** y **sprite.height**

- *Posición*
Los valores de posición se usan mediante coordenadas cartesianas (x, y), siendo la esquina superior izquiera el punto (0,0). Por defecto, agregar un sprite se ubica en la posición (0,0), si queremos cambiar su posición lo podemos hacer con las propiedades **x** y **y**, por ejemplo, para hubicarlo en el centro podemos hacerlo de la sigueinte forma:

```javascript 
    scorpio.x = (w / 2) - (scorpio.width / 2);
    scorpio.y = (h / 2) - (scorpio.height / 2);
```
> También es posible usar sprite.position.set(x, y)

Si retornamos la posición de un sprite nos da la ubicación del punto de la esquina superior derecha del mismo, esto se puede cambiar con la propiedad **pivot**

- *Escalado*
Para cambiar el tamaño de un sprite se puede usar **sprite.width** y **sprite.height** asignado valores fijos, o se puede hacer mas eficientemente usando la propiedad **sprite.scale.x** y **sprite.scale.y**.

Para reducir el tamaño a la mitad :
```javascript 
    scorpio.scale.x = 0.5;
    scorpio.scale.y = 0.5;
```
> También es posible usar scorpio.scale.set(x, y)

- *Rotación*
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



Referentes:
- [PIXI.Sprite](https://pixijs.download/dev/docs/PIXI.Sprite.html "PIXI.Sprite")