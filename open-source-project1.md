I will start in point wise.

> This is my first project writeup. any feedback will be much appreciated,

## 1. Thinking phase

<img src="https://media.tenor.com/-HfTRwXMWT0AAAAd/kid-thinking.gif" width="200"/>

I'm very interested in open-source projects, and I was thinking of creating one myself. So, I started something like a simple project, and at that time I was reading another article [111 Linux commands](https://dev.to/scorcism/linux-commands-all-purpose-l06), and I thought, Why not create something similar to this one?

Many of the forks want the meaning of commands in one line itself.

So, I packed my bag (my desk) and sat outside for 10–20 minutes and started thinking.

<img src="https://media.tenor.com/skrB3dpqD-oAAAAM/waiting-alone-lonely.gif" width="200"/>

## 2.  Wireframe setup
 <img src="https://i.gifer.com/origin/f5/f5159d95d3c419029c28b136615b4096_w200.gif" width="200"/>
 
Initially, I thought I would create a simple website with very minimal UI because my main intention was to add commands, which would require a lot of time.

The main question was: how am I going to handle the command, like, from where will I get the command's answer?

using an API?

I thought the same, but this will become costly as for the API, I have to create a form, I have to add validations, I also have to check if the user doesn't dump garbage data, I have to create some eternal storage and handle that storage, and for the contribution, I have to look into something that will all be so much.

After some time, I thought of storing all the commands in a simple JSON file and fetching the data from that file. As everything will be a JSON file, it will be handy for the contributors to contribute to a simple file.

Then,

I knew I was going to use react from the beginning.

Next, we'll go over all of the pages I'll need. I decided with `home page` only because it would increase the complexity.

This is all the process I went through, and this took around 30 minutes to do.

So, I will go with

**Tech Stack**
 - React JS
 - JSON
 - CSS

yes i have use simple css coz it will expand more scope for others to contribute and implement their ideas.

### React project setup

run the command

```bash
npx create-react-add oneliner # oneliner -> app name
cd onliner
npm i react-router-dom
```
**Creating pages, components, brands, and assets folders**  
**Pages** will contain the 404 page.  
**Assets** will contain the JSON file.  
**components** will contain the parts of the page. e.g., `header`, footer, and body content for the homepage  
**Brands** will contain the GitHub logo.

```bash
cd src
mkdir assets
mkdir components
mkdir pages
mkdir brands

cd components
touch Header.jsx
touch 	Body.jsx
touch Footer.jsx
touch Answer.jsx
touch Action.jsx 
cd ..

cd pages
touch 
NotFound.jsx
cd ..

cd assets
touch DB.json
cd ..

cd brands
touch GitHub.jsx
```


now moving to the coding part

## 3. Coding
**Now, as the wireframe is created,we will start with he actual `coding`**

<img src="https://media.tenor.com/GfSX-u7VGM4AAAAC/coding.gif" />

**`App.jsx`**
```bash
vim App.jsx
```
```jsx

import { Routes, Route, BrowserRouter } from  'react-router-dom'
import  Body  from  './components/Body'
import  Footer  from  './components/Footer'
import  Header  from  './components/Header'
import  NotFound  from  './pages/NotFound'
function  App() {

return (
		<>
		<BrowserRouter>
		<Header  />
		<Routes>
		<Route  path="/"  element={<Body  />}  />
		<Route  path="/*"  element={<NotFound  />}  />
		</Routes>
		<Footer  />
		</BrowserRouter>
		</>
)
}
export  default  App
```
### Components

