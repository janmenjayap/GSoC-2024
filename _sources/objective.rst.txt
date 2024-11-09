.. _objective:

Objective
---------

The proposal submitted and accepted for the Google Summer of Code (GSoC) 2024 at SageMath can be found here: Link.

In the initial proposal, all methods were presented as independent, standalone functions. However, after discussions
with my mentor, Prof. David Coudert, we concluded that a more structured approach would be beneficial. Specifically,
we decided to create a dedicated class, :class:`MatchingCoveredGraph`, which would inherit from :class:`Graph`
(itself inheriting from :class:`GenericGraph`). This class would encapsulate the methods as member functions.

This shift to a class-based approach requires overwriting some methods from both :class:`Graph` and :class:`GenericGraph`
(that are new to the proposal). The purpose of these overrides is twofold:

    * to simplify certain operations in the context of time complexity, and
    * to ensure that the resulting graph is always matching covered, that is, an instance of the class :class:`MatchingCoveredGraph`.

This ensures that any transformations or operations performed on a matching covered graph retain its defining properties.

The primary objective of this project is to implement and formalize the handling of matching covered graphs within SageMath
by developing the :class:`MatchingCoveredGraph` class and refining relevant methods to support these structures. In addition
to the core objectives outlined above, there are several supplementary targets associated with this project. A comprehensive
and detailed overview of the objectives is as follows:

1. Implementing methods for generating following families of matching covered graphs:

    - Möbius ladder graph
    - Staircase graph
    - Biwheel graph
    - Truncated biwheel graph

2. Implementing methods for generating some small graphs/ digraphs:

    - Bicorn graph
    - Tricorn graph
    - Murty graph
    - Cubeplex graph
    - Twinplex graph
    - KohTindell digraph

3. Implementing methods pertaining to matching:

    .. raw:: html

        <div style="overflow-x: auto; max-width: 100%;">
            <table style="width: 100%; border-collapse: collapse; font-family: Georgia, serif; margin-bottom: 10px;">
                <tbody>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_matching_covered()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the graph is matching covered.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_bicritical()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the graph is bicritical.</td>
                    </tr>
                </tbody>
            </table>
        </div>

