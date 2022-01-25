# In-memory-URL-Compression

Implementation of the In-memory url compression approach discussed in the research paper [[1]](#1). The main purpose for implementation is to test this structure while doing a broad crawling and handling huge amount of urls.

### Main idea:
URLs contain a lot of redundant information, like scheme, domain name, some query parameters, especially if we are handling many urls from the same source:
  - Usage of Delta encoding (https://en.wikipedia.org/wiki/Delta_encoding) would save a lot of space, by only saving the difference of the new inserted URL compared    to the previous one.
  - However Delta encoding has a limitation: URLs need to be sorted first, then compressed. After having a compressed data, inserting a new URL, requires to sort all data again ==> AVL tree data structure come into rescue.

Implement AVL tree data structure (https://en.wikipedia.org/wiki/AVL_tree) to make insert search, and deletion for URLs easy and fast.

This structure can save more than 50% of space in cases where URLs share a lot of redundant information, especially if they are from the same host.

Time complexity of AVL trees insert, search and deletion operations is O(log n)
Space complexity is O(n).
  


## References
<a id="1">[1]</a>
Koht-arsa, K., & Sanguanpong, S. (2001, November). In-memory URL compression. In National Computer Science and Engineering Conference.
