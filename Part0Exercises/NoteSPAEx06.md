```mermaid
sequenceDiagram
participant browser
participant server

Note right of browser: User writes a note and clicks "Save"

browser->>broswer: JavaScript captures the new note data

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
activate server
Note left of server: Server processes the new note and updates the data
server-->>browser: 201 Created (JSON response with updated note data)
deactivate server

Note right of browser: JavaScript updates the UI dynamically with the new note without reloading the page

browser->>browser: The note is added to the list and rendered immediately