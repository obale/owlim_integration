FEATURES
========

* RDF triple export with the help of RDF mappings.
* Endpoint and repository id could be change in Drupal (default:
        http://127.0.0.1:8080/openrdf-sesame/ and sti2)
* Supported OpenRDF Sesame REST API: plain OpenRDF Sesame and OWLIM


Supported operations
====================       

ADD
---
  
* Get RDF mappings
* Build triples with the help of the received node and the mappings          
* Send the triples as <transaction> to the triplestore endpoint
        
DELETE
-------
          
* Delete the graph that is related to the node (Context Value: http://.../node/$id)
        

UPDATE
------
          
* Call the DELETE operation
* Call the ADD operation
 

TODO
====

* Improve logging capabilities for debugging purpose
* Improve the help section
