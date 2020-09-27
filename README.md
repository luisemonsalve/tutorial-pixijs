# 5. Colisiones

A continuación se describen los comandos y funciones para detectar colisiones entre dos sprites

La función que usaremos es *collision()*, descrita a continuación.

```javascript 
 function collision(x1, w1, x2, w2) {
        /* 
        x1 = posición de elemento 1
        x2 = posición de elemento 2
        w1 = width de elemento 1
        w2 = width de elemento 2
         */
        if ((x1 + w1) >= x2 - w2) {
            return true;
        } else {
            return false;
        }
    }

```

