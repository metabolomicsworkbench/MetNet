# MetNet
MetNet (Metabolite enrichment, pathways and networks)

Given a list of metabolites, e.g., metabolites with significant change between two conditions such as disease/normal or treatment/control in a metabolomics study obtained by using <a href="https://github.com/metabolomicsworkbench/MetENP" target="_blank" rel="noopener noreferrer">MetENP</a> or another tool, a metabolomics researcher may want to find what are the pathways and functions affected. MetENP provides lists of metabolic pathways affected, but does not provide such information for the signaling/regulatory pathways affected, e.g., through protein-protein interaction (PPI). MetNet, which is a metabolite-centric tool, fills that gap. The user is strongly encouraged to understand MetENP before using MetNet. MetNet uses several features from MetENP such as metabolite name harmonization using REFMET, metabolite class enrichment, metabolic pathway enrichment and visualization and identification of reactions related to the given metabolites and the genes (enzymes) catalyzing these reactions. The gene list is used to develop their protein-protein interaction network using STRING-DB APIs. Currently, MetNet is available as a REST API. The MetNet REST API provides HTTPS-based access to MetNet via a web-browser or scripts in several programming languages such as PHP, R, Python, that can handle HTTPS requests. The results are provided as a json object or a table with the columns FileDescription and FileURL. The components of the results can be accessed following these URLs. Please note that in the REST interface, the order of the parameters is fixed.

While the MetNet REST API can be used in stand-alone mode, it is best used through a workflow development tool such as NIH CFDE Workflow Builder Tool (WBT) available at https://playbook-workflow-builder.cloud (and https://github.com/nih-cfde/playbook-partnership/; please note that some features of this API may be available only in a separate development instance available at <a href="https://github.com/metabolomicsworkbench/playbook-partnership/tree/playbook-partnership-mano-20221129" target="_blank" rel="noopener noreferrer">WBT development page for Metabolomics Workbench</a>. Downstream of the metabolite-related gene list, using the WBT, one can develop gene regulatory networks and then perform functional interpretation through pathway/gene set enrichment. The WBT also allows one to use our MetGENE tool (<a href="https://github.com/metabolomicsworkbench/MetGENE" target="_blank" rel="noopener noreferrer">MetGENE website</a> and <a href="https://smart-api.info/ui/342e4cec92030d74efd84b61650fb0ea" target="_blank" rel="noopener noreferrer">SmartAPI for MetGENE</a>), where, starting with one or more genes, one can identify the related reactions and metabolites that can serve as a starting list of metabolites for MetNet. 

More information about the MetNet REST API, including the meaning of the parameters involved and how to use it, is provided at its SmartAPI page (<a href="https://smart-api.info/registry?q=f770f3e71163f5b66bcaf5ff74616540" target="_blank" rel="noopener noreferrer">SmartAPI for MetNet</a>).

Please contact Mano Maurya (mano@sdsc.edu) for any questions.
