
```
This project provides a drop-in replacement for the std::tr1::unordered_map
and std::tr1::unordered_map containers. We also hope to eventually make it
API-compatible with google::densehash.

This hash table implementation uses the cuckoo hashing algorithm. This is
an algorithm rather similar to the traditional linear hashing except that
old elements are actually allowed move inside the hash array.

See http://en.wikipedia.org/wiki/Cuckoo_hashing for details.

The advantage of the cuckoo hashing algorithm is that you can build hash
tables with extremely high load ratio (>99.9% is typical unless your hash
function is truly broken), without sacrificing worst-case lookup efficiency.

Just like  hash tables with linear probing implementation (e.g. google::densehash)
constructing a table with a very high load ratio will be a bit expensive: insertion
time gets longer and longer as load gets neat 100%. However, once constructed, the
data structure guarantees a fast worst-case constant time lookup.

In summary, if you use a cuckoo hash table, you can an construct in-memory lookup
structures that are extremely memory efficient and still guaranteed to perform a
lookup in worst-case constant time.
```