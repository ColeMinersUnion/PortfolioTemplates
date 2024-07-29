# PortfolioTemplates
## Basics

While not necessary to start, I recommand having basic knowledge of HTML, CSS and Javscript.
This tutorial will be using react, while not mandatory, I like react and since I'll be using this 
for my friends, it'll be easier for me to answer questions with them. 

## Setup
### Installations
Please install the latest version of [Node.js](https://nodejs.org/en/download/prebuilt-installer)
To check that node has been downloaded, open your terminal and run
```bash
npm -v
```

### Vite
Now, to create the website we will run the following commands
```bash
#making the folder to hold our portfolio
mkdir portfolio
cd portfolio

npm create vite@latest myportfolio --template
#use your arrow keys to scroll to where it says react.
#hit enter
#scroll to Javascript
#hit enter

cd myportfolio
npm install
npx vite --host
```
Tada! You have a website. 

## Page navigation with React-Router-Dom
To find documentation on React-Router-Dom, please visit [ReactRouter](https://reactrouter.com/en/main)

In the src directory add two folders, Components and Pages. The directory should appear as:

