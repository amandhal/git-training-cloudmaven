## Section A — Practical Tasks 
PRACTICAL 01 - Git Installation, Configuration & First Repository
- 1a. Install Git on your Ubuntu VM and verify the installation by running git --version. Screenshot the terminal output.
- 1b. Configure your global Git identity: set user.name and user.email.
- 1c. Create a directory called git-nginx-assessment, initialise a Git repository inside it.
<img width="1157" height="785" alt="test-1" src="https://github.com/user-attachments/assets/f8c26258-2d91-4001-8aea-1f98ed7614ed" />

- 1d. Create two files: README.md (with a project title and your name) and app.py (with a print('Hello Git') statement).
<img width="1142" height="595" alt="image" src="https://github.com/user-attachments/assets/a20fb477-3dd2-4883-bf21-d36bcd0b463d" />

- 1e. Stage both files and make your first commit with the message: 'Initial commit: add README and app.py'.
- 1f. Run git log and screenshot the output showing the commit hash, author, date, and message.
<img width="1402" height="404" alt="image" src="https://github.com/user-attachments/assets/900bf7a0-30e7-4bde-b151-ab0d2fe842e9" />

PRACTICAL 02 - Branching, Committing & Pull Request Workflow
- 2a. From the main/master branch, create a new branch named feature/add-calculator following Git naming best practices.
- 2b. Switch to the new branch and add a file calculator.py with at least two Python functions (e.g., add, subtract).
- 2c. Stage and commit this file with a clear, imperative commit message.
- 2d. Make a second commit on this branch: update README.md to mention the new calculator module.
<img width="1919" height="663" alt="image" src="https://github.com/user-attachments/assets/4845bc7e-ca9f-4c74-85be-6b43aed69896" />

- 2e. Push the feature branch to GitHub and open a Pull Request (PR) against main.
<img width="1642" height="527" alt="image" src="https://github.com/user-attachments/assets/4b9a593d-82e6-4d9b-a4e5-26de29bd4fce" />
<img width="1323" height="505" alt="image" src="https://github.com/user-attachments/assets/08fa9d32-ef49-4776-b2f3-0f02660d5378" />

- 2f. Screenshot the PR page on GitHub showing the branch comparison, commit list, and file diff
<img width="1490" height="776" alt="image" src="https://github.com/user-attachments/assets/4505a1f7-dc7d-4ad7-a7fa-9c966241bb56" />
<img width="1918" height="393" alt="image" src="https://github.com/user-attachments/assets/4c45a326-5060-4dd9-bef4-88612979e7b1" />

- 2g. Merge the PR on GitHub, then pull the updated main branch locally.
<img width="1540" height="692" alt="image" src="https://github.com/user-attachments/assets/0e039eb6-5c09-4c05-a819-251afe05f250" />

PRACTICAL 03 - Stash, Undo & History (Revert, Reset, Amend)
- 3a. On a new branch called bugfix/stash-demo, modify app.py (add a comment or a line). Without committing, run git stash. Verify app.py is clean using git status. Pop the stash and confirm the changes return.
<img width="1601" height="972" alt="image" src="https://github.com/user-attachments/assets/ba7bf0cb-7a88-4f8c-8e62-09ae32664fef" />

- 3b. Create and commit a file named bug.txt with content 'This is a bug'. Then use git revert to undo this commit. Screenshot git log --oneline showing both the original commit and the revert commit.
<img width="1329" height="527" alt="image" src="https://github.com/user-attachments/assets/05a05994-36dc-436b-9367-ecf753540c33" />

- 3c. Create a file hotfix.txt, stage it, then commit it. Use git commit --amend -m 'fix: hotfix with corrected message' to update the commit message. Show git log --oneline before and after.
<img width="1336" height="742" alt="image" src="https://github.com/user-attachments/assets/6812aa33-130b-4c8a-aa0d-4790bdf1ba2c" />

- 3d. Make two more commits. Use git reset --soft HEAD~1 to un-commit the last change while keeping it staged. Screenshot git status showing the staged file.
<img width="1112" height="872" alt="image" src="https://github.com/user-attachments/assets/25c2c6c3-4d0c-439c-882d-2791ba211473" />

