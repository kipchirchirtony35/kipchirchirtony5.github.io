# Terminal Log

## Task 5.1 — Navigation
pwd
ls
cd ~\Documents
cd ..
cd ~

## Task 5.1 — Project Structure
New-Item -ItemType Directory -Path "my-project\src\css","my-project\src\js","my-project\src\images","my-project\docs","my-project\tests" -Force
New-Item -ItemType File -Path "my-project\README.md" -Force

## Task 5.2 — File Operations
New-Item -ItemType File -Path "src\index.html" -Force
Get-Content src\index.html
Copy-Item src\index.html src\backup.html
Move-Item src\backup.html docs\
Rename-Item src\index.html home.html
Remove-Item src\home.html

## Task 5.2 — Directories
Copy-Item -Recurse src\ src-backup\
Move-Item src-backup\ archive\
Remove-Item archive\css              # fails on non-empty dir
Remove-Item -Recurse -Force archive\  # succeeds, deletes contents too

## Task 5.3 — Search
Get-ChildItem -Recurse -Filter *.html       # 3 HTML files found
Select-String -Path src\index.html -Pattern "class"
Get-ChildItem -Recurse | Select-String -Pattern "contact" -List

## Task 5.3 — Answers
1. HTML files: 3
2. Files containing "contact": docs\contact.html
3. CSS file line count: 1
4. Last 10 commands: Get-History | Select-Object -Last 10

## Task 5.4 — Script
.\new-project.ps1 my-awesome-app


