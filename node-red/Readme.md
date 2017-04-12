Experiments for harvesting different ontology/vocabulary repositories using Node-Red (https://nodered.org/) workflows. 

The different workflows are stored here as JSON in dedicated .nodered files. After node-red has been set up, the workflows can be imported there via clipboard (Menu > Import > Clipboard)

Currently, one test workflow is provided for EBI-OLS (http://www.ebi.ac.uk/ols/index) in file ebi_downloader.nodered, when deployed, it looks as follows:

![Image of EBI downloader workflow](https://raw.githubusercontent.com/d0rg0ld/eudat_ols_aggregator/master/node-red/EBI_Node-Red_workflow.png)

The workflow is initiated through clicking the blue button in the "timestamp" node in the upper left corner and is mainly divided into two steps, one for retrieving the ontology names stored in EBI-OLS and the other for listing all the terms in each ontology. In both steps, paging through result lists is performed by checking for the presence of "next" links ("switch" and "set msg.url" node loops) and retriggering the respective API call accordingly. The node "Debug reduce number of ontologies" currently limits the number of ontologies for which terms are retrieved to the first two ontologies in each result page.

Each term is listed in a tab separated row together with its URI, its preferred label and description and any existing alternative labels. Moreover, the ontology prefix, iri and name are listed as well. The selection and processing of API JSON results to TSV rows is performed within the node "csv formatter". Each resulting row is then appended to a TSV file "ebi_harvest_test" located in the server-side node-red working directory. The file is deleted each time the workflow is restarted.