PRACTICAL 04 - NGINX Install, Config & Hosting Multiple Static Sites
- 4a. Install NGINX on Ubuntu and verify it is running with systemctl status nginx. Enable it to start on boot.
<img width="1298" height="1029" alt="image" src="https://github.com/user-attachments/assets/31989142-26d2-4552-9d59-0fc42a538ff1" />

- 4b. Run sudo nginx -t to confirm the default config is valid. Screenshot the output.
<img width="679" height="99" alt="image" src="https://github.com/user-attachments/assets/4a128d39-69e5-40af-b050-f70245527a9d" />

- 4c. Create two separate site directories: /var/www/app1.local/html and /var/www/app2.local/html. Add a unique index.html to each (e.g., 'Welcome to App 1' and 'Welcome to App 2').
<img width="1097" height="239" alt="image" src="https://github.com/user-attachments/assets/dd1b42ab-1baf-453a-a015-fd9b0feb842e" />

- 4d. Create NGINX server block config files for app1.local and app2.local in /etc/nginx/sites-available/. Each block must set listen 80, server_name, root, and a location / block with try_files.
- 4e. Enable both sites using symlinks to sites-enabled. Test the config and reload NGINX.
<img width="1460" height="838" alt="image" src="https://github.com/user-attachments/assets/cfa8f456-9464-4395-a0cf-3cc72a9140b5" />

- 4f. Add both domains to /etc/hosts pointing to 127.0.0.1. Run curl http://app1.local and curl http://app2.local and screenshot both responses.
<img width="872" height="269" alt="image" src="https://github.com/user-attachments/assets/2da1c4c3-3d64-44a4-bd20-e0f835901c4f" />

PRACTICAL 05 - Reverse Proxy with Docker Backend
- 5a. Pull and run an nginx:alpine Docker container as a backend app on port 8080: docker run -d -p 8080:80 --name backend-app nginx:alpine. Verify it responds with curl http://localhost:8080
<img width="1673" height="792" alt="image" src="https://github.com/user-attachments/assets/2df8d630-5ec8-4e56-8910-50dff56b23ac" />

- 5b. Create a new NGINX site config at /etc/nginx/sites-available/myapp.local that proxies all requests to http://127.0.0.1:8080 using proxy_pass.
- 5c. Include all four required proxy headers: Host, X-Real-IP, X-Forwarded-For, X-Forwarded-Proto.
- 5d. Enable the site, test the config, reload NGINX. Add myapp.local to /etc/hosts.
<img width="1461" height="604" alt="image" src="https://github.com/user-attachments/assets/3b28c7a1-3b8e-4cfc-a39f-2f26385bd1cc" />

- 5e. Run curl http://myapp.local and screenshot the response proving NGINX is proxying to the Docker backend.
<img width="1704" height="1048" alt="image" src="https://github.com/user-attachments/assets/37f6c5db-3e6b-4cc3-8b79-206fbc39c3df" />

- 5f. Explain in your README what each proxy_set_header directive does and why it matters.

PRACTICAL 06 - SSL/TLS, Load Balancing & Merge Conflict Resolution
- 6a. [SSL Concept — Local Self-Signed Cert] Generate a self-signed SSL certificate using openssl: openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/myapp.key -out /etc/ssl/certs/myapp.crt. Update the myapp.local NGINX config to listen on port 443 with ssl_certificate and ssl_certificate_key directives. Test with curl -k https://myapp.local.
<img width="1919" height="961" alt="image" src="https://github.com/user-attachments/assets/6e15afe2-ffee-4d5f-81f0-597bb27f0f19" />

- 6b. [Load Balancer Config] Create a new NGINX config file that defines an upstream block with two backend entries (they can both point to 127.0.0.1:8080 for this exercise). Configure NGINX to proxy_pass to this upstream group. Reload and verify.
<img width="1726" height="998" alt="image" src="https://github.com/user-attachments/assets/90d08670-43e1-489b-87c6-8770d3f6b2ea" />

