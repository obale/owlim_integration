FEATURES
========

* RDF triple export with the help of RDF mappings.
* Endpoint and repository id could be change in Drupal (default:
        http://127.0.0.1:8080/openrdf-sesame/ and sti2)
* Supported OpenRDF Sesame REST API: plain OpenRDF Sesame and OWLIM


Installation
============

Create OWLIM repository with the help of the following template (~/.aduna/openrdf-sesame-console/templates/eswc2013.ttl)

    @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#>.
    @prefix rep: <http://www.openrdf.org/config/repository#>.
    @prefix sr: <http://www.openrdf.org/config/repository/sail#>.
    @prefix sail: <http://www.openrdf.org/config/sail#>.
    @prefix owlim: <http://www.ontotext.com/trree/owlim#>.

    [] a rep:Repository ;
        rep:repositoryID "{%Repository ID|eswc2013%}" ;
        rdfs:label "{%Repository title|ESWC Repository%}" ;
        rep:repositoryImpl [
            rep:repositoryType "openrdf:SailRepository" ;
            sr:sailImpl [
                sail:sailType "swiftowlim:Sail" ;
                owlim:ruleset "{%Set of rules|rdfs%}" ;
                owlim:noPersist "{%No Persistence|false|true%}" ;
                owlim:storage-folder "{%Storage folder|eswc2013-storage%}" ;
                owlim:base-URL "http://eswc-conferences.org#" ;
                owlim:entity-index-size "{%entity index size|200000%}" ;
                owlim:repository-type "in-memory-repository" ;
                owlim:imports "{%imports(';' delimited)|%}" ;
                owlim:defaultNS "{%defaultNS(';' delimited)|%}"
            ]
        ].

Use _openrdf-console_ to create on the base of the template eswc2013.ttl the repository eswc2013:

    ~/openrdf-console/bin$ sh console.sh
    > connect http://127.0.0.1:8080/openrdf-sesame .
    [some output]
    > create eswc2013.
    [interactive shell]
    > exit.


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
