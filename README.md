HON Lucene Levenstein Distance
=========================

Custom patch of the default Lucene Levenstein Distance that uses a more "normalized" measure.

The problem with regular Lucene Levenstein distance is that it prefers additions to swaps in certain cases.  For instance, 
Lucene gives a similarity of 0.83 between "candi" and "candid," but 0.8 between "candi" and "candy," because distances 
are normalized over the length of the longer string. A traditional Levenstein distance calculation would give the same distance for both.

This implementation attempts to give a more "classic" Levenstein distance by normalizing over the length of the target word, rather than
the max length of the two words.  This means that, in the example above, the similarity score would be 0.8 for both "candid" and "candy."


Installation
----------

Download the code and do:

```
mvn install
```

Then copy the target/hon-lucene-levenstein-1.0.jar into your Solr war's lib directory.

Developer
-----------

Nolan Lawson

Health on the Net Foundation

License
-----------

[Apache 2.0][1].

[1]: http://www.apache.org/licenses/LICENSE-2.0.html
