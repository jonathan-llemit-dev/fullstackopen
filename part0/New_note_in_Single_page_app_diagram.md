sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: JSON {"message":"note created"}
    deactivate server

    Note right of browser: The browser executes first the notes.push(note) to add the note on the local array of notes. Second, the browser cleared the input field (e.target.elements[0].value = ""). Then re-render the list redrawNotes(). Then finally submit the notes to server  sendToServer(note).