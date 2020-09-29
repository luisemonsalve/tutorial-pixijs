# 6. Formas y textos


## Crear un Texto
Para crear un [Text](https://pixijs.download/dev/docs/PIXI.Text.html) solo basta una linea, si se desea agregar estilos se debe usar la clase de pixi llamada [TextStyle](https://pixijs.download/dev/docs/PIXI.TextStyle.html)
```javascript 
const titleStyle = new TextStyle({
        fontFamily: "Press Start 2P",
        fontSize: 26,
        fill: "white",
        stroke: '#000000',
        strokeThickness: 3,
    });

let title = new Text("Juego pausado", titleStyle);
```
## Crear un Forma
Hay varios graficos nativos de Pixi que pueden ser útiles en muchos casos
- **Rectangulo**
```javascript 
let rectangle = new Graphics();
rectangle.lineStyle(4, 0xFF3300, 1);
rectangle.beginFill(0x66CCFF);
rectangle.drawRect(0, 0, 64, 64);
rectangle.endFill();
app.stage.addChild(rectangle);
```

- **Circulo**
```javascript 
let circle = new Graphics();
rectangle.beginFill(0x66CCFF);
circle.drawCircle(0, 0, 32);
circle.endFill();
```

- **Elipse**
```javascript 
let ellipse = new Graphics();
ellipse.beginFill(0xFFFF00);
ellipse.drawEllipse(0, 0, 50, 20);
ellipse.endFill();
app.stage.addChild(ellipse);
```

- **Lineas**
```javascript 
let line = new Graphics();
line.lineStyle(4, 0xFFFFFF, 1);
line.moveTo(0, 0);
line.lineTo(80, 50);
app.stage.addChild(line);
```