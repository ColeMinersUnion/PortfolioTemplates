# Basics

While not necessary to start, I recommand having basic knowledge of HTML, CSS and Javscript.
This tutorial will be using react, while not mandatory, I like react and since I'll be using this 
for my friends, it'll be easier for me to answer questions with them. If you already feel comfortable with
the tech stack used in this project, feel free to ignore this readme and start playing with the code. 


# Setup
## Installations
Please install the latest version of [Node.js](https://nodejs.org/en/download/prebuilt-installer)
To check that node has been downloaded, open your terminal and run
```bash
npm -v
```

## Vite
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

# Page navigation with React-Router-Dom
To find documentation on React-Router-Dom, please visit [ReactRouter](https://reactrouter.com/en/main)

In your temrinal, please run
```bash
npm install react-router-dom
```

In the src directory add two folders, Components and Pages. The directory should appear as:\
src/\
├── assets/\
├── components/\
├── pages/\
├── App.css\
├── App.jsx\
├── index.css\
└── main.jsx

In the components folder we will create two new files: Navbar.jsx and Footer.jsx
## Navbar.jsx
We will be creating a very simple navbar to navigate between pages. 

```javascript
import { Link } from 'react-router-dom';

//navbar
//we will add more links as our portfolio expands.
export default function Navbar(){
  return (
    <>
      <Link to={'/'}>
        <a>Home</a>
      </Link>
    </>
  );
} 
```

## Footer.jsx
Now we will create a footer to sit at the bottom of all of our pages. 
```javascript
export default function Footer(){
    return (
      <>
        <h4>This website was built by Cole Hansen</h4>
        <h4>07/29/2024</h4>
      </>  
    );
}
```

## Main.jsx
Adding a layout, router and router provide. 

```javascript
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './index.css'

import { Outlet, createBrowserRouter, RouterProvider } from 'react-router-dom'
import Navbar from './components/Navbar.jsx'
import Footer from './components/Footer.jsx'

const Layout = () => {
  return (
    <>
      <Navbar/>
      <Outlet/>
      <Footer/>
    </>
  );
};

const router = createBrowserRouter([{
  path:'/',
  element:<Layout/>,
  children : [
    {
      path:'/',
      element:<App/>
    }
  ]
}])

ReactDOM.createRoot(document.getElementById('root')).render(
  <RouterProvider router={router}></RouterProvider>
)
```

# Adding Pages

Here we'll add two more pages. An about page, and a project page. In the pages directory, add two new files. \
pages/\
├── About.jsx\
└── Projects.jsx

## About.jsx
```javascript
export default function About(){
  //lipsum!
  return (
        <>
            <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Donec imperdiet lorem convallis, sodales massa quis, ornare ipsum. 
                Sed tellus ligula, consequat vitae venenatis eget, volutpat vitae purus. 
                Donec ut justo odio. Vivamus non lectus et nunc congue rhoncus eu ac ligula. 
                Nunc in ultricies tortor, vel tempor justo. 
                Proin consequat elit eu nisi pulvinar euismod. 
                Phasellus sollicitudin id sapien vitae porta. 
                Suspendisse nibh lectus, vehicula sed mi aliquet, faucibus malesuada lectus.
                Mauris laoreet quam eget arcu pharetra, nec sagittis justo rutrum. 
                Cras finibus porttitor augue malesuada eleifend. 
                Donec non nunc at purus dapibus pulvinar quis eu ipsum.
                Mauris eget erat non diam aliquet mollis sed vel turpis. 
                Ut porttitor tristique rutrum. Nullam in venenatis lorem. 
                Suspendisse potenti. Mauris venenatis ligula tortor, 
                quis auctor orci molestie sit amet. 
                Donec fermentum cursus turpis ac fermentum. 
                Suspendisse sed ultricies ipsum, nec lacinia nisi. 
                Vivamus leo eros, porttitor a eleifend quis, aliquam at diam. 
                Aliquam interdum iaculis lectus, nec sagittis magna condimentum eu.
                Sed facilisis felis et varius ultricies. 
                Sed dapibus imperdiet ipsum in consectetur. 
                Donec eget arcu quis dolor tempus rutrum. 
                Mauris semper mi hendrerit mauris scelerisque, eu consequat odio auctor.
                Donec mattis hendrerit laoreet. Duis sodales elementum risus quis pulvinar. 
                Mauris nec efficitur turpis, nec semper mauris. Mauris ut nibh lacus.
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
                In elit diam, dictum nec nibh eu, pharetra congue est. 
                Donec pellentesque venenatis metus et maximus. 
                Morbi in nunc et leo rhoncus dapibus. Nam sed arcu ac erat efficitur posuere. 
                Orci varius natoque penatibus et magnis dis parturient montes, 
                nascetur ridiculus mus. 
                Vivamus viverra gravida felis, sagittis maximus tortor egestas id.
                Aenean vitae neque et dolor consectetur interdum nec sed sapien. 
                Mauris sodales ipsum et leo tempus cursus et non metus. 
                Aliquam id elementum nunc, ac vulputate arcu. 
                Mauris cursus ut urna tempus lacinia. 
                Nam ornare cursus diam non eleifend. 
                Suspendisse elementum suscipit sem et imperdiet. 
                Aliquam mollis mollis tortor quis blandit. 
                Suspendisse auctor velit tortor, ut dictum arcu blandit non. 
                Proin dapibus, erat eget fermentum aliquam, dui odio gravida diam, 
                vitae malesuada metus ipsum ac magna. 
                Aenean eleifend urna ac nisi lobortis, sit amet bibendum neque imperdiet. 
                Pellentesque est dui, sagittis in nibh at, aliquet euismod tortor. 
                Proin id quam eget nunc viverra sollicitudin sit amet eu turpis. 
                Vivamus sit amet imperdiet nisi, ut fermentum libero. 
                Lorem ipsum dolor sit amet, consectetur adipiscing elit.
                Integer vehicula, orci ut imperdiet iaculis, odio sapien fermentum ante, 
                non efficitur leo tellus vitae neque. 
                Etiam vel elit pharetra, aliquet lectus ac, mattis nisl. 
                Aliquam erat volutpat. Duis gravida elit in ultrices maximus. 
                Donec augue nisi, viverra pharetra vulputate vitae, vehicula sit amet massa.
                Pellentesque blandit in nibh vitae accumsan. Ut vel tellus quam. 
            </p>
        </>
    );
}
```
## Projects.jsx
## Updating older files
### Main.jsx
### Navbar.jsx
