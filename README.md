# Postman_JavaScript_npm
Sample Postman scripts I created in JavaScript with Chai Assertion Library. The scripts are also packaged by npm for easy execution and integration to CI/CD pipeline with Jenkins. Authentication information has been removed for privacy reasons.

## npm package for easy execution
Please follow README.md file inside each folder to install npm and execute. Newman execution examples (such as how to overwrite variables in cmd) are added to package.json. Since postman only support overwrite global variables in newman, so variables are separated into globalVariables.json and environment variables located in xx_env.json files. Global variables applies to all postman collections, and environment variables only apply to 1 collections which has the same name just without _env.

## regressionCascadeDelete.json
A complicated example to use postman.setNextRequest("") to create a tree that top node contains n 1st level children, each 1st level child contains n 2nd level children, and each 2nd level child contains n 3rd level children. This is a good example of how to use "Pre-request Script", and how to loop Postman http requests to work around its limitations (instead of loop, you have to use if else, see Tests in the POST requests).

## regressionDiagram.json
regressionDiagram.png displayed the architecture design of the regressionDiagram.json file, which created a sophisticated but not overwhelming test foundation of the building information management (BIM) config APIs. The structure of regressionDiagram.json are reused multiple times in other regression scripts.

## regressionFloor.json
Pre-request of POST EGF/SVG includes how to generate random guid. Also you can see how to randomly pick a node or relation from a return then use it in future calls (look for randomxXx in the http call's name).

## sanityConfigBulkUpdate.json
In the Test area of "Get /v1/bulkupdate/{id} Create Completed", you can see how to wait for a bulk upload to be processed and check the result every 10 seconds.

## sanityResourceResources.json
In the Tests of "GET /v1/resources/{organizationId} ORGANIZATION", there is a for loop with embeded if else statements to handle random return orders (i.e., jpg may returned as the first element of the list or the second or the thrid or the last.).
When POST a resource in Postman (say a JPG), from the POST call body, enter key "resources", and select key type to be File, then add the JPG to the Value filed. 
When run the script in Newman, you need to define {{filePath}} relative path in globalVariables.json, and change request - body - format - src of the collection json to something like {{filePath}}name.jpg

## regressionGetNodeRelations.json
This script contains a performance check, i.e., how long it should take for the entire script to run. I capture the time in the pre-request script of the 1st http call, and capture the time again in the test section of the last http call, and assert the difference of these 2 times.
