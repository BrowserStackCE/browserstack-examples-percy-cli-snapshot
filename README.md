## Percy_CLI_Standalone

This repository provides an approach to compare your Static Web pages using Percy for visual changes across multiple browsers and releases.

## How it works

This repo is purely depended on the npm package https://www.npmjs.com/package/@percy/cli which is used to interact with percy.io and upload the screenshot/snapshots for visual comparison

We make use of a simple yml file to configure all the URLs that needs to tested for visual comparison. 
In this project the snapshot.yml file serves as a configuration file will all the URLs. 

## Getting Started 

 1. Clone the repository

    2. Ensure you have the following dependencies install on the Machine

    - node >= 12
    - npm >= 8

    3. Install the percy packacge

    '''sh
    npm install --save-dev @percy/cli
    '''

    4. Update the required URLs in snapshot.yml file. 
        This project has a baseURL defined and the endpoints as defined a urls for each snapshots. 

    5. Once you have the URL update. Please Export the Percy_Token form you percy.io project setting. Refer to this document for more info. (https://www.browserstack.com/docs/percy/get-started/create-project)
    '''sh 
    export PERCY_TOKEN=web_**********
    '''
    6. Now, Let's create a baseline build for comparison purpose. 
    '''sh
    PERCY_BRANCH=golden_state percy snapshot –base-url <application-url> <percy-config-file.yml>
    '''
    7. Once you have the basebuild create you can now trigger a comparison build against the basebuild. 
    '''sh
    PERCY_BRANCH=golden_state percy snapshot –base-url <application-url> <percy-config-file.yml>
    '''sh
    PERCY_BRANCH=release_v2 PERCY_TARGET_BRANCH=golden_state percy snapshot –base-url <application-url> <percy-config-file.yml>
    '''
    8. Once this is complete you should now be able to login to Percy.io dashboard view the build you just created with all the visual changes highlighted. 






# Percy_CLI_Standalone