4. Introducing the class :class:`MatchingCoveredGraph` and implementing methods
   concerning matching covered graph:

    * Class related methods:

    .. raw:: html

        <div style="overflow-x: auto; max-width: 100%;">
            <table style="width: 100%; border-collapse: collapse; font-family: Georgia, serif; margin-top: 10px; margin-bottom: 10px;">
                <tbody>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>__init__()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the graph is matching covered.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>__hash__()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Compute a hash for the immutable matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>__repr__()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a string representation of the matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>_subgraph_by_adding()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the matching covered subgraph containing the given vertices and edges.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>_subgraph_by_deleting()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the matching covered subgraph containing the provided vertices and edges.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>_upgrade_from_graph()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Upgrade the given graph to a matching covered graph.</td>
                    </tr>
                </tbody>
            </table>
        </div>

    * Methods concerning barriers and canonical partition:

    .. raw:: html

        <div style="overflow-x: auto; max-width: 100%;">
            <table style="width: 100%; border-collapse: collapse; font-family: Georgia, serif; margin-top: 10px; margin-bottom: 10px;">
                <tbody>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>canonical_partition()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the canonical partition.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>maximal_barrier()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the (unique) maximal barrier containing the vertex.</td>
                    </tr>
                </tbody>
            </table>
        </div>

    * Methods concerning bricks, braces and tight cut decomposition:

    .. raw:: html

        <div style="overflow-x: auto; max-width: 100%;">
            <table style="width: 100%; border-collapse: collapse; font-family: Georgia, serif; margin-top: 10px; margin-bottom: 10px;">
                <tbody>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>bricks_and_braces()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the list of (the underlying simple) bricks and braces.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_brace()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the matching covered graph is a brace.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_brick()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the matching covered graph is a brick.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>number_of_braces()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the number of braces.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>number_of_bricks()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the number of bricks.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>number_of_petersen_bricks()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the number of Petersen bricks.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>tight_cut_decomposition()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a tight cut decomposition.</td>
                    </tr>
                </tbody>
            </table>
        </div>

    * Methods concerning removability and ear decomposition:

    .. raw:: html

        <div style="overflow-x: auto; max-width: 100%;">
            <table style="width: 100%; border-collapse: collapse; font-family: Georgia, serif; margin-top: 10px; margin-bottom: 10px;">
                <tbody>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>add_ear()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Add an ear to the matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>bisubdivide_edge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">bisubdivide an edge <i>k</i> times.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>bisubdivide_edge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">bisubdivide <i>k</i> times edges from an iterable container.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>ear_decomposition()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a matching covered ear decomposition computed efficiently.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_removable_double_ear()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the pair of ears form a removable double ear.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_removable_doubleton()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the pair of edges constitute a removable doubleton.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_removable_ear()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the ear is removable.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_removable_edge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the edge is removable.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>optimal_ear_decomposition()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return an optimal ear decomposition.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>removable_double_ears()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a list of removable double ears.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>removable_doubletons()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a list of removable doubletons.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>removable_ears()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a list of removable ears.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>removable_edegs()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return an <code><b>EdgesView</b></code> of removable edges.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>retract()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Compute the retract of the matching covered graph.</td>
                    </tr>
                </tbody>
            </table>
        </div>

    * Methods for generating bricks and braces:

    .. raw:: html

        <div style="overflow-x: auto; max-width: 100%;">
            <table style="width: 100%; border-collapse: collapse; font-family: Georgia, serif; margin-top: 10px; margin-bottom: 10px;">
                <tbody>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>brace_generation_sequence()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a McCuaig brace generation sequence of the (provided) brace.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>brick_generation_sequence()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a Norine-Thomas brick generation sequence of the (provided) brick.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_mccuaig_brace()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the brace is a McCuaig brace.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_norine_thomas_brick()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the brick is a Norine-Thomas brick.</td>
                    </tr>
                </tbody>
            </table>
        </div>

    * Overwritten methods:

    .. raw:: html

        <div style="overflow-x: auto; max-width: 100%;">
            <table style="width: 100%; border-collapse: collapse; font-family: Georgia, serif; margin-top: 10px; margin-bottom: 10px;">
                <tbody>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>add_clique()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Add a clique to the graph with the provided vertices.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>add_cycle()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Add a cycle to the graph with the provided vertices.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>add_edge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Add an edge from vertex <code>u</code> to vertex <code>v</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>add_edges()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Add edges from an iterable container.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>add_vertex()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Add a vertex to the (matching covered) graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>add_vertices()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Add vertices from an iterable container of vertices.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>allow_loops()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Change whether loops are allowed in (matching covered) graphs.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>allows_loops()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return whether loops are permitted in (matching covered) graphs.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>cartesian_product()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the cartesian product of <code>self</code> and <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>clear()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Make the graph empty removing all associated informations.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>complement()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the complement of the graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>contract_edge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Contract an edge from <code>u</code> to <code>v</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>contract_edges()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Contract edges from an iterable container.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>degree_constrained_subgraph()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a degree-constrained matching covered subgraph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>delete_edge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Delete the edge from <code>u</code> to <code>v</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>delete_edges()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Delete edges from an iterable container.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>delete_multiedge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Delete all edges from <code>u</code> to <code>v</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>delete_multiedge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Delete all edges from <code>u</code> to <code>v</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>delete_vertices()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Delete specified vertices form <code>self</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>disjoint_union()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the disjoint union of <code>self</code> and <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>disjunctive_product()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the disjunctive product of <code>self</code> and <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>has_loops()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return whether there are loops in the matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>has_perfect_matching()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the graph has a perfect matching.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_biconnected()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the matching covered graph is biconnected.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_block_graph()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the matching covered graph is a block graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_cograph()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the matching covered graph is cograph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_forest()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the matching covered graph is a forest.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_matching_covered()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check if the graph is matching covered.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_path()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the graph is a path.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_subgraph()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the matching covered graph is a subgraph of <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>is_tree()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Check whether the matching covered graph is a tree.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>join()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the join of <code>self</code> and <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>lexicographic_product()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the lexicographic product of <code>self</code> and <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>load_afile()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Load the matching covered graph specified in the given file into the current object.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>loop_edges()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a list of all loops in the matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>loop_vertices()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a list of vertices with loops.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>merge_vertices()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Merge vertices.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>number_of_loops()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the number of edges that are loops.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>random_subgraph()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a random matching covered subgraph containing each vertex with probability <code>p</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>remove_loops()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Remove loops on vertices in <code>vertices</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>save_afile()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Save the graph to file in alist format.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>strong_product()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the strong product of <code>self</code> and <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>subdivide_edge()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Subdivide an edge <code>k</code> times.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>subdivide_edges()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Subdivide <code>k</code> times edges from an iterable container.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>subgraph()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the matching covered subgraph containing the given vertices and edges.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>subgraph_search()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a copy of (matching covered) <code>G</code> in <code>self</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>subgraph_search_count()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the number of labelled occurrences of matching covered <code>G</code> in <code>self</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>subgraph_search_iterator()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return an iterator over the labelled copies of (matching covered) <code>G</code> in <code>self</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>tensor_product()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the tensor product of <code>self</code> and <code>other</code>.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>to_undirected()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return an undirected Graph instance of the matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>transitive_closure()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the transitive closure of the matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>transitive_reduction()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return a transitive reduction of the matching covered graph.</td>
                    </tr>
                    <tr>
                        <td style="width: 38%; padding: 10px; border: 2px solid #000; box-sizing: border-box;"><code>union()</code></td>
                        <td style="width: 62%; padding: 10px; border: 2px solid #000; box-sizing: border-box;">Return the union of <code>self</code> and <code>other</code>.</td>
                    </tr>
                </tbody>
            </table>
        </div>

5. Implementing the Micali-Vazirani algorithm for finding a perfect matching
   in an undirected unweighted graph in :math:`\mathcal{O}(|E| \cdot \sqrt{|V|})`