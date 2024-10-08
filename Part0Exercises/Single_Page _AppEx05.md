```mermaid
sequenceDiagram
participant browser
participant server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
activate server
server-->>browser: HTML document (spa)
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server-->>browser: the css file
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
activate server
server-->>browser: the JavaScript file (spa.js)
deactivate server

Note right of browser: The browser starts executing the JavaScript code to render the SPA

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server-->>browser: [{"content": "SPA is cool", "date": "2024-1-1" }, ... ]
deactivate server

Note right of browser: The browser dynamically renders the notes using JavaScript without reloading the page 