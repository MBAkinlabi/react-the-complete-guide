# Using Create React App
- There's a tool that creates the React project for us.
- You can simply Google `create react app` to find the link to its official GitHub repository.
- On that GitHub page, you'll find installation instructions and detailed explanation of what it does. 
- We'll install it globally with NPM.
- To use NPM, you need to install NodeJS. You can download and install from NodeJS.org
- The latest version is good, if you have problem, choose the LTS version. 
- When downloading NodeJS to use NPM. Don't worry we're not writing NodeJS code.
- After downloading, run this command as directed on the `create react app` on GitHub.
- Follow the instructions on that GitHub page you've visited.
- Author continues. (for the sake of this course follow the instructions here to avoid mistakes and errors).
- Go to the folder you want to run the react app and do this:
```shell
sudo npm install create-react-app -g`
```
- `cd` into the folder you want to create your react app.
- **NOTE** to follow the author well and avoid mistakes because of new updates, you should do the following:
- Run this command:
```shell
create-react-app my-app --scripts-version 1.1.5
```
- This impacts the structure of the project. Do this to ensure that we don't have any problems.
- You have to navigate into the newly creately folder.
```shell
cd my-app
```
- Then run `npm start` to start your project.
- What this does is that it starts the development server, which opens a new tab in your browser. Or, at least, it should open that tab.  
- In case it doesn't you can manually open the browser and visit http://localhost:3000/
- This is the first demo app created for you.
- The compiled successfully or server in the terminal should be kept on running. It shouldn't be closed. That's the server.
- Don't quit. But you can always quit it if you want by hitting `control + c`
- If you quit it, it'll stop watching your files. 
- Whenever you change something in your code, the page will automatically reload and reflect the latest changes. 
- You can quit the server when you're done developing. But as long you're developing, keep it open.
- 