Experiments for harvesting different ontology/vocabulary repositories using Node-Red (https://nodered.org/) workflows. 

The different workflows are stored here as JSON in dedicated .nodered files. After node-red has been set up, the workflows can be imported there via clipboard (Menu > Import > Clipboard)

Currently, one test workflow is provided for EBI-OLS (http://www.ebi.ac.uk/ols/index) in file ebi_downloader.nodered, when deployed, it looks as follows:

![Image of EBI downloader workflow](https://raw.githubusercontent.com/d0rg0ld/eudat_ols_aggregator/master/node-red/EBI_Node-Red_workflow.png)

The output of the test workflow is stored in file "ebi_harvest_test" located the server-side node-red working directory 
