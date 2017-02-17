第二章 DOT 语言
==============================================================================

2.1 图(graph|digraph)的定义
------------------------------------------------------------------------------

.. code-block:: none
    :linenos:
    :caption: Definition of Graph

    graph : [*strict*] (*graph* | *digraph*) [ID] '{' stmt_list '}'

DOT 语言内定义图，主要有三部分：图类型的声明、图的名称和图的具体内容。

:code:`[strict] (graph | digraph)` 是对图类型的定义， :code:`graph` 用于定义一\
般由点和线段组成的无向图，而 :code:`digraph` 则用于定义有向图。  :code:`strict`
是可选的，用于限制是否启用严格的语法。关于严格的语法，会在后续讲到，一般不需要\
声明 :code:`strict` 。

:code:`[ID]` 是对图名称的声明，一般由描述该图的名称的英文表示。

:code:`'{' stmt_list '}'` 是图的具体内容，由一段被英文花括号包裹的语句列表组\
成。语句列表的定义如下：

2.2 语句(stmt)的定义
------------------------------------------------------------------------------

.. code-block:: none
    :linenos:
    :caption: Definition of Statement List

    stmt_list : [ stmt [';'] stmt_list ]

上述的定义是递归定义，简单的理解就是 :code:`stmt_list` 是由多个 :code:`stmt`
组成的，多个 :code:`stmt` 之间使用英文分号分隔。

.. code-block:: none
    :linenos:
    :caption: Definition of Statement

    stmt : node_stmt | edge_stmt | attr_stmt | ID '=' ID | subgraph

2.2.1 属性语句(attr_stmt)的定义
..............................................................................

.. code-block:: none
    :linenos:
    :caption: Definition of Attribute Statement

    attr_stmt : (*graph* | *node* | *edge*) attr_list
    edge_stmt : (node_id | subgraph) edgeRHS [ attr_list ]
    node_stmt : node_id [ attr_list ]



