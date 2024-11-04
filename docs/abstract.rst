.. _abstract:

Abstract
--------

.. raw:: html

    <hr/>

Matchings and perfect matchings have received considerable attention in graph
theory as well as in other related domains (such as, but not limited to,
algorithms and optimization). There still remain many open problems — such as
`Barnette’s conjecture <https://en.wikipedia.org/wiki/Barnette%27s_conjecture>`_,
`Berge-Fulkerson conjecture <http://garden.irmacs.sfu.ca/op/the_berge_fulkerson_conjecture>`_,
and so on — due to which it continues to remain an active area of research. For
problems pertaining to perfect matchings, it is well-known that it suffices to
solve them for matching covered graphs (that is, those connected graphs wherein
each edge belongs to some perfect matching). The theory of matching covered
graphs, despite its relatively recent emergence, presents an exciting landscape
filled with captivating discoveries, elegant proofs, and unexpected
applications. In the following paragraph, we briefly summarize some of the key
developments in this field without going into the mathematical details.

Kotzig [3]_, in 1959, introduced the notion of canonical partition of a
matching covered graph that uniquely partitions its vertex set into its maximal
barriers. In 1987, László Lovász [5]_ established the uniqueness of the tight
cut decomposition procedure; as per this, every matching covered graph may be
uniquely decomposed into a list of special matching covered graphs called
*bricks* (nonbipartite) and *braces* (bipartite). The key contribution of this
landmark paper was to solve the Matching Lattice Problem. Lovász and Plummer,
in 1975, introduced the well-known ear decomposition of matching covered
graphs; see *Matching Theory* [4]_. This notion of ear decomposition was
further refined to that of an optimal ear decomposition by Carvalho, Lucchesi
and Murty [2]_. Furthermore, in their seminal paper, the same authors [1]_
introduced the dependency relationship in matching covered graphs that is
closely tied with the ear decomposition theory. In 2001, McCuaig [7]_
established a generation method for all braces; analogously, Norine and Thomas
[9]_, in 2007, established a generation method for all bricks. Both of these
generation procedures may be viewed as a synthesis of the ear decomposition and
tight cut decomposition theories, and have found applications in solving some
of the major problems in matching theory — such as Polya’s Permanent Problem
[8]_. All of these results — pertaining to decompositions, generation methods
and related concepts — have played indispensable roles in the advancement of
matching theory, and continue to do so.

It is worth noting that all of the notions discussed above are computable in
poly-time. Despite this, there are no publicly available implementations. It is
for this reason that researchers in this area are at a loss, and are required
to implement parts of this theory by themselves. Currently, in SageMath, a few
existing matching-theoretic algorithms for general graphs have been put within
the module *Undirected graphs* — either under the submodule *Algorithmically
hard stuff* (for instance:
`matching_polynomial() <https://doc.sagemath.org/html/en/reference/graphs/sage/graphs/graph.html#sage.graphs.graph.Graph.matching_polynomial>`_)
or under *Leftovers* (for instance:
`has_perfect_matching() <https://doc.sagemath.org/html/en/reference/graphs/sage/graphs/graph.html#sage.graphs.graph.Graph.has_perfect_matching>`_,
`matching() <https://doc.sagemath.org/html/en/reference/graphs/sage/graphs/graph.html#sage.graphs.graph.Graph.matching>`_,
`is_factor_critical() <https://doc.sagemath.org/html/en/reference/graphs/sage/graphs/graph.html#sage.graphs.graph.Graph.is_factor_critical>`_ and
`perfect_matchings() <https://doc.sagemath.org/html/en/reference/graphs/sage/graphs/graph.html#sage.graphs.graph.Graph.perfect_matchings>`_),
whereas that concerning the bipartite graphs have been put within the module
*Bipartite Graphs* (for instance: matching(), matching_polynomial() and
perfect_matchings()). Ergo, we propose to implement efficient algorithms
pertaining to the results and concepts discussed in the above paragraph in
SageMath, and to make all of these available freely to students, educators as
well as researchers all across the world.

This proposal has been inspired by the book of Lucchesi and Murty — *Perfect
Matchings: a theory of matching covered graphs* [6]_.


.. raw:: html

    <hr/>
    <b> References </b>
    <hr/>

.. [1] M. H. Carvalho, C. L. Lucchesi, and U. S. R. Murty. *Ear decompositions of matching covered
       graphs*. Combinatorica, 19:151–174, 1999.

.. [2] M. H. de Carvalho, C. L. Lucchesi, and U. S. R. Murty. *Optimal ear decompositions of matching
       covered graphs and bases for the matching lattice*. Journal of Combinatorial Theory, Series B,
       76(1):1–14, 2002.

.. [3] A. Kotzig. *Ein beitrag zur theorie der endlichen graphen* i–ii–iii. Mat. Fyz. Casopis, 9:73–91,
       136–159, and 10 (1960) 205–215, 1959.

.. [4] L. Lovász and M. D. Plummer. *Matching Theory*. Number 29 in Annals of Discrete Mathematics.
       Elsevier Science, 1986.

.. [5] László Lovász. *Matching structure and the matching lattice*. Journal of Combinatorial Theory,
       Series B, 43(2):187–222, 1987.

.. [6] Cláudio L. Lucchesi and U.S.R. Murty. *Perfect Matchings: A Theory of Matching Covered Graphs*.
       Algorithms and Computation in Mathematics. Springer Cham, 1 edition, 25 March 2024.

.. [7] W. McCuaig. *Brace generation*. Journal of Graph Theory,
       38:124–169, 2001.

.. [8] William McCuaig. *Pólya’s permanent problem*. The Electronic Journal of Combinatorics,
       11(1):R79, 2004.

.. [9] S. Norine and R. Thomas. *Generating bricks*. Journal of Combinatorial Theory, Series B,
       97:769–817, 2007.


.. raw:: html

    <hr/>