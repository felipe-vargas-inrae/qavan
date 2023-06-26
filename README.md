# QAVAN: <i>Query-Answering Approach for Virtual Actionable Numerical Relationships</i>

## Description
QAVAN is a query-answering approach to perform mathematical formulas on demand over Knowledge Graph (KG) data on based Semantic Web technologies. QAVAN exploit the Advanced Features of the W3C recommendation SHACL to that goal. This approach is able to compute only the mathematical formulas for the specific instances involve in a query. Thus, avoiding the problems in disk space and memory that could produce a full materialisation.

## Input parameters
QAVAN program takes as inputs:

* --conf: A valid JSON with the execution information details below
* --nestedANR: A flag to indicate that nested ANRs should be taken into account
* --inferences: A flag to indicate RDFS entailment should be taken into account for inferences 
* --unzip: A flag to indicate that the inference should be compressed, useful for big datasets 

### The config JSON file should contain the following values:
```javascript
{
  "experimentName": "Dependency ANRs Cities",
  "rootPath": "/home/",
  "graphPath": "my_graph.ttl",
  "shapePath": "my_shape.ttl",
  "queryPath" : "my_query.sparql",
  "outInferencePath" :"inference_graph.ttl",
  "outReportPath": "report.ttl",
  "outResultSet" : "results_set.csv",
  "method" : options=["VIRTUAL","MATERIALISED"]
}
```

## Running QAVAN in the command line
```
java  -jar QAVAN-1.0-SNAPSHOT.jar --config "myconf.json" 
```
## Outputs 
QAVAN provide three outputs:
* an inference graph in format RDF Turtle
* query results in tabular CSV format
* a report containing the execution time and the sizes of the inputs along with further details.

## Experiments
For the experiments we use three main datasets:
* [Meteo-France](https://www.kaggle.com/datasets/katerpillar/meteonet)  
* [DBPedia](https://databus.DBpedia.org/DBpedia/)  version: 2022.09.01.
* [Eurostat](https://ec.europa.eu/eurostat/web/cities/data/database)  
This repository contains two folders: 
* Meteo-France folder 
* DBPedia folder
Each folder contains an example of how to run it.

## Used technologies
* Apache Jena version 4.3.2
* SHACL-API version 1.4.2

