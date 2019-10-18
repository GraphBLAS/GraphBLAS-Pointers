# GraphBLAS pointers

* [GraphBLAS.org](http://graphblas.org/)
* [HPC Graph Analysis](http://www.graphanalysis.org/)

If you're new to GraphBLAS, I suggest reading the starred items first :star:.

## Readings

### Papers and specifications

* Jeremy Kepner et al.: [Mathematical Foundations of the GraphBLAS](https://people.eecs.berkeley.edu/~aydin/GraphBLAS-Math.pdf), HPEC 2016
  * :star: A more detailed version of this paper is part of the ["GraphBLAS Mathematics - Provisional Release 1.0"](http://www.mit.edu/~kepner/GraphBLAS/GraphBLAS-Math-release.pdf) specification document (2017)
  * An updated version of this paper is also reprinted in the [Mathematics of Big Data](https://mitpress.mit.edu/books/mathematics-big-data) (2018) as Chapter 6, p81-113.
* Aydin Buluc, Tim Mattson, Scott McMillan, Jose Moreira, Carl Yang: [The GraphBLAS C API Specification (version 1.3.0)](https://people.eecs.berkeley.edu/~aydin/GraphBLAS_API_C_v13.pdf) (deprecated: [version 1.2.0](https://people.eecs.berkeley.edu/~aydin/GraphBLAS_API_C_v12.pdf))

### GraphBLAS design papers

* Timothy G. Mattson et al.: [Standards for graph algorithm primitives](https://arxiv.org/abs/1408.0393), HPEC 2013
* Jeremy Kepner, David A. Bader, Aydın Buluç, John R. Gilbert, Timothy G. Mattson, Henning Meyerhenke: [Graphs, Matrices, and the GraphBLAS: Seven Good Reasons](https://arxiv.org/ftp/arxiv/papers/1504/1504.01039.pdf), ICCS 2015
* Jeremy Kepner et al.: [Mathematical Foundations of the GraphBLAS](https://people.eecs.berkeley.edu/~aydin/GraphBLAS-Math.pdf), HPEC 2016
* Timothy G. Mattson, Carl Yang, Scott McMillan, Aydın Buluç, José E. Moreira: [GraphBLAS C API: Ideas for future versions of the specification](https://people.eecs.berkeley.edu/~aydin/GrB_futures_hpec17.pdf), HPEC 2017

### Implementation details

* Timothy A. Davis: [Algorithm 9xx: SuiteSparse:GraphBLAS: graph algorithms in the language of sparse linear algebra](http://faculty.cse.tamu.edu/davis/GraphBLAS_files/toms_graphblas.pdf), submitted to ACM Trans. Math. Softw.
* Ariful Azad, Aydın Buluç: [A Work-Efficient Parallel Sparse Matrix-Sparse Vector Multiplication Algorithm](https://arxiv.org/pdf/1610.07902.pdf), IPDPS 2017
* John R. Gilbert, Steven P. Reinhardt, Viral B. Shah: [High-Performance Graph Algorithms from Parallel Sparse Matrices](http://gauss.cs.ucsb.edu/publication/gapdt-para06.pdf), Workshop on Applied Parallel Computing (PARA), 2006

### Books

* Jeremy Kepner, John R. Gilbert: [Graph Algorithms in the Language of Linear Algebra](https://epubs.siam.org/doi/book/10.1137/1.9780898719918), SIAM, 2011
    * Note that GraphBLAS was on the drawing board at this time – neither the notation, nor the API was finalized.
* Jeremy Kepner, Hayden Jananthan: [Mathematics of Big Data: Spreadsheets, Databases, Matrices, and Graphs](https://mitpress.mit.edu/books/mathematics-big-data), MIT Press, 2018
    * This book is currently the latest detailed reference on semiring-based computations, including graph algorithms. That said, the book is aimed at a broader audience and covers many other topics as well including associative arrays. The book is not intended to be a GraphBLAS refernece (it only mentions GraphBLAS once), but it can be used for providing a background in linear algebra (see e.g. Chapter 8, "Visualizing the Algebra of Associative Arrays").

## Implementations

### Core implementations

* [SuiteSparse:GraphBLAS](http://faculty.cse.tamu.edu/davis/GraphBLAS.html)
    * This is released both as an individual package and (less frequently) as part of [SuiteSparse](http://faculty.cse.tamu.edu/davis/suitesparse.html).
    * There are also some (often outdated) [mirror](https://github.com/sergiud/SuiteSparse/tree/master/GraphBLAS) [repositories](https://github.com/jluttine/suitesparse/) on GitHub.
* [GraphBLAS Template Library (GBTL)](https://github.com/cmu-sei/gbtl): C++ implementation
* [IBM GraphBLAS](https://github.com/IBM/ibmgraphblas)
* [GraphBLAST](https://github.com/gunrock/graphblast)
* [PyGB](https://github.com/jessecoleman/gbtl-python-bindings)
* [GraphMat](https://github.com/narayanan2004/GraphMat/)
    * Narayanan Sundaram: [GraphMat: High performance graph analytics made productive](http://www.vldb.org/pvldb/vol8/p1214-sundaram.pdf), VLDB 2015
    * Michael J. Anderson et al.: [GraphPad: Optimized Graph Primitives for Parallel and Distributed Platforms](https://ieeexplore.ieee.org/abstract/document/7516027), IPDPS 2016

### Related implementations

* [Graphulo](https://graphulo.mit.edu/) (in [Apache Accumulo](https://accumulo.apache.org/))
    * [Repository](https://github.com/Accla/graphulo)
* [D4M](http://www.mit.edu/~kepner/D4M/)
    * [Repository](https://github.com/Accla/d4m)
    * [D4M.jl](https://github.com/Accla/D4M.jl): Julia implementation
    * [D4M.py](https://github.com/Accla/D4M.py): Python implementation
* [pggraphblas](https://github.com/michelp/pggraphblas): Postgres GraphBLAS implementation
* [RedisGraph](https://redislabs.com/redis-enterprise/redis-modules/redis-enterprise-modules/redisgraph/)
* Combinatorial BLAS (CombBLAS): "An extensible distributed-memory library offering a small but powerful set of linear algebraic operations specifically targeting graph analytics." _Influences the development of GraphBLAS._
    * Paper - Aydın Buluç, John R. Gilbert: [The Combinatorial BLAS: design, implementation, and applications](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.916.6801&rep=rep1&type=pdf), Int. J. High Perform. Comput. Appl. 2011 ([paper entry at the publisher's site](https://journals.sagepub.com/doi/10.1177/1094342011403516)). This paper is referred to as a "strawman proposal" on GraphBLAS.org
    * [Documentation](https://people.eecs.berkeley.edu/~aydin/CombBLAS/html/)
    * [Slides](https://people.eecs.berkeley.edu/~aydin/talks/CombBLAS_Nov11.pdf)
* Viral B. Shah, Alan Edelman, Stefan Karpinski, Jeff Bezanson, Jeremy Kepner: [Novel algebras for advanced analytics in Julia](https://dspace.mit.edu/handle/1721.1/115964), HPEC 2013
    * [Repository](https://github.com/JuliaComputing/SemiringAlgebra.jl)

## Algorithms

* LAGraph: library of algorithms for GraphBLAS (similarly to LAPACK for BLAS)
    * Paper - Timothy G. Mattson, Timothy A. Davis, Manoj Kumar, Aydın Buluç, Scott McMillan, Jose Moreira and Carl Yang: [LAGraph: A Community Effort to Collect Graph Algorithms Built on Top of the GraphBLAS](http://faculty.cse.tamu.edu/davis/GraphBLAS_files/lagraph-grapl19.pdf), GrAPL @ IPDPS 2019 ([source](https://github.com/GraphBLAS/GrAPL19))
    * [LAGraph repository on GitHub](https://github.com/GraphBLAS/LAGraph)
* Ariful Azad, Aydın Buluç: [LACC: A Linear-Algebraic Algorithm for Finding Connected Components in Distributed Memory](https://people.eecs.berkeley.edu/~aydin/LACC.pdf), IPDPS 2019
* Timothy A. Davis: [Graph algorithms via SuiteSparse:GraphBLAS: triangle counting and K-truss](http://faculty.cse.tamu.edu/davis/GraphBLAS_files/Davis_HPEC18.pdf), HPEC 2018
* Tze Meng Low, Varun Nagaraj Rao, Matthew Lee, Doru-Thom Popovici, Franz Franchetti, Scott McMillan: [First look: Linear algebra-based triangle counting without matrix multiplication](http://spiral.ece.cmu.edu:8080/pub-spiral/pubfile/hpec_2017_low_289.pdf), HPEC 2017
* Michael M. Wolf, Jonathan W. Berry, Dylan T. Stark: [A task-based linear algebra building blocks approach for scalable graph analytics](https://docs.inf.mit.bme.hu/graph-generation-papers/hpec15-wolf.pdf), HPEC 2015
* Ariful Azad, Aydın Buluç, John R. Gilbert: [Parallel Triangle Counting and Enumeration Using Matrix Algebra](https://crd.lbl.gov/assets/pubs_presos/triangles-gabb.pdf), GABB @ IPDPS 2015
* Carl Yang, Aydın Buluç, John D. Owens: [Implementing Push-Pull Efficiently in GraphBLAS](https://arxiv.org/pdf/1804.03327.pdf), ICPP 2018

## Presentations

### Tutorials

* Scott McMillan, Timothy G. Mattson: [Hands-on tutorial for GraphBLAS](https://github.com/tgmattso/GraphBLAS), HPEC 2018, 2019

### GraphBLAS

* :star: Aydın Buluç: [GraphBLAS: concepts, algorithms, and applications](https://scheduling2019.sciencesconf.org/file/566318), June 2019
* John R. Gilbert: [GraphBLAS: Graph Algorithms in the Language of Linear Algebra](https://sites.cs.ucsb.edu/~gilbert/talks/Gilbert-27Jun2019.pdf), June 2019
* John R. Gilbert: [Graph Algorithms in the Language of Linear Algebra](https://sites.cs.ucsb.edu/~gilbert/cs240a/slides/old/cs240a-GALA.pdf), CS 240A presentation adapted from Intel Non-Numeric Computing Workshop, 2014
* John R. Gilbert: [Building Blocks for Graph Algorithms in the Language of Linear Algebra](https://sites.cs.ucsb.edu/~gilbert/talks/GilbertCIMI7July2015.pdf)
* John R. Gilbert: [Graph Algorithms in the Language of Linear Algebra: How did we get here, where do we go next?](https://pdfs.semanticscholar.org/e0e3/a850ca03f5092aaa45152e53bd77af689567.pdf), IPDPS Graph Algorithms Building Blocks 2018
* Jeremy Kepner, Vijay Gadepally, Ben Miller: [Graph Analytics expressed in GraphBLAS](http://www.mit.edu/~kepner/Graphulo/141222-GraphuloInGraphBLAS.pptx), 2014
* Timothy A. Davis: [SuiteSparse:GraphBLAS: graph algorithms via sparse matrix operations on semirings](https://cerfacs.fr/wp-content/uploads/2017/09/S02E04-Davis.pdf), Sparse Days 2017 at CERFACS
* :star: Scott McMillan: [Graph Algorithms on Future Architectures](https://resources.sei.cmu.edu/asset_files/Presentation/2015_017_001_446303.pdf), CMU SEI Research Review 2015
    * [Poster](https://resources.sei.cmu.edu/asset_files/Poster/2015_020_001_446691.pdf)
    * [Video](https://www.youtube.com/watch?v=-sIdS4cz7-4)
* Scott McMillan: [GraphBLAS: A Programming Specification for Graph Analysis](https://resources.sei.cmu.edu/asset_files/Presentation/2016_017_001_474272.pdf), SEI Research Review 2016
    * [Poster](https://resources.sei.cmu.edu/asset_files/Poster/2016_020_001_484268.pdf)
* Scott McMillan: [Design and Implementation of the GraphBLAS Template Library (GBTL)](https://resources.sei.cmu.edu/asset_files/Presentation/2016_017_001_494328.pdf), SIAM Annual Meeting 2016
* Scott McMillan: [Automated Code Generation for High-Performance, Future-Compatible Graph Libraries](https://resources.sei.cmu.edu/asset_files/Presentation/2017_017_001_506482.pdf), SEI Research Review 2017
    * [Poster](https://resources.sei.cmu.edu/asset_files/Poster/2017_020_001_506622.pdf)
    * [Video](https://www.youtube.com/watch?v=tiKrQrYarmA)
* Aydın Buluç: [Graph algorithms, computational motifs, and GraphBLAS](https://people.eecs.berkeley.edu/~aydin/ECP_GraphBLAS_Buluc.pdf), ECP Annual Meeting 2018
* Aydın Buluç: [Concepts in the GraphBLAS C API](https://people.eecs.berkeley.edu/~aydin/GraphBLAS_March2017.pdf), 2017
* Ariful Azad, Aydın Buluç: [Parallel Algorithms across the GraphBLAS Stack](https://people.eecs.berkeley.edu/~aydin/Buluc-ACS-June2017-web.pdf), ACS HPC and Data Analytics Workshop 2017
* Aydın Buluç: [Faster parallel GraphBLAS kernels](https://people.eecs.berkeley.edu/~aydin/UCB_October2016.pdf), EECS, UC Berkeley, 2016
* Aydın Buluç: [The Graph BLAS effort and its implications for Exascale](https://people.eecs.berkeley.edu/~aydin/ex14_graph_blas.pdf), SIAM Workshop on Exascale Applied Mathematics Challenges and Opportunities (EX14), 2014
* Michael Wolf: [Task Parallel Approach to the Linear Algebra-Based Implementation of miniTri Michael Wolf](https://www.osti.gov/servlets/purl/1369523), SIAM Annual Meeting, 2016
* Albert-Jan Yzelman: [Efficient sparse matrix computations and their generalization to graph computing applications](http://wiki.ldbcouncil.org/pages/viewpage.action?pageId=59277315), Linked Data Benchmark Council, Technical User Community meeting, 2017
* Gábor Szárnyas: [Multiplex graph analysis with GraphBLAS](https://fosdem.org/2019/schedule/event/graph_multiplex_analysis_graphblas/), Graph Developer room at FOSDEM 2019

### Accumulo

* Vijay Gadepally, Lauren Edwards, Jeremy Kepner: [Using D4M for rapid prototyping of analytics for Apache Accumulo](http://accumulosummit.com/2015/program/talks/using-d4m-for-rapid-prototyping-of-analytics-for-apache-accumulo/), Accumulo Summit 2015
* Vijay Gadepally, Timothy Weale, Dylan Hutchison, Jeremy Kepner: [Graphulo: Graph Analytics in Apache Accumulo](http://accumulosummit.com/2016/program/talks/graphulo/), Accumulo Summit 2016
    * There are many papers, posters, and presentations in the [Accumulo repository](https://github.com/Accla/graphulo/tree/master/docs)
* Jeremy Kepner: [Accumulo and the Convergence of Machine Learning, Big Data, and Supercomputing](http://accumulosummit.com/2017/program/talks/convergence-of-machine-learning-big-data-and-supercomputing/), Accumulo Summit 2017
* Lauren Milechin, Hayden Jananthan, Vijay Gadepally, Jeremy Kepner: [Interacting with Accumulo and Graphulo using Julia/Python D4M](http://accumulosummit.com/2018/program/talks/accumulo-and-graphulo-using-julia-python-d4m/), Accumulo Summit 2018
* Dylan Hutchison, Jeremy Kepner, Vijay Gadepally, Adam Fuchs: [Server-side Sparse Matrix Multiply in the Accumulo Database](http://www.ieee-hpec.org/2015/Final_Presentations/19_Paper862015-08-10-graphulo-tablemult.pdf), HPEC 2015

### RedisGraph

* Roi Lipman, Timothy A. Davis: [Lower Latency Graph Queries in Cypher with Redis Graph](https://www.youtube.com/watch?v=xnez6tloNSQ), RedisConf 2018
    * [GraphBLAS section](https://www.youtube.com/watch?v=xnez6tloNSQ?t=304)
    * [Slides](https://www.slideshare.net/RedisLabs/redisconf18-lower-latency-graph-queries-in-cypher-with-redis-graph)
* Roi Lipman: [Deep Dive into RedisGraph](https://www.youtube.com/watch?v=4KS2MRccQX4), 2019
    * [Slides](https://www.slideshare.net/RedisLabs/redisgraph-internals-roi-lipman)

## Events

| year | HPEC                                                       | IPDPS workshop                                         |
| ---- | ---------------------------------------------------------- | ------------------------------------------------------ |
| 2019 | [HPEC](http://www.ieee-hpec.org/)                          | [GrAPL](https://github.com/GraphBLAS/GrAPL19)          |
| 2018 | [HPEC](http://www.ieee-hpec.org/2018/)                     | [GABB](http://graphanalysis.org/workshop2018.html)     |
| 2017 | [HPEC](http://ieee-hpec.org/2017/techprog2017/sept13.htm)  | [GABB](http://graphanalysis.org/workshop2017.html)     |
| 2016 | [HPEC](http://ieee-hpec.org/2016/techprog2016/sept14.htm)  | [GABB](http://graphanalysis.org/workshop2016.html)     |
| 2015 | [HPEC](http://www.ieee-hpec.org/2015/)                     | [GABB](http://www.graphanalysis.org/workshop2015.html) |
| 2014 | [HPEC](http://www.ieee-hpec.org/2014/copy/agendatext.html) | [GABB](http://www.graphanalysis.org/workshop2014.html) |
| 2013 | [HPEC](http://ieee-hpec.org/2013/agenda.htm)               | -                                                      |

## News, blogs, interviews

* [Blog by Tim Davis](http://aldenmath.com/blog/)
* [GraphBLAS: Building Blocks For High Performance Graph Analytics](https://crd.lbl.gov/news-and-publications/news/2017/graphblas-building-blocks-for-high-performance-graph-analytics/) - Berkeley Lab Researchers Contribute to GraphBLAS and Will Leverage it for Exascale Applications
* [ACM's interview with Tim Davis](https://www.acm.org/articles/people-of-acm/2019/tim-davis)
* [First Person: Tim Davis](https://www.americanscientist.org/article/first-person-tim-davis), American Scientist

## MAGiQ: a GraphBLAS-based RDF query engine

* Fuad Jamour, Ibrahim Abdelaziz, Panos Kalnis: [A Demonstration of MAGiQ: Matrix Algebra Approach for Solving RDF Graph Queries](http://www.vldb.org/pvldb/vol11/p1978-jamour.pdf), VLDB demonstration, 2018
* Fuad Jamour, Ibrahim Abdelaziz, Yuanzhao Chen, Panos Kalnis: [Matrix Algebra Framework for Portable, Scalable and Efficient Query Engines for RDF Graphs](https://dl.acm.org/citation.cfm?doid=3302424.3303962), EuroSys 2019
* Fuad Jamour: [Algorithms and Frameworks for Graph Analytics at Scale](https://repository.kaust.edu.sa/bitstream/handle/10754/631280/FuadJamourThesis.pdf?sequence=3), PhD thesis, 2019

## Related papers

* Daniele G. Spampinato et al.: [Linear Algebraic Depth-First Search](https://dl.acm.org/citation.cfm?doid=3315454.3329962), ARRAY workshop at PLDI, 2019
