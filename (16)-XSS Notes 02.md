
#### 1. Stored XSS
- **Description**: The attacker injects malicious scripts into a web application, and these scripts are stored on the server (e.g., in a database). When users access the affected pages, the scripts execute.
- **Example**:
  - **Payload**: 
    ```html
    <script>alert('Stored XSS!')</script>
    ```
  - **Usage**: Often found in comment sections, user profiles, or forums where user input is stored and displayed.

#### 2. Reflected XSS
- **Description**: The attacker injects a script through a URL that reflects the input back to the user. The script executes immediately without being stored on the server.
- **Example**:
  - **Payload**:
    ```html
    <img src="invalid.jpg" onerror="alert('Reflected XSS Triggered!')">
    ```
  - **Usage**: The attacker crafts a URL that includes the payload, and when the victim clicks the link, the script executes.

#### 3. DOM-Based XSS
- **Description**: The vulnerability exists in the client-side code (JavaScript) rather than server-side code. The attacker modifies the DOM environment of the browser.
- **Example**:
  - **Payload**:
    ```html
    <script>alert('DOM-Based XSS!')</script>
    ```
  - **Usage**: This can occur when user input is directly manipulated by JavaScript without proper sanitization.

### Relation of Provided Payloads to XSS Types

1. **Image Error Trigger**
   - **Payload**: 
     ```html
     <img src="invalid.jpg" onerror="alert('XSS Triggered!')">
     ```
   - **Type**: **Reflected XSS** (if injected via URL) or **DOM-Based XSS** (if part of a dynamic web page).
   - **Context**: Used in scenarios where input is not properly sanitized and event handlers are present in HTML.

2. **Direct Script Injection**
   - **Payload**: 
     ```html
     <script>alert(23234)</script>
     ```
   - **Type**: **Stored XSS** (if stored on the server) or **Reflected XSS** (if immediately reflected back from a request).
   - **Context**: Typically used in forms or comment sections where user input is rendered back to the page.

### Summary
- **Stored XSS**: Malicious scripts stored on the server.
- **Reflected XSS**: Malicious scripts reflected back immediately through a URL.
- **DOM-Based XSS**: Malicious scripts executed via manipulation of the DOM in the browser.
