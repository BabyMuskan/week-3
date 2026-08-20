# 🛠️ Week 3 Troubleshooting Log & Error Report

*Developer:* Muskan  
*Project:* Week 3 Mega Project - Authentication & Database Integration  
*Track:* Web Design & Development  

---

## 📌 Issue Log 1: PowerShell Script Execution Restricted

* *Error Message:* SecurityError: (:) [], PSSecurityException - UnauthorizedAccess
* *Phase:* Initial Setup (npm init -y)
* *Root Cause:* Windows PowerShell restriction prevented npm scripts from executing in VS Code terminal.
* *Resolution / Solution:* 
  - Executed Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass in PowerShell to grant process-level execution rights.
  - Alternatively switched to Command Prompt (cmd) inside VS Code terminal to run initial commands smoothly.

---

## 📌 Issue Log 2: Template Literal Syntax Error

* *Error Message:* SyntaxError: missing ) after argument list at server.js
* *Phase:* Node.js Server Setup (node server.js)
* *Root Cause:* Standard quotes ('') were used instead of template literals / backticks ( \` ) while attempting to concatenate string variables like ${PORT}.
* *Resolution / Solution:* 
  - Corrected syntax to use standard string concatenation console.log("Server running on port " + PORT); or template literal backticks console.log(\`Server running on port ${PORT}\);`.
  - Saved file and re-ran node server.js, confirming the server initialized on port 5000.

---

## 📌 Issue Log 3: Environment Key Exposure Prevention (CORS / Security)

* *Error / Risk:* Exposing secret credentials & MongoDB connection string to public repository.
* *Phase:* Configuration Phase (.env & .gitignore)
* *Root Cause:* Direct hardcoding of secrets inside server.js poses security vulnerability on GitHub.
* *Resolution / Solution:* 
  - Extracted database credentials and secret JWT keys into a separate .env file.
  - Ensured .env and node_modules were strictly listed in .gitignore before making initial GitHub commits.

---

## 📌 Issue Log 4: Cross-Origin Resource Sharing (CORS) Handling

* *Error / Issue:* Potential blocked requests between frontend UI and backend API routes.
* *Phase:* API Integration & Express Middleware
* *Root Cause:* Browsers block API requests across different origins unless CORS middleware is enabled.
* *Resolution / Solution:* 
  - Installed cors package via npm install cors.
  - Added app.use(cors()); middleware in server.js before initializing API routes.
  ## 📌 Issue Log 6: Database Connection Configuration

* *Error Message:* Database connection error: querySrv ENOTFOUND
* *Phase:* Backend Initialization
* *Root Cause:* Missing/Incorrect MongoDB connection string in .env environment configuration.
* *Resolution / Solution:* Created a MongoDB Atlas Cluster, obtained the SRV connection string, and updated MONGO_URI in .env with correct credentials. Verified connection, resulting in 'MongoDB Connected Successfully!' log.
## 📌 Issue Log 6: Database Connection Configuration

* *Error Message:* Database connection error: querySrv ENOTFOUND
* *Resolution:* Connected to MongoDB Atlas Cloud Database successfully.
* *Screenshot:*
![MongoDB Connected](screenshot/server_connected.png)
