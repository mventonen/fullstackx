```mermaid
sequenceDiagram
    participant browser
    participant server

    note left of browser: user creates a new note
    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    note over server: server processes the new note
    server-->>browser: Status Code: 201 (Created)

    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: JSON file content: [{content: "jou", date: "2024-01-01T17:41:07.564Z"}, ...]
    
    note left of browser: browser displays the updated notes list
