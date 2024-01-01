```mermaid
sequenceDiagram
    participant browser
    participant server
    
    note left of browser: new note and click save
    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note
    note over server: server adds new note
    server-->>browser: HTML status code 302
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    server-->>browser: HTML-code
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    server-->>browser: main.css
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    server-->>browser: main.js
    note over browser: browser runs js-code that gets JSON data from server
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    server-->>browser: JSON file content: [{content: "jou", date: "2024-01-01T16:57:39.941Z"}, ...]
    Note right of browser: Browser renders the newer json contents to display