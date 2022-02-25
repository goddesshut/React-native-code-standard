# File Structure

The main idea is that each module we define has all the code related to it and only code from the module itself is imported. When we have several modules that need the same piece of code, we can write it into a common and import it into the different modules.

**The fundamental rule to be followed is not to import code between modules.**

For our project, we seperate folder structure to be 2 part.
1) Create folder "app" to contain every module that we have. This folder is main that using for launching application
2) Create folder "packages" per module.


### Structure base on files type
Creating "src" in root directory of our project. We will keep UI, Bussiness logic, utilies, constans and everything on our app uses inside this directory.<br>
"index.ts" file in each module will export only screen that be main root or shared to main application.
```
SIRIUS-MOBILE
|-- app/
|   |-- src/
|   |-- app.json
|   |-- package.json
|-- packages/
|   |-- commons/
|   |-- moduleA/
|   |   |-- src/
|   |   |   |-- components/
|   |   |   |-- screens/
|   |   |   |-- services/
|   |   |   |-- models/
|   |   |   |-- utils/
|   |   |   |-- hooks/
|   |   |   |-- index.ts/
|   |-- moduleB/
|-- package.json
|-- .tsconfig
```

### Feature based
#### Screen and component
Most important part of our project are the `screens` and `components` the reusable on which we would work on mostly.

#### The screen directory
In "screens" directory. Should create a directory for each screen and create multiple file each for UI, types, bussiness logic, state management, types into seperate file. In case project will be huge it will be easier to mange in each screen.
```
SIRIUS-MOBILE
|-- packages/
|   |-- moduleA/
|   |   |-- src/
|   |   |   |-- screens/
|   |   |   |   |-- Home/
|   |   |   |   |   |-- components/
|   |   |   |   |   |   |-- NetworthCard.tsx
|   |   |   |   |   |-- HomeScreen.tsx
|   |   |   |   |   |-- types.ts
```

In case you want a simpler structure, you don’t need to create directories for each screen
```
SIRIUS-MOBILE
|-- packages/
|   |-- moduleA/
|   |   |-- src/
|   |   |   |-- screens/
|   |   |   |   |-- HomeScreen.tsx
```

#### The component directory
In "components" directory. Base on reusable component you can put all your component files inside root. If component will contain more than 1 file, you should create sub folder inside and If creating any custom resuable components It's should seperate them out as well.
```
SIRIUS-MOBILE
|-- packages/
|   |-- commons/
|   |   |-- components/
|   |-- moduleA/
|   |   |-- src/
|   |   |   |-- components/
|   |   |   |   |-- CustomCard/
|   |   |   |   |   |-- CustomCard.tsx
|   |   |   |   |   |-- types.ts
|   |   |   |   |-- CusttomButton.tsx
```
**<font color=red>The component should reuseable inside this module. If the component can shared to other module you should put it on common</font>**

#### The services directory
In "services" directory will contain all of api or backend services should go into a separate directory.<br>
It should seperate file by api or backend endpoint that will connnected. Should create file "types" as enum also for each service function that we have
```
SIRIUS-MOBILE
|-- packages/
|   |-- moduleA/
|   |   |-- src/
|   |   |   |-- services/
|   |   |   |   |-- homeService.ts
|   |   |   |   |-- currentOrderService.ts
```

#### The hooks directory
In 'hooks' directory will contain all the bussiness logic, state management or shared query.<br>
"types.ts" file is a type declation file 
```
SIRIUS-MOBILE
|-- packages/
|   |-- moduleA/
|   |   |-- src/
|   |   |   |-- hooks/
|   |   |   |   |-- useHome.ts
|   |   |   |   |-- types.ts
```

#### The utils directory
We all might write some utility functions which we could use throughout the application. All that code should go into this directory. You can have multiple files to categorize your utility functions.
```
SIRIUS-MOBILE
|-- packages/
|   |-- moduleA/
|   |   |-- src/
|   |   |   |-- utils/
|   |   |   |   |-- stringUtils.ts
|   |   |   |   |-- dateUtils.ts
```