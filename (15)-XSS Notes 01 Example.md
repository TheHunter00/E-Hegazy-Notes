![1710831657362](https://github.com/user-attachments/assets/da05cb39-464f-4cda-877d-a9b549e78773)
---
#### Step 1: Identify the Target
1. **Choose a Web Application**: Select a web application where you have permission to test. This could be a demo site or a personal project.
2. **Locate Input Fields**: Navigate the site to find areas where users can enter data, such as:
   - Comment sections
   - Search boxes
   - Feedback forms
   - User profile fields

#### Step 2: Prepare Your Test Payload
1. **Select a Simple XSS Payload**:
   - Start with the following basic payload:
     ```html
     <script>alert('XSS Test')</script>
     ```
   - This code will create an alert box if executed.

#### Step 3: Enter the Payload
1. **Input the Payload**:
   - Go to the identified input field.
   - Paste or type the payload (`<script>alert('XSS Test')</script>`).
2. **Submit the Input**:
   - Click the button to submit the input (e.g., "Post", "Submit", or "Search").

#### Step 4: Observe the Response
1. **Look for Alerts**:
   - If an alert box appears with the message "XSS Test", it means the site is vulnerable to XSS.
2. **Take Note of Any Changes**:
   - If no alert appears, move to the next step to gather more information.

#### Step 5: View Page Source
1. **Open Page Source**:
   - Right-click on the webpage and select "View Page Source".
2. **Search for Your Input**:
   - Use Ctrl + F to find the term "XSS Test".
   - **If Found**: If you see the input as `<script>alert('XSS Test')</script>`, the site is vulnerable.
   - **If Encoded**: If you see it as `&lt;script&gt;alert('XSS Test')&lt;/script&gt;`, the site is escaping the input, which is a sign of protection.

#### Step 6: Test Additional Payloads
1. **Try Other XSS Payloads**:
   - To further assess the vulnerability, use the following additional payloads:
   - **Image Error Trigger**:
     ```html
     <img src=x onerror=alert('XSS Triggered!')>
     ```
   - **Event Handler**:
     ```html
     <a href="#" onclick="alert('XSS Clicked!')">Click me</a>
     ```
   - **Input Field Focus**:
     ```html
     <input type="text" value="x" onfocus="alert('Focus XSS')">
     ```

#### Step 7: Document Your Findings
1. **Record Results**:
   - Note which payloads triggered alerts and how the application responded.
2. **Take Screenshots**:
   - Capture screenshots of alerts and page sources to document your findings.

#### Step 8: Ethical Considerations
1. **Get Permission**:
   - Ensure you have explicit permission to test the application. Unauthorized testing can lead to legal consequences.
2. **Responsible Disclosure**:
   - If you find vulnerabilities, consider reporting them responsibly to the site owner or through a bug bounty program.

