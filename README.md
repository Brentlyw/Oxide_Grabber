# Oxide-Grabber
A working proof of concept for a Rust based credential "stealer" which exfiltrates to a Python HTTP server.

# Features
 - Manually traverses %LOCALAPPDATA% & %APPDATA% with max depth of 6 looking for chromium password SQLite databases.
 - Decrypts these saved logins and saves them to a temporary .csv, which is then sent off to the HTTP server & subsequently deleted.
 - Server keeps track and maintains a banned IP list.
 - API key is required to communicate with the server, or IP will be banned.
 - .CSV files are the only upload type allowed, or IP will be banned.
 - Server logs in console, but also has a *simplistic and clean WebUI* to browse logged credentials.

# Setup
 1.) Build the client by ```cargo build --release``` - it should be about 2MB. *(This size can be reduced by swapping chrono or reqwest with smaller libs, and packing)*  
 2.) Run the server.py script, which will run on 127.0.0.1:8000 *(Change this as needed, and in the main.rs)*  

# Disclaimer
 - This was not designed to be evasive, persistant, or undetected. This was made as a proof of concept, you can expand on it if you need other functionality.
 - The webUI is not nessesary, you can find all logs at ./oxide_logs/
