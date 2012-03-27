FEATURES
========

* RDF triple export with the help of RDF mappings.
* Endpoint and repository id could be change in Drupal (default:
        http://127.0.0.1:8080/openrdf-sesame/ and sti2)
* Supported OpenRDF Sesame REST API: plain OpenRDF Sesame and OWLIM
* Supported operations
        * ADD: 
          (1) Get RDF mappings
          (2) Build triples with the help of the received node and the mappings
          (3) Send the triples as <transaction> to the triplestore endpoint
        * DELETE:
          (1) Delete the graph that is related to the node (Context Value:
            http://.../node/$id)
        * UPDATE:
          (1) Call the DELETE operation
          (2) Call the ADD operation
        
TODO
====

* Add dependencies to the .info file
* Improve logging capabilities for debugging purpose
* Improve the help section