**component:** `Header.jsx`
```bash
cd components
vim Header.jsx
```
```jsx
import { Link } from "react-router-dom";

const Header = () => {
    return (
        <>
            <header>
                <h1><Link to="/">one-liner</Link></h1>
            </header>
        </>
    )
}
export default Header;
```
**component**: `Footer.jsx`
```bash
vim Footer.jsx
```
```jsx
import Action from "./Action";

const Footer = () => {
    return (
        <>
            <div className="footer">
                <footer>
                    <Action />
                    <a href="//github.com/asPerRequirements/oneliner" className="underline-animation" rel="noreferrer">asPerRequirements</a>
                    <p className="small"><a href="https://opensource.org/" className="" target="_blank" rel="noreferrer">Open Source Project</a> by <a href="//github.com/scorcism" rel="noreferrer" target="_black">Abhishek Pathak</a></p>
                </footer>
            </div>
        </>
    )
}
export default Footer;
```
**component :** `Body.jsx`
```bash
vim Body.jsx
```
```jsx
// For routing
import { useEffect, useState } from "react";
import Answer from "./Answer";
// DB
import DB from "../assets/DB.json"

const Body = () => {
	// State to manage data
    const [data, setData] = useState([]);
    const [answer, setAnser] = useState([])
    const [showAnswer, setShowAnswer] = useState(false)

	// To search from the data and store it in answer
    const handleSearch = (e) => {
        let value = e.target.value
        data.forEach(block => {
            if (block.question.toLowerCase() === value.toLowerCase()) {
                setAnser(block)
                setShowAnswer(true)
            }
        })
    }

    useEffect(() => {
        setData(DB);
    }, [])

    return (
        <>
            <section className="main__body">
                <div className="body_container">
                    <div className="body__fields">
                        <input type="text" onChange={handleSearch} name="geet" className="body__fields--input" id="little" placeholder="Enter Keyword ..." />
                    </div>
                </div>
            </section>
            <section className="section__answer">
                <Answer answer={answer} showAnswer={showAnswer} setShowAnswer={setShowAnswer}/>
            </section>
        </>
    )

}

export default Body;
```
**component :** `Answer.jsx`

```bash
vim Answer.jsx
```
```jsx

const Answer = ({ answer, showAnswer, setShowAnswer }) => {

    const hide = () => {
        setShowAnswer(false);
    }
    return (
        <>
            {
                showAnswer &&
                <div className="answer">
                    <div className="answer_conatiner">

                        <p className="answer__p">
                            {answer.answer}
                        </p>
                        <button onClick={hide} className="hide_answer">x</button>
                    </div>
                </div>
            }
        </>
    )
}
export default Answer;
```
**component :**`Action.jsx`
```bash
vim Action.jsx
```
```jsx
import GitHub from "../brands/GitHub"

const Action = () => {
    return (
        <>
            <div className="action__container">
                <div className="actions">
                    <GitHub />
                </div>
            </div>
        </>
    )
}

export default Action
```

### Pages
**pages**: `NotFound.jsx`

```bash
cd ../pages
vim NotFound.jsx
```

```bash
import { Link } from "react-router-dom";

const NotFound = () =>{
    return (
        <>
            <div className="notfound">
                <h1>Not Found</h1>
                <Link to="/">Home</Link>
            </div>
        </>
    )
}

export default NotFound;
```
### Brands
**brands**: `GitHub.jsx`
```bash
cd ../brands
vim GitHub.jsx
```
```jsx

const GitHub = () => {

    return (
        <>
            <div>
                <a href="//github.com/asPerRequirement/oneliner" target="_black" rel="noreferrer">
                    <img className="github" src="/github.svg" alt="github" title="Github Repo" />
                </a>
            </div>
        </>
    )
}

export default GitHub;
```

**assets**: `DB.json`
### JSON DB
```bash
cd ../assets/
vim DB.json
```

```json
[
    {
        "question": "chmod",
        "answer": "change permissions of a file",
        "category": "linux"
    },
    {
        "question": "ls",
        "answer": "list directory contents",
        "category": "linux"
    },
    {
        "question": "cd",
        "answer": "Change directory",
        "category": "linux"
    },
    {
        "question": "chown",
        "answer": "Change Ownership of file",
        "category": "linux"
    }
]
```
##  css
**CSS**: `index.css`
```bash
cd ..
vim index.css
```

Not Pasting here, coz its a lengthy file. you can follow [this](https://raw.githubusercontent.com/asPerRequirements/oneliner/main/src/index.css) link.

**Now all the coding part is done**

## 4. Run the application 
<img src="https://gifdb.com/images/high/crayon-shin-chan-rock-n-roll-dance-eeirpj1dbdmjzgih.gif"/>

1. **Open terminal** 
2. **Enter**
	```bash
	npm run start
	```
### 4. **output:**
![output](https://imgur.com/U0DMPCC.png)

![op](https://imgur.com/FiAvYC5.png)

## Conclusion

### [You can click on this to access the project](https://github.com/asPerReqirements/oneliner)

This project is very much simple and has very less features your contribution will be much appreciated.

**any feedback about the article will make me more happy**

---

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
