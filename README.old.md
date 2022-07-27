**Edit a file, create a new file, and clone from Bitbucket in under 2 minutes**

When you're done, you can delete the content in this README and update the file with details for others getting started with your repository.

*We recommend that you open this README in another tab as you perform the tasks below. You can [watch our video](https://youtu.be/0ocf7u76WSo) for a full demo of all the steps in this tutorial. Open the video in a new tab to avoid leaving Bitbucket.*

---
**Deploying react app to s3 bucket using bitbucket.

## creating the repo 

``The first thing is to create new repo for this 

to create new repo we need to fill the follling blocks that are prescribed in the pic:-

<img width="608" alt="Screenshot 2022-07-27 at 11 42 15 PM" src="https://user-images.githubusercontent.com/70562150/181343030-b9aa8324-860d-4b9e-b818-07c24197f945.png">


that is <project name>;<Repository name>;<Access level(i.e wheather to keep it public or private)>;<Default branch name>; etc then click on 

create repository ,it will create your repo.

``now ,you have to clone the repo locally to work further ,for that you need to use this command:- that you will find on right of your repo name``

`with "clone" option there you need to just copy paste the command` 

'In my case it is :---

```
git clone https://vivekvishal011@bitbucket.org/vivekvishal011/react-app.git

```

`then go to project directory with cd command `

`in my case it is :---

```
cd react-app
```

## prerequisite for react-app creation

Create React App requires a Node version of at least 10.


A package manager called npm. It is automatically included in your installation of Node. You need to have an npm version of at least 5.2.



``you have installed "Install Node.js and NPM" (in my case i'm using mac so these commands are used)``

``Install Node.js and NPM on Mac``

Type the following command to install Node.js and NPM:

```
brew install node
```
Homebrew downloads and installs the dependencies.

When the installation finishes, confirm that you successfully installed Node.js by checking its version:

```
node -v
```

The system displays the Node.js version as the output of the command.

Next, check the installed version of NPM by typing:

```
npm -v
```

```for more details use this link ::---https://phoenixnap.com/kb/install-npm-mac```

## Creating React App

```
npx create-react-app <name of the app you want to create> 

in my case name is (react-app)
```

when you run this command, a folder named "react-app" will be created where we specified on our computer and all of the packages,

it requires will be automatically installed.

``The Project Structure``

when our project files have been created and our dependencies have been installed, our project structure should look like this:

<img width="769" alt="Screenshot 2022-07-28 at 12 16 55 AM" src="https://user-images.githubusercontent.com/70562150/181349080-50ab3e33-0958-4c00-a926-12b928914edb.png">

1.> "README.md" is a markdown file that includes a lot of helpful tips and links that can help you while learning to use Create React App.

2.> "node_modules" is a folder that includes all of the dependency-related code that Create React App has installed.

You will never need to go into this folder.

3.> "package.json" that manages our app dependencies and what is included in our node_modules folder for our project, 

plus the scripts we need to run our app.

4.> ".gitignore" is a file that is used to exclude files and folders from being tracked by Git. 

We don't want to include large folders such as the node_modules folder

5.> "public" is a folder that we can use to store our static assets, such as images, svgs, and fonts for our React app.

6.> "src" is a folder that contains our source code. It is where all of our React-related code will live and 

is what we will primarily work in to build our app.

```
Note: A new Git repository is created whenever you make a new project with Create React App. You can start saving 

changes to your app right away using "<git add .>" and "<git commit -m "your commit message".>"
```

``for more details about file , run and all you need to visit this link:--

https://www.freecodecamp.org/news/how-to-build-a-react-project-with-create-react-app-in-10-steps/#:~:text=Create%20React%20App%20requires%20a,version%20of%20at%20least%205.2.``

till here our react-app is created ,now i have to create a file with the name "bitbucket-pipelines.yml" file ;

that will conatins the pipeline scripts to perform the bulid,test and deploy task.

for the build and test job 

<img width="878" alt="Screenshot 2022-07-28 at 12 34 15 AM" src="https://user-images.githubusercontent.com/70562150/181352229-ec247869-8b0d-4124-b6c5-006375f745d0.png">

after that we need to push all files to the repo for that need to perform these commands:

```
gid add .

git commit -m <"commit sms">

git push 
```
if everything goes well here then you will see the results,otherwise you will

get a issue saying configure 2fa i.e two factor authontication 

to deal with you need to authonticate with mobile instaling the app suggested in the bitbucket and perform the step accordingly.
<img width="768" alt="Screenshot 2022-07-28 at 12 42 11 AM" src="https://user-images.githubusercontent.com/70562150/181353417-782839c7-07d4-4c74-bd88-ee2c2ee11e41.png">

after completing this you can enable the pipeline then go to pipeline >>> you will see the pipeline is running and got success you will get the result
<img width="1272" alt="Screenshot 2022-07-28 at 12 47 35 AM" src="https://user-images.githubusercontent.com/70562150/181354284-2d7d6020-be52-4805-997e-a7ab46f9221b.png">


## custom pipeline

  now let setup custom pipeline ; a custom pipeline only runs manually

``for deployment i,m going to set production to deploy the things on s3 bucket``

pipeline to deploy objects on s3

<img width="861" alt="Screenshot 2022-07-28 at 12 54 02 AM" src="https://user-images.githubusercontent.com/70562150/181355305-75686fa8-f569-4afd-8d6c-3a5b333aa887.png">

``for the env variables``


if you go to bitbucket >>> repository settings >>> within the pipeline section ---deployments is there need to select that 

then there you will find everything like test environment , build , production etc ,

you need the enter the variable in the same stage where you used that envirinment varible in the pipelines.

{Iin my case i used  for production so i specify every varibles in the production section}

<img width="1191" alt="Screenshot 2022-07-28 at 1 04 42 AM" src="https://user-images.githubusercontent.com/70562150/181357074-cc055546-6449-4ad7-b5e2-553366e64c06.png">


onces you are done with all these thing then again you just need to commit and push the changes to the repo 

for that you need to use this commnd :

```
git add .
git commit -m "commit sms"
git push
```
you will see on going to pipelie that it is running and get success.

now to run then custom pipelines you need to goo on pipeline >> run pipeline >> choose the branh you need to perform >>

>> pipeline then ok.


<img width="1224" alt="Screenshot 2022-07-28 at 1 10 04 AM" src="https://user-images.githubusercontent.com/70562150/181358088-f65fe630-ba5d-4d7c-b3da-dd22185a135d.png">


``if everythings goes well then you will see the result else you will find an error saying deployment object permission ``

``for that you need to go on s3 bucket and check and correct the acl settings.``

``now re-run the pipeline you will see the results.``

<img width="1250" alt="Screenshot 2022-07-28 at 1 15 06 AM" src="https://user-images.githubusercontent.com/70562150/181358863-a763fe18-4426-4eb9-a17e-5f17412ca1d0.png">

``deployment successful in s3.``









## Happy bitbucketing.....!


