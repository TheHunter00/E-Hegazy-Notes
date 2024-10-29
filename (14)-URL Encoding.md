
#### Step 1: What is URL Encoding?

- **Purpose**: URL encoding changes special characters in a URL to make them safe to use.
- **Examples of Encoding**:
  - Space (` `) → `%20`
  - Ampersand (`&`) → `%26`
  - Plus (`+`) → `%2B`
  - Percent (`%`) → `%25`

#### Step 2: Setting Up Burp Suite

1. **Install Burp Suite**: Download and install it on your computer.

2. **Set Up Your Browser**:
   - Configure your browser to use Burp’s proxy (usually `127.0.0.1:8080`).

#### Step 3: Capture a Request

1. **Open Burp Suite** and go to the **Proxy** tab.

2. **Perform an Action**: Do something in your browser, like searching or logging in. This will send a request that Burp can capture.

3. **View the Captured Request**:
   - In the Proxy tab, you will see the request you made. Look for the URL and any parameters.

#### Step 4: Send to Repeater

1. **Right-click** on the request you captured.

2. **Choose "Send to Repeater"**. This lets you change and resend the request.

#### Step 5: Modify the Request

1. **Go to the Repeater tab**.

2. **Find the Parameters**: Look for the part you want to change. For example, `search=John Doe`.

3. **Apply URL Encoding**:
   - Change `search=John Doe` to `search=John%20Doe` (single encoding).
   - For double encoding, change it to `search=John%2520Doe`.

#### Step 6: Send the Modified Request

1. **Click “Send”** in the Repeater tab.

2. **Check the Response**: Look at the server's reply to see how it handled your encoded input.

#### Step 7: Analyze the Results

- See if the server responded differently. This can show you how the server processes the data you send.

### Example

Let’s say you want to search for "John Doe":

1. **Original Request**: 
   ```
   GET /search?name=John Doe HTTP/1.1
   ```

2. **Single URL Encoded Request**:
   ```
   GET /search?name=John%20Doe HTTP/1.1
   ```

3. **Double URL Encoded Request**:
   ```
   GET /search?name=John%2520Doe HTTP/1.1
   ```

### Summary

- **URL encoding** helps send data safely in URLs.
- **Burp Suite** lets you capture, change, and resend requests to test web applications.

