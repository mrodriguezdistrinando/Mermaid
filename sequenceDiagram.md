::: mermaid

sequenceDiagram
    participant navegador
    participant servidor

    navegador->>servidor: POST https://studies.cs.helsinki.fi/exampleapp/notes
    activate servidor
    servidor-->>navegador: HTML document
    deactivate servidor

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate servidor
    servidor-->>navegador: the css file
    deactivate servidor

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate servidor
    servidor-->>navegador: the JavaScript file
    deactivate servidor

    Note right of navegador: El navegador comienza a ejecutar el código JavaScript que recupera el JSON del servidor.

    navegador->>servidor: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate servidor
    servidor-->>navegador: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate servidor

    Note right of navegador: El navegador ejecuta la funcion de callback que muestra las notas

:::