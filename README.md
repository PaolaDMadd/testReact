# React for newbie: how to deploy react-app in GitHub pages in few steps


1) in terminal use << npx create-react-app file-Name >> to create a new react file.
2) verify that the app is running correctly using the cmd-line <<npm start>> NB make sure it is the correct file.
3) Create an empty repository in github without a readme.nd file, and make sure it is on public status. (don't leave the page as it contains some instuction you'll need later).
4) go back to terminal (little hint to close the server use << ^ c >> for mac).
5) run the command << npm install gh-pages --save-dev>>
this command creates the package.json file, you need to modify adding 3 important lines:

6)      one in the beginning << "homepage": "https://PaolaDMadd.github.io/testReact">> 
        the url needs to be created in this way : "https://githubUserName.github.io/repositoryName"

        the second and third will be in the script section add  
        "predeploy": "npm run build", 
        and
        "deploy": "gh-pages -d build",

NB:     each line ends with a comma (otherwise the code will break)
        Also make sure the 3 elemnts you are adding are not in a concatenate array and that the devDependencies         appears as follows:
        
        "devDependencies": {
        "gh-pages": "^2.2.0"
        }

7) To initialize git use the command <<git init>> (make sure you are in the correct file)
8) Then run the command << git remote add origin https://PaolaDMadd.github.io/testReact.git >> NB: this line will be available on the github initial empty repository page.

This is the right moment to make all modification to the file...be creative!!

9) Let's check if everithing is fine running the command << git status >> this will show all the changes.
   Changes need to be added and committed first using : 
10) <<git add .>> 
11) <<git commit -m ' add a comment to the commit'>>
    NB: if this is the first deploy at this point our user name and password can be required.

now the deploy command can be run to connect the code to the github pages.
12) <<npm run deploy>> 
The final step is to push the code on our repositiory using
13) <<git push -u origin master>>
14) It's always better check the new repository we created and see if everything is fine. 
    in the setting tabs scoll down to Github Pages a link will be there with the default branch.
   
Congratulations!! 
