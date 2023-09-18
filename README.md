# MetNet
MetNet (Metabolite enrichment, pathways and networks)

Given a list of metabolites, e.g., metabolites with significant change between two conditions such as disease/normal or treatment/control in a metabolomics study obtained by using <a href="https://github.com/metabolomicsworkbench/MetENP">MetENP</a> or another tool, a researcher may want to find what are the pathways and functions affected. MetENP provides a list of metabolic pathways affected, but it does not provide such information for signaling/regulatory pathways affected, e.g., using protein-protein interaction (PPI) information. MetNet, which is a metabolite-centric tool, fills that gap. The user is strongly encouraged to understand MetENP before using MetNet. MetNet uses several features from MetENP such as metabolite name harmonization using REFMET, metabolite class enrichment, metabolic pathway enrichment and visualization and identification of reactions related to the given metabolites and the genes (enzymes) catalyzing these reactions. The gene list is used to develop their PPI network using STRING-DB APIs. Currently, MetNet is available as a REST API. The MetNet REST API provides HTTPS-based access to MetNet via a web-browser or scripts in several programming languages such as PHP, R, Python, that can handle HTTPS requests. The results are provided as a json object or a table with the columns FileDescription and FileURL. The components of the results can be accessed following these URLs. Please note that in the REST interface, the order of the parameters is fixed.

While the MetNet REST API can be used in stand-alone mode, it is best used through a workflow development tool such as the NIH Common Fund Data Ecosystem (CFDE) Workflow Builder Tool (WBT) available at https://playbook-workflow-builder.cloud (see also https://github.com/nih-cfde/playbook-partnership/ and please note that some features of this API may be available only in a separate development instance available at <a href="https://github.com/metabolomicsworkbench/playbook-partnership/tree/playbook-partnership-mano-20221129">WBT development page for Metabolomics Workbench</a>). Downstream of the metabolite-related gene list, using the WBT, one can develop gene regulatory networks and then perform functional interpretation through pathway/gene set enrichment. The WBT also allows one to use our MetGENE tool (<a href="https://github.com/metabolomicsworkbench/MetGENE">MetGENE website</a> and <a href="https://smart-api.info/ui/342e4cec92030d74efd84b61650fb0ea">SmartAPI for MetGENE</a>), where, starting with one or more genes, one can identify the related reactions and metabolites that can serve as a starting list of metabolites for MetNet. 

More information about the MetNet REST API, including the meaning of the parameters involved and how to use the API, is provided at its SmartAPI page (<a href="http://smart-api.info/registry?q=67cc0e21b6238472f6f1f00e6b7c32aa">SmartAPI for MetNet</a>).

## Examples:

### Example of specifying the list of metabolites in a file (one metabolite per line):

The file URL, https://sc-cfdewebdev.sdsc.edu/tmp/metlist.txt, is tripple encoded (using rawurlencode in php or encodeURIComponent in javascript/typescript).

https://bdcw.org/MetENP/rest/metclass/sub_class/updown_fillcolor/red__green__blue/enrich_stats/HG/no/1/sps/hsa/padj/fdr/kegg_comp_path/FALSE/geneoption/TRUE/PPIopt/1_1000_900/location/1/metlistfname/https%25253A%25252F%25252Fsc-cfdewebdev.sdsc.edu%25252Ftmp%25252Fmetlist.txt/View/txt

### Example of specifying the list of metabolites directly in the URL (separated by \n, then tripple encoded, so that, \n becomes %25255Cn):
List of metabolites (as a comma separated list):
NAD+, NADH, NADPH, NADP+, Glucose 6-phosphate, 6-Phosphonoglucono-D-lactone, Ribulose 5-phosphate, 6-Phosphogluconic acid, Xylulose 5-phosphate, Glyceraldehyde 3-phosphate, Erythrose 4-phosphate, 
Sedoheptulose 7-phosphate, Fructose 6-phosphate, Ribose 5-phosphate, ATP, ADP, Xylulose

https://bdcw.org/MetENP/rest/metclass/sub_class/updown_fillcolor/red__green__blue/enrich_stats/HG/no/1/sps/hsa/padj/BH/kegg_comp_path/FALSE/geneoption/TRUE/PPIopt/1_1500_700/location/0/metlistfname/NAD%25252B%25255CnNADH%25255CnNADPH%25255CnNADP%25252B%25255CnGlucose%2525206-phosphate%25255Cn6-Phosphonoglucono-D-lactone%25255CnRibulose%2525205-phosphate%25255Cn6-Phosphogluconic%252520acid%25255CnXylulose%2525205-phosphate%25255CnGlyceraldehyde%2525203-phosphate%25255CnErythrose%2525204-phosphate%25255CnSedoheptulose%2525207-phosphate%25255CnFructose%2525206-phosphate%25255CnRibose%2525205-phosphate%25255CnATP%25255CnADP%25255CnXylulose/View/json

Please contact Mano Maurya (mano@sdsc.edu) for any questions.
