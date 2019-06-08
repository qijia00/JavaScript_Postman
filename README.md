# JavaScript_Postman
Sample Postman scripts I created in JavaScript. Authentication information has been removed for privacy reasons.

## npm wrapper for easy execution
please follow README.md file inside each folder to install npm and execute. Newman execution examples (such as how to overwrite variables in cmd) are added to package.json. Since postman only support overwrite global variables in newman, so variables are separated into globalVariables.json and environment variables located in xx_env.json files. Global variables applies to all postman collections, and environment variables only apply to 1 collections which has the same name just without _env.

## regressionCascadeDelete.json
a complicated example to use postman.setNextRequest("") to create a tree that top node contains n 1st level children, each 1st level child contains n 2nd level children, and each 2nd level child contains n 3rd level children. This is a good example of how to use "Pre-request Script", and how to loop Postman http requests to work around its limitations (instead of loop, you have to use if else, see Tests in the POST requests).

## regressionDiagram.json
regressionDiagramx.pdf displayed the architecture design of the regressionDiagram.json file, which created a sophisticated but not overwhelming test foundation of the building information management (BIM) config APIs. The structure of regressionDiagram.json are reused multiple times in other regression scripts.
