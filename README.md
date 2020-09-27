# 1. Setup

Se debe de definir los valores de las variables *w* y *h* para definir el tamaño de la ventana de pixi
```javascript 
    var fCanvas = false;
    var w = 760;
    var h = 478;
	if (!PIXI.utils.isWebGLSupported()) {
        console.log('Not Support')
        fCanvas = true;
    } else {
        console.log('Supported')
    }
	
	function init() {
        //Create a Pixi Application
        app = new Application({
            antialias: true,
            transparent: false,
            resolution: 1,
            forceCanvas: fCanvas,
            view: document.getElementById("game-canvas")
        });
        app.renderer.resize(w, h);
        loader.load(setup);
    }
);
```

Agregamos la linea `` para cambiar el color de fondo, si desplegamos la aplicación deberiamos ver un cuadro azúl

![Stage](https://raw.githubusercontent.com/luisemonsalve/tutorial-pixijs/tree/1-Setup/readme_src/1.png)