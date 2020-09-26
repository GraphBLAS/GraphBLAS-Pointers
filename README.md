# GraphBLAS Pointers

Notation:
* :star: if you're new to GraphBLAS, check out these pointers first
* :hammer: theory-focused
* :wrench: implementation-focused
* :hammer_and_wrench: mix of theory and implementation
* :book: detailed specification

## Community sites

* :bird: [GraphBLAS Twitter page](https://twitter.com/GraphBLAS)
* [GraphBLAS.org](http://graphblas.org/)
* [HPC Graph Analysis](http://www.graphanalysis.org/)

## Selected readings and presentations

* :star: [GraphBLAS Wikipedia page](https://en.wikipedia.org/wiki/GraphBLAS)
* :star: [Graph Analytics: A Foundational Building Block for the Data Analytics World](https://techdecoded.intel.io/big-picture/graph-analytics-a-foundational-building-block-for-the-data-analytics-world/), Tim Mattson, Henry Gabb (2020)

### GraphBLAS design papers

* :hammer: [Standards for graph algorithm primitives](https://arxiv.org/pdf/1408.0393.pdf) (HPEC 2013) by Tim Mattson et al.
* :hammer: [Graphs, Matrices, and the GraphBLAS: Seven Good Reasons](https://arxiv.org/ftp/arxiv/papers/1504/1504.01039.pdf) (ICCS 2015) by Jeremy Kepner et al.
* :hammer: :star: [Mathematical Foundations of the GraphBLAS](https://people.eecs.berkeley.edu/~aydin/GraphBLAS-Math.pdf) (HPEC 2016) by Jeremy Kepner et al.
  * Extended version: [GraphBLAS Mathematics - Provisional Release 1.0](http://www.mit.edu/~kepner/GraphBLAS/GraphBLAS-Math-release.pdf) (2017)
* :hammer_and_wrench: [Design of the GraphBLAS API for C](https://people.eecs.berkeley.edu/~aydin/GABB17.pdf) (GABB @ IPDPS 2017) by Aydın Buluç et al.
* :hammer_and_wrench: [GraphBLAS C API: Ideas for future versions of the specification](https://people.eecs.berkeley.edu/~aydin/GrB_futures_hpec17.pdf) (HPEC 2017) by Tim Mattson et al.
* :wrench: [Implementing the GraphBLAS C API](https://ieeexplore.ieee.org/document/8425425) (GABB @ IPDPS 2018) by José E. Moreira, Manoj Kumar, William P. Horn

### Tutorials

* :hammer: :star: [GraphBLAS: A linear algebraic approach for high-performance graph algorithms](http://mit.bme.hu/~szarnyas/grb/graphblas-introduction.pdf) by Gábor Szárnyas: an introduction to GraphBLAS with 100+ slides
  * :movie_camera: [Talk at FOSDEM 2020's HPC room](https://fosdem.org/2020/schedule/event/graphblas/) (abridged version)
  * [Case studies, algorithms, and other slide decks](http://mit.bme.hu/~szarnyas/grb/)
* :hammer_and_wrench: :star: [Hands-on tutorial for GraphBLAS](https://github.com/tgmattso/GraphBLAS) (HPEC 2018-) by Scott McMillan and Tim Mattson
* :wrench: :star: [Introduction to GraphBLAS with Python](https://www.youtube.com/watch?v=JUbXW_f03W0) (2019) by Michel Pelletier

### Specifications

* :hammer_and_wrench: :book: [The GraphBLAS C API Specification](https://people.eecs.berkeley.edu/~aydin/GraphBLAS_API_C_v13.pdf) by Aydın Buluç, Tim Mattson, Scott McMillan, José Moreira, Carl Yang
  * Summary paper: [Design of the GraphBLAS API for C](https://people.eecs.berkeley.edu/~aydin/GABB17.pdf) (GABB @ IPDPS 2017)
* :hammer_and_wrench: :book: [SuiteSparse:GraphBLAS User Guide](https://github.com/DrTimothyAldenDavis/GraphBLAS/blob/stable/Doc/GraphBLAS_UserGuide.pdf) by Tim Davis

## Algorithms

* :wrench: :star: LAGraph – A library of algorithms for GraphBLAS, similar to LAPACK for BLAS
  * [Repository on GitHub](https://github.com/GraphBLAS/LAGraph)
  * [LAGraph Working Group](https://github.com/GraphBLAS/LAGraph-Working-Group): Public document and planning repository for the LAGraph Working Group
  * [LAGraph: A Community Effort to Collect Graph Algorithms Built on Top of the GraphBLAS](http://faculty.cse.tamu.edu/davis/GraphBLAS_files/lagraph-grapl19.pdf) (GrAPL @ IPDPS 2019) by Tim Mattson et al.

### Generic

* :wrench: [Parallel GraphBLAS with OpenMP](http://faculty.cse.tamu.edu/davis/publications_files/CSC20_OpenMP_GraphBLAS.pdf) (SIAM Workshop on Combinatorial Scientific Computing, CSC 2020) by Mohsen Aznaveh et al.
* :hammer: [GraphBLAS: Handling performance concerns in large graph analytics](https://www.ibm.com/university/power/images/CF2018.pdf) (Computing Frontiers 2018) by Manoj Kumar, José Moreira, Pratap Pattnaik
* Many algorithms are described as an example in the specification and in papers about frameworks:
  * The [specification](https://people.eecs.berkeley.edu/~aydin/GraphBLAS_API_C_v13.pdf) has BFS (levels/parents), betwenness centrality, maximal independent set (Luby's algorithm) and triangle count
  * The [GraphBLAS CF paper](https://www.ibm.com/university/power/images/CF2018.pdf) has deep neural network (feed-forward pass), betweenness centrality and PageRank.
  * The [SuiteSparse TOMS paper](https://people.engr.tamu.edu/davis/GraphBLAS_files/toms_graphblas.pdf) has BFS and maximal independent set (Luby's algorithm).
  * The [GraphBLAS Template Library](https://github.com/cmu-sei/gbtl) has many textbook algorithms including maxflow and minimum spanning tree (Prim's).
  * LAGraph has many algorithms including [community detection using label propagation](https://github.com/GraphBLAS/LAGraph/blob/master/Source/Algorithm/LAGraph_cdlp.c) and an [SCC algorithm](https://github.com/GraphBLAS/LAGraph/blob/master/Source/Algorithm/LAGraph_scc.c).
  * [BFS algorithm computing the DAG of the traversal](https://gist.github.com/szarnyasg/6ffccfd8963de7e1b58a6a7084d34b8b)

### Traversals and shortest paths

* :hammer_and_wrench: `[BFS]` [Optimal algebraic Breadth-First Search for sparse graphs](https://arxiv.org/pdf/1906.03113.pdf) (preprint, 2019) by Paul Burkhardt 
* :hammer_and_wrench: `[BFS]` [Implementing Push-Pull Efficiently in GraphBLAS](https://arxiv.org/pdf/1804.03327.pdf) (ICPP 2018) by Carl Yang, Aydın Buluç, John D. Owens
  * This paper forms the basis of Chapter 5 in Carl Yang's PhD thesis, [High-Performance Linear Algebra-based Graph Framework on the GPU](https://escholarship.org/content/qt37j8j27d/qt37j8j27d.pdf) (2019). The figures in the conference paper have some coloring issues that have been amended in the thesis.
  * [Presentation](https://www.ece.ucdavis.edu/~ctcyang/pub/icpp-slides2018.pdf)
* :hammer: `[DFS]` [Linear Algebraic Depth-First Search](https://dl.acm.org/doi/10.1145/3315454.3329962) (ARRAY workshop @ PLDI 2019) by Daniele G. Spampinato et al.
  * :movie_camera: [Video](https://www.youtube.com/watch?v=fKim6IKdr8U)
* :hammer_and_wrench: `[SSSP]` [Delta-Stepping SSSP: From Vertices and Edges to GraphBLAS Implementations](https://arxiv.org/pdf/1911.06895.pdf) (GrAPL @ IPDPS 2019) by Upasana Sridhar et al.
  * In its Preliminaries section, this paper contains the translation of a few vertex-centric and edge-centric design patterns to linear algebra.

### Connected components

* :hammer_and_wrench: `[CC]` [Parallel algorithms for finding connected components using linear algebra](https://escholarship.org/content/qt8ms106vm/qt8ms106vm.pdf) (Journal of Parallel and Distributed Computing 2020) by Yongzhe Zhang, Ariful Azad, Aydın Buluç
* :hammer_and_wrench: `[CC]` [FastSV: A Distributed-Memory Connected Component Algorithm with Fast Convergence](https://arxiv.org/abs/1910.05971) (PP 2020) by Yongzhe Zhang, Ariful Azad, Zhenjiang Hu
* :hammer_and_wrench: `[CC]` [LACC: A Linear-Algebraic Algorithm for Finding Connected Components in Distributed Memory](https://people.eecs.berkeley.edu/~aydin/LACC.pdf) (IPDPS 2019) by Ariful Azad and Aydın Buluç

### Triangle counting, k-truss, clustering coefficient

* :wrench: [Graph algorithms via SuiteSparse:GraphBLAS: Triangle counting and K-truss](http://faculty.cse.tamu.edu/davis/GraphBLAS_files/Davis_HPEC18.pdf) (HPEC 2018) by Tim Davis
* :hammer_and_wrench: Tze Meng Low et al.'s work on triangle counting:
    * [First look: Linear algebra-based triangle counting without matrix multiplication](http://spiral.ece.cmu.edu:8080/pub-spiral/pubfile/hpec_2017_low_289.pdf) (HPEC 2017) by Tze Meng Low et al.
    * [A Family of Provably Correct Algorithms for Exact Triangle Counting](https://dl.acm.org/doi/10.1145/3145344.3145484) (Correctness @ SC 2017) by Matthew Lee and Tze Meng Low
        * [Presentation](https://correctness-workshop.github.io/2017/papers/low.pdf)
    * [Linear Algebraic Formulation of Edge-centric K-truss Algorithms with Adjacency Matrices](https://users.ece.cmu.edu/~franzf/papers/hpec_2018_tml.pdf) (HPEC 2018) by Tze Meng Low et al.
* :hammer: [Parallel Triangle Counting and Enumeration Using Matrix Algebra](https://crd.lbl.gov/assets/pubs_presos/triangles-gabb.pdf) (GABB @ IPDPS 2015) by Ariful Azad, Aydın Buluç, John R. Gilbert
    * This paper introduced _masked matrix multiplication_ which became an important primitive in GraphBLASs.
* :hammer: [A task-based linear algebra building blocks approach for scalable graph analytics](https://www.osti.gov/servlets/purl/1531050) (HPEC 2015) by Michael M. Wolf, Jonathan W. Berry, Dylan T. Stark
    * Related presentation: [Task Parallel Approach to the Linear Algebra-Based Implementation of miniTri](https://www.osti.gov/servlets/purl/1369523) (SIAM Annual Meeting 2016) by Michael M. Wolf
    * Related presentation: [Fast Linear Algebra-Based Triangle Counting with KokkosKernels](https://www.osti.gov/servlets/purl/1470929) (IEEE	HPEC/DARPA/Amazon	Graph	Challenge at HPEC 2017) by Michael Wolf et al.

### Context-free path querying (CFPQ)

* :hammer_and_wrench: [Context-Free Path Querying with Single-Path Semantics by Matrix Multiplication](https://dl.acm.org/doi/abs/10.1145/3398682.3399163) (GRADES-NDA 2020) by Arseniy Terekhov et al.
* :hammer_and_wrench: [Context-Free Path Querying by Kronecker Product](https://www.researchgate.net/profile/Semyon_Grigorev/publication/343687331_Context-Free_Path_Querying_by_Kronecker_Product/links/5f3e8981458515b72931fbf3/Context-Free-Path-Querying-by-Kronecker-Product.pdf) (ADBIS 2020) by Egor Orachev et al.
* :hammer: [Path Querying with Conjunctive Grammars by Matrix Multiplication](https://www.researchgate.net/profile/Semyon_Grigorev/publication/337961820_Path_Querying_with_Conjunctive_Grammars_by_Matrix_Multiplication/links/5df9dde64585159aa48500d6/Path-Querying-with-Conjunctive-Grammars-by-Matrix-Multiplication.pdf) (Programming and Computer Software 2019) by Rustam Azimov and Semyon Grigorev
* :wrench: [CFPQ algorithm implementations using pygraphblas](https://github.com/JetBrains-Research/CFPQ_PyAlgo)

### Community detection

* :hammer_and_wrench: [Linear Algebraic Louvain Method in Python](https://users.ece.cmu.edu/~lowt/papers/Louvain_accepted.pdf) (GrAPL 2020) by Tze Meng Low et al.
  * :movie_camera: [Video](https://www.youtube.com/watch?v=BIu0m4Hchiw)
  * [pygraphblas implementation](https://github.com/michelp/pygraphblas/blob/master/pygraphblas/demo/Louvain.ipynb)
  
### Other

* :hammer_and_wrench: [A GraphBLAS Approach for Subgraph Counting](https://arxiv.org/pdf/1903.04395.pdf) (preprint) by Langshi Chen et al.
* :hammer_and_wrench: [Write Quick, Run Fast: Sparse Deep Neural Network in 20 Minutes of Development Time via SuiteSparse:GraphBLAS](http://faculty.cse.tamu.edu/davis/publications_files/HPEC19.pdf) (HPEC 2019) by Tim Davis, Mohsen Aznaveh, Scott P. Kolodziej
* :hammer_and_wrench: [Graph Coloring on the GPU](https://people.eecs.berkeley.edu/~aydin/coloring.pdf) (GrAPL 2019) by Muhammad Osama et al.

## Presentations

### Overviews on GraphBLAS and linear algebra-based graph processing

* :hammer: :star: Gábor Szárnyas: [GraphBLAS: A linear algebraic approach for high-performance graph algorithms](http://mit.bme.hu/~szarnyas/grb/graphblas-introduction.pdf) (introduction to GraphBLAS, 100+ slides), :movie_camera: [Talk at FOSDEM 2020's HPC room](https://fosdem.org/2020/schedule/event/graphblas/) (abridged version)
* :hammer: :star: Jeremy Kepner: [Mathematical Foundations of the GraphBLAS and Big Data](https://github.com/johnrgilbert/MDS2020-linear-algebraic-graph-tools/blob/master/MS142-Kepner-Slides.pdf) (SIAM Minisymposium 2020 on Linear Algebraic Tools for Graph Computation)
    :movie_camera: [Video](https://youtu.be/gZSNp6XbOK8?t=6)
* John R. Gilbert's talks:
  * :hammer_and_wrench: :star: [GraphBLAS: Graph Algorithms in the Language of Linear Algebra](https://sites.cs.ucsb.edu/~gilbert/talks/Gilbert-27Jun2019.pdf) (2019)
  * :hammer: [Graph Algorithms in the Language of Linear Algebra: How did we get here, where do we go next?](https://pdfs.semanticscholar.org/e0e3/a850ca03f5092aaa45152e53bd77af689567.pdf) (GABB @ IPDPS 2018)
  * :hammer_and_wrench: [Building Blocks for Graph Algorithms in the Language of Linear Algebra](https://sites.cs.ucsb.edu/~gilbert/talks/GilbertCIMI7July2015.pdf) (CIMI Workshop on Innovative Clustering Methods 2015)
  * :hammer_and_wrench: [Graph Algorithms in the Language of Linear Algebra](https://sites.cs.ucsb.edu/~gilbert/cs240a/slides/old/cs240a-GALA.pdf) (originally at Intel Non-Numeric Computing Workshop 2014)
* Scott McMillan's talks:
  * :hammer_and_wrench: :star: [Graph Algorithms on Future Architectures](https://resources.sei.cmu.edu/asset_files/Presentation/2015_017_001_446303.pdf) (CMU SEI Research Review 2015),
    :scroll: [Poster](https://resources.sei.cmu.edu/asset_files/Poster/2015_020_001_446691.pdf),
    :movie_camera: [Video](https://www.youtube.com/watch?v=-sIdS4cz7-4)
  * :hammer_and_wrench: [GraphBLAS: A Programming Specification for Graph Analysis](https://resources.sei.cmu.edu/asset_files/Presentation/2016_017_001_474272.pdf) (SEI Research Review 2016),
    :scroll:[Poster](https://resources.sei.cmu.edu/asset_files/Poster/2016_020_001_484268.pdf)    
  * :hammer_and_wrench: [Design and Implementation of the GraphBLAS Template Library (GBTL)](https://resources.sei.cmu.edu/asset_files/Presentation/2016_017_001_494328.pdf) (SIAM Annual Meeting 2016)
  * :hammer_and_wrench: [Automated Code Generation for High-Performance, Future-Compatible Graph Libraries](https://resources.sei.cmu.edu/asset_files/Presentation/2017_017_001_506482.pdf) (SEI Research Review 2017),
    :scroll: [Poster](https://resources.sei.cmu.edu/asset_files/Poster/2017_020_001_506622.pdf),
    :movie_camera: [Video](https://www.youtube.com/watch?v=tiKrQrYarmA)
  * :hammer_and_wrench: [GraphBLAS Updates](https://apps.dtic.mil/sti/pdfs/AD1088909.pdf), SC BoF: HPC Graph Toolkits and GraphBLAS Forum, 2019
* Aydın Buluç's talks:
  * :hammer_and_wrench: [GraphBLAST: A high-performance C++ GPU library implementing GraphBLAS](https://ecpannualmeeting.com/assets/overview/sessions/Buluc-GraphBLAS-ECP.pdf) (ECP Annual Meeting 2020)
  * :hammer_and_wrench: :star: [GraphBLAS: Concepts, algorithms, and applications](https://scheduling2019.sciencesconf.org/file/566318) (Scheduling Workshop 2019)
  * :hammer_and_wrench: [Graph algorithms, computational motifs, and GraphBLAS](https://people.eecs.berkeley.edu/~aydin/ECP_GraphBLAS_Buluc.pdf) (ECP Annual Meeting 2018)
  * :wrench: [Concepts in the GraphBLAS C API](https://people.eecs.berkeley.edu/~aydin/GraphBLAS_March2017.pdf) (2017)
  * :hammer: [Parallel Algorithms across the GraphBLAS Stack](https://people.eecs.berkeley.edu/~aydin/Buluc-ACS-June2017-web.pdf) (ACS HPC and Data Analytics Workshop 2017) co-authored by Ariful Azad
  * :hammer: [Faster parallel GraphBLAS kernels](https://people.eecs.berkeley.edu/~aydin/UCB_October2016.pdf) (EECS, UC Berkeley, 2016)
  * [The Graph BLAS effort and its implications for Exascale](https://people.eecs.berkeley.edu/~aydin/ex14_graph_blas.pdf) (SIAM Workshop on Exascale Applied Mathematics Challenges and Opportunities, 2014)
* :hammer_and_wrench: [Task Parallel Approach to the Linear Algebra-Based Implementation of miniTri Michael Wolf](https://www.osti.gov/servlets/purl/1369523) (SIAM Annual Meeting, 2016) by Michael Wolf
* :hammer_and_wrench: [Efficient sparse matrix computations and their generalization to graph computing applications](http://wiki.ldbcouncil.org/download/attachments/59277315/walldorf17.pdf?version=1&modificationDate=1486938217000&api=v2&download=true) (Linked Data Benchmark Council, Technical User Community meeting, 2017) by Albert-Jan Yzelman
* Tim Davis' talks:
  * :hammer_and_wrench: [SuiteSparse:GraphBLAS: Graph algorithms via sparse matrix operations on semirings](https://cerfacs.fr/wp-content/uploads/2017/09/S02E04-Davis.pdf) (Sparse Days @ CERFACS 2017)
  * :hammer_and_wrench: [SuiteSparse:GraphBLAS, a Parallel Implementation of the GraphBLAS Specification](https://github.com/johnrgilbert/MDS2020-linear-algebraic-graph-tools/blob/master/MS142-Davis-Slides.pdf) (SIAM Minisymposium 2020 on Linear Algebraic Tools for Graph Computation) :movie_camera: [Video](https://youtu.be/gZSNp6XbOK8?t=1721)
* :hammer_and_wrench: [Multiplex graph analysis with GraphBLAS](https://fosdem.org/2019/schedule/event/graph_multiplex_analysis_graphblas/) (Graph Developer room @ FOSDEM 2019) by Gábor Szárnyas

### Books

* [Graph Algorithms in the Language of Linear Algebra](https://epubs.siam.org/doi/book/10.1137/1.9780898719918) (SIAM, 2011) by Jeremy Kepner and John R. Gilbert
    * This is the best reference on the topic of linear algebra-based graph processing. However, note that GraphBLAS effort was not yet started when this book was written. Therefore, there are some differences between the notation of GraphBLAS documents and the one used in this book.
* [Mathematics of Big Data: Spreadsheets, Databases, Matrices, and Graphs](https://mitpress.mit.edu/books/mathematics-big-data) (MIT Press, 2018) by Jeremy Kepner and Hayden Jananthan
    * An updated version of paper [Mathematical Foundations of the GraphBLAS](https://people.eecs.berkeley.edu/~aydin/GraphBLAS-Math.pdf) is reprinted in this book (Chapter 6, p81-113)
    * This book is currently the latest detailed reference on semiring-based computations, including graph algorithms. It also covers many other topics such as associative arrays. The book is not intended to be a GraphBLAS reference, but it can be used for providing a background in linear algebra (see e.g. Chapter 8, "Visualizing the Algebra of Associative Arrays").

## Implementations

### Core implementations

* [SuiteSparse:GraphBLAS](http://faculty.cse.tamu.edu/davis/GraphBLAS.html)
    * [GitHub repository](https://github.com/DrTimothyAldenDavis/SuiteSparse/tree/master/GraphBLAS)
    * :hammer_and_wrench: [Algorithm 1000: SuiteSparse:GraphBLAS: Graph algorithms in the language of sparse linear algebra](https://dl.acm.org/doi/10.1145/3322125) ([preprint](http://faculty.cse.tamu.edu/davis/GraphBLAS_files/toms_graphblas.pdf)) (ACM Transactions on Mathematical Software, 2019) by Tim Davis
    * The SuiteSparse:GraphBLAS library is released both as an individual package and (less frequently) as part of [SuiteSparse](http://faculty.cse.tamu.edu/davis/suitesparse.html).
    * This library can be installed on Debian-based distributions with the `libsuitesparse-dev` package. For example, Ubuntu 20.04's default repository contains SuiteSparse:GraphBLAS 3.2.0.
* [GraphBLAS Template Library (GBTL)](https://github.com/cmu-sei/gbtl): C++ implementation (version 3.0 has been release in June 2020)
* [GraphBLAST](https://github.com/gunrock/graphblast)
    * [GraphBLAST: A High-Performance Linear Algebra-based Graph Framework on the GPU](https://arxiv.org/pdf/1908.01407.pdf), preprint by Carl Yang, Aydın Buluç, John D. Owens
    * [High-Performance Linear Algebra-based Graph Framework on the GPU](https://escholarship.org/content/qt37j8j27d/qt37j8j27d.pdf) (PhD dissertation, 2019) by Carl Yang

### Other implementations

* [IBM GraphBLAS](https://github.com/IBM/ibmgraphblas): C++ implementation in approx. 6000 lines of code.
* [GraphBLAS C99](https://github.com/bobcgausa/GraphBLAS): "C99 prototype implementation of enough of GraphBLAS standard to run first two examples in Appendix A of the standard." Consists of <800 lines of code. Only supports vxm.
* [GraphMat](https://github.com/narayanan2004/GraphMat/): linear algebra-based graph analytics framework prototype by Intel
    * [GraphMat: High performance graph analytics made productive](http://www.vldb.org/pvldb/vol8/p1214-sundaram.pdf) (VLDB 2015) by Narayanan Sundaram
    * [GraphPad: Optimized Graph Primitives for Parallel and Distributed Platforms](https://ieeexplore.ieee.org/abstract/document/7516027) (IPDPS 2016) by Michael J. Anderson et al.

## Wrappers

* Python wrappers:
    * :star: [pygraphblas](https://github.com/michelp/pygraphblas): a Python wrapper for SuiteSparse:GraphBLAS aiming to provide a Pythonic AP
      * [GraphBLAS Programmability: Python and MATLAB Interfaces](https://github.com/DrTimothyAldenDavis/GraphBLAS/blob/stable/Doc/HPEC20_Python_and_MATLAB.pdf) by Tim Mattson, Michel Pelletier, Tim Davis (preprint)
    * :star: [grblas](https://github.com/metagraph-dev/grblas): a Python wrapper for SuiteSparse:GraphBLAS with a new high-level syntax that provides a 1:1 mapping between the C API and Python
        * This library and all dependencies can be installed with [conda](https://docs.conda.io/projects/conda/en/latest/) for OS X and Linux
    * [PyGB](https://github.com/jessecoleman/gbtl-python-bindings): a Python wrapper for GBTL
* [SuiteSparseGraphBLAS.jl](https://github.com/abhinavmehndiratta/SuiteSparseGraphBLAS.jl): a Julia wrapper for SuiteSparse:GraphBLAS
     * a [fork](https://github.com/cvdlab/SuiteSparseGraphBLAS.jl) aiming to provide a more Julian interface
* [rustgraphblas](https://github.com/fabianmurariu/rustgraphblas): a Rust wrapper
* [graphblas-java-native](https://github.com/fabianmurariu/graphblas-java-native): a Java wrapper
  * [artifact at the Maven Central](https://search.maven.org/search?q=a:graphblas-java-native)
* MATLAB wrapper: built-in for SuiteSparse:GraphBLAS
* [Docker containers on Docker Hub](https://hub.docker.com/r/graphblas/)

See also the [ongoing design of the GraphBLAS C++ API](https://people.eecs.berkeley.edu/~demmel/ma221_Spr20/GraphBLASCppAPI20.pdf).

## Related libraries

* [RedisGraph](https://redislabs.com/redis-enterprise/redis-modules/redis-enterprise-modules/redisgraph/)
    * More pointers [below](#RedisGraph)
* [Graphulo](https://graphulo.mit.edu/) (built for [Apache Accumulo](https://accumulo.apache.org/))
    * More pointers [below](#Graphulo)
* [D4M](http://www.mit.edu/~kepner/D4M/)
    * [Repository](https://github.com/Accla/d4m)
    * [D4M.jl](https://github.com/Accla/D4M.jl): Julia implementation
    * [D4M.py](https://github.com/Accla/D4M.py): Python implementation
* [pggraphblas](https://github.com/michelp/pggraphblas): Postgres extension for using GraphBLAS
* [Combinatorial BLAS (CombBLAS)](https://github.com/PASSIONLab/CombBLAS): "An extensible distributed-memory library offering a small but powerful set of linear algebraic operations specifically targeting graph analytics." _Influences the development of GraphBLAS._
    * Aydın Buluç, John R. Gilbert: [The Combinatorial BLAS: design, implementation, and applications](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.916.6801&rep=rep1&type=pdf), Int. J. High Perform. Comput. Appl. 2011 ([paper entry at the publisher's site](https://journals.sagepub.com/doi/10.1177/1094342011403516)). This paper is referred to as a "strawman proposal" on GraphBLAS.org
    * [Documentation](https://people.eecs.berkeley.edu/~aydin/CombBLAS/html/)
    * [Presentation](https://people.eecs.berkeley.edu/~aydin/talks/CombBLAS_Nov11.pdf)
* Viral B. Shah, Alan Edelman, Stefan Karpinski, Jeff Bezanson, Jeremy Kepner: [Novel algebras for advanced analytics in Julia](https://dspace.mit.edu/handle/1721.1/115964), HPEC 2013
    * [Repository](https://github.com/JuliaComputing/SemiringAlgebra.jl)
* A Hybrid GraphBLAS in C++11: specification, design, implementation, and performance (a work-in-progress distributed C++11 GraphBLAS implementation)
    * [Poster](http://albert-jan.yzelman.net/slides/siam-pp20-poster.pdf) by Albert-Jan Yzelman and W. J. Suijlen

### RedisGraph

* [Deep Dive into RedisGraph](https://www.youtube.com/watch?v=4KS2MRccQX4) (RedisConf 2019) by Roi Lipman
    * [Presentation](https://www.slideshare.net/RedisLabs/redisgraph-internals-roi-lipman)
* [Lower Latency Graph Queries in Cypher with Redis Graph](https://www.youtube.com/watch?v=xnez6tloNSQ) (RedisConf 2018) by Roi Lipman and Tim Davis
    * [GraphBLAS section](https://www.youtube.com/watch?v=xnez6tloNSQ?t=304)
    * [Presentation](https://www.slideshare.net/RedisLabs/redisconf18-lower-latency-graph-queries-in-cypher-with-redis-graph)
* [Evaluating Cypher queries and procedures as algebraic operations within RedisGraph](http://wiki.ldbcouncil.org/pages/viewpage.action?pageId=106233859&preview=/106233859/111706128/LDBC-July-2019.pdf) (12th LDBC TUC, 2019) by Roi Lipman

### Graphulo

* [Graphulo: Graph Analytics in Apache Accumulo](http://accumulosummit.com/2016/program/talks/graphulo/) (Accumulo Summit 2016) by Vijay Gadepally, Timothy Weale, Dylan Hutchison, Jeremy Kepner
* [Interacting with Accumulo and Graphulo using Julia/Python D4M](http://accumulosummit.com/2018/program/talks/accumulo-and-graphulo-using-julia-python-d4m/) (Accumulo Summit 2018) by Lauren Milechin, Hayden Jananthan, Vijay Gadepally, Jeremy Kepner
* [Accumulo and the Convergence of Machine Learning, Big Data, and Supercomputing](http://accumulosummit.com/2017/program/talks/convergence-of-machine-learning-big-data-and-supercomputing/) (Accumulo Summit 2017) by Jeremy Kepner
* [Server-side Sparse Matrix Multiply in the Accumulo Database](http://www.ieee-hpec.org/2015/Final_Presentations/19_Paper862015-08-10-graphulo-tablemult.pdf) (HPEC 2015) by Dylan Hutchison, Jeremy Kepner, Vijay Gadepally, Adam Fuchs
* [Using D4M for rapid prototyping of analytics for Apache Accumulo](http://accumulosummit.com/2015/program/talks/using-d4m-for-rapid-prototyping-of-analytics-for-apache-accumulo/) (Accumulo Summit 2015) by Vijay Gadepally, Lauren Edwards, Jeremy Kepner
* [Graph Analytics expressed in GraphBLAS](http://www.mit.edu/~kepner/Graphulo/141222-GraphuloInGraphBLAS.pptx) (2014) by Jeremy Kepner, Vijay Gadepally, Ben Miller

You can also find many papers, posters, and presentations in the [Accumulo repository](https://github.com/Accla/graphulo/tree/master/docs).

## Events

| year | IPDPS workshop                                              | HPEC                                                       |
| ---- | ----------------------------------------------------------- | ---------------------------------------------------------- |
| 2020 | [GrAPL](https://hpc.pnl.gov/grapl/)                         | [HPEC](http://www.ieee-hpec.org/)                          |
| 2019 | [GrAPL](https://hpc.pnl.gov/grapl/previous/2019/index.html) | [HPEC](http://www.ieee-hpec.org/2019/)                     |
| 2018 | [GABB](http://graphanalysis.org/workshop2018.html)          | [HPEC](http://www.ieee-hpec.org/2018/)                     |
| 2017 | [GABB](http://graphanalysis.org/workshop2017.html)          | [HPEC](http://ieee-hpec.org/2017/techprog2017/sept13.htm)  |
| 2016 | [GABB](http://graphanalysis.org/workshop2016.html)          | [HPEC](http://ieee-hpec.org/2016/techprog2016/sept14.htm)  |
| 2015 | [GABB](http://www.graphanalysis.org/workshop2015.html)      | [HPEC](http://www.ieee-hpec.org/2015/)                     |
| 2014 | [GABB](http://www.graphanalysis.org/workshop2014.html)      | [HPEC](http://www.ieee-hpec.org/2014/copy/agendatext.html) |
| 2013 | −                                                           | [HPEC](http://ieee-hpec.org/2013/agenda.htm)               |

## News, blogs, interviews

* [Blog by Tim Davis](http://aldenmath.com/blog/)
* [GraphBLAS: Building Blocks For High Performance Graph Analytics](https://crd.lbl.gov/news-and-publications/news/2017/graphblas-building-blocks-for-high-performance-graph-analytics/) – Berkeley Lab Researchers Contribute to GraphBLAS and Will Leverage it for Exascale Applications
* [ACM's interview with Tim Davis](https://www.acm.org/articles/people-of-acm/2019/tim-davis)
* [First Person: Tim Davis](https://www.americanscientist.org/article/first-person-tim-davis), American Scientist

## Typesetting

The [`nicematrix`](https://ctan.org/pkg/nicematrix?lang=en) LaTeX package can be used to typeset block matrices.
* [Example TeX code](http://mit.bme.hu/~szarnyas/grb/tricount.tex)

## Related work

* [graphblas-verif](https://github.com/jennalwise/graphblas-verif): Formal verification of the GraphBLAS C API implementation by Tim Davis using Frama-C/WP.
* [LA3: A scalable link-and locality-aware linear algebra-based graph analytics system](http://www.vldb.org/pvldb/vol11/p920-ahmad.pdf) (VLDB 2018) by Yousuf Ahmad et al. 
* [Efficient Distributed Graph Analytics using Triply Compressed Sparse Format](https://people.cs.pitt.edu/~hasanzadeh/files/papers/PID6084671.pdf) (CLUSTER 2019) by Mohammad Hasanzadeh Mofrad et al.
* MAGiQ – a GraphBLAS-based RDF query engine:
  * [A Demonstration of MAGiQ: Matrix Algebra Approach for Solving RDF Graph Queries](http://www.vldb.org/pvldb/vol11/p1978-jamour.pdf) (demo at VLDB 2018) by Fuad Jamour, Ibrahim Abdelaziz, Panos Kalnis
  * [Matrix Algebra Framework for Portable, Scalable and Efficient Query Engines for RDF Graphs](https://dl.acm.org/doi/10.1145/3302424.3303962) (EuroSys 2019) by Fuad Jamour, Ibrahim Abdelaziz, Yuanzhao Chen, Panos Kalnis
  * [Algorithms and Frameworks for Graph Analytics at Scale](https://repository.kaust.edu.sa/bitstream/handle/10754/631280/FuadJamourThesis.pdf?sequence=3) (PhD thesis, 2019) by Fuad Jamour
* [Parallel and Scalable Sparse Basic Linear Algebra Subprograms](https://folk.idi.ntnu.no/weifengl/thesis/phdthesis_liu.pdf) (PhD thesis, 2015) by Weifeng Liu
* [Density-Aware Linear Algebra in a Column-Oriented In-Memory Database System](https://nbn-resolving.org/urn:nbn:de:bsz:14-qucosa-210043) (PhD thesis, 2016) by David Kernert
* Connection of relational joins (join-project, projected join) and sparse matrix multiplication:
  * [A relational approach to the compilation of sparse matrix programs](https://link.springer.com/chapter/10.1007%2FBFb0002751) (Euro-Par 1997) by Vladimir Kotlyar et al.
  * [Faster join-projects and sparse matrix multiplications](https://www.itu.dk/people/pagh/papers/joinproject.pdf) (ICDT 2009) by Rasmus Resen Amossen and Rasmus Pagh
  * [Fast Join Project Query Evaluation using Matrix Multiplication](https://users.cs.duke.edu/~xh102/sigmod2020.pdf) (SIGMOD 2020) by Shaleen Deep et al.
  * [SPORES: Sum-Product Optimization via Relational Equality Saturation for Large Scale Linear Algebra](http://www.vldb.org/pvldb/vol13/p1919-wang.pdf) (VLDB 2020) by Yisu Remy Wang et al.
