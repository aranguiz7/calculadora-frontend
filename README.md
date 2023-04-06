1. Equipo: Potrero

Integrantes:
- Cristian Dúran https://github.com/cristiandf06
- Ignacio Aránguiz  https://github.com/aranguiz7
- Iván Becerra  https://github.com/IvanBecerraA


2. Descripción Proyecto Calculadora

Cración de calculadora con operaciones matemáticas básicas.


3. Tecnologías

HTML, CSS, Bootstrap y JavaSript.


4. Funcionalidad del código JavaSript

a través de los atributos de ID se obtienen los elementos del DOM para manipular en JavaSript

    const display = document.querySelector("#display");
    const buttons = document.querySelectorAll("button");


El código JavaScript utiliza un bucle forEach para iterar sobre cada elemento en la lista buttons y asigna un evento onclick a cada uno.

    buttons.forEach((item) => {
    item.onclick = () => {
        
    };
    });


El código JavaScript se ejecuta con la función onclick documentado anteriormente.

La primera condición if verifica si el botón que se ha hecho click tiene un id de "limpiar". Si es así, el contenido del elemento display se establece en una cadena vacía.

    if (item.id == "limpiar") {
        display.innerText = "";
        }

La segunda condición else if verifica si el botón que se ha hecho click tiene un id de "borrar". Si es así, se convierte el contenido del elemento display a una cadena de texto (toString()), se elimina el último carácter (substr(0, string.length - 1)), y se actualiza el contenido del elemento display para mostrar la cadena resultante.

    else if (item.id == "borrar") {
      let string = display.innerText.toString();
      display.innerText = string.substr(0, string.length - 1);
    }

La tercera condición else if verifica si el botón que se ha hecho click tiene un id de "igual" y si hay contenido en el elemento display. Si es así, se evalúa el contenido del elemento display utilizando la función eval() y se actualiza el contenido del elemento display para mostrar el resultado.

    else if (display.innerText != "" && item.id == "igual") {
      display.innerText = eval(display.innerText);
    }

La cuarta condición else if verifica si el botón que se ha hecho click tiene un id de "igual" y si no hay contenido en el elemento display. Si es así, se actualiza el contenido del elemento display para mostrar un mensaje de error temporal "Error capa 8!" durante un segundo.

    else if (display.innerText == "" && item.id == "igual") {
      display.innerText = "Error capa 8!";
      setTimeout(() => (display.innerText = ""), 1000);
    }

Por último, si ninguna de las condiciones anteriores se cumple, se agrega el id del botón al contenido del elemento display.

    else {
      display.innerText += item.id;
    }


