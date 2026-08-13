\documentclass[aspectratio=169,11pt]{beamer}

% A clean, original-looking Beamer design
\usetheme{Boadilla}
\usecolortheme{dove}
\setbeamertemplate{navigation symbols}{}
\setbeamertemplate{footline}{
  \leavevmode%
  \hbox{\begin{beamercolorbox}[wd=.78\paperwidth,ht=2.5ex,dp=1ex,leftskip=.5cm]{author in head/foot}
    Haripriya H \hfill Mathematics for Computing
  \end{beamercolorbox}%
  \begin{beamercolorbox}[wd=.22\paperwidth,ht=2.5ex,dp=1ex,center]{date in head/foot}
    \insertframenumber/\inserttotalframenumber
  \end{beamercolorbox}}%
}
\definecolor{accent}{RGB}{38,82,120}
\setbeamercolor{structure}{fg=accent}
\setbeamercolor{frametitle}{fg=accent}
\setbeamercolor{title}{fg=accent}

\usepackage{amsmath,amssymb,mathtools}
\usepackage{tikz}
\usetikzlibrary{positioning,arrows.meta}
\usepackage{booktabs}

\title[Mathematics for Computing]{Mathematics for Computing}
\subtitle{Assignment 1}
\author{Haripriya H}
\institute{M.Tech in Computer Science and Engineering\\
Specialization in Data Science and Artificial Intelligence\\
Department of Computer Science, CUSAT}
\date{August 13, 2026}

\begin{document}

\begin{frame}
  \titlepage
\end{frame}

\begin{frame}{Roadmap}
\tableofcontents
\end{frame}

\section{Sets}

\begin{frame}{What is a Set?}
\begin{block}{Definition}
A set is a well-defined, unordered collection of distinct objects. The objects are called
\emph{elements} of the set.
\end{block}

\begin{exampleblock}{Computing example}
Let
\[
D=\{\text{Python},\text{Java},\text{SQL},\text{C}\}.
\]
Here, each programming language occurs as one distinct element.
\end{exampleblock}

\begin{itemize}
  \item Order does not change a set.
  \item Repeated elements are written only once.
\end{itemize}
\end{frame}

\begin{frame}{Cardinality of a Set}
The \textbf{cardinality} of a set is its number of distinct elements and is
written as $|A|$.

\begin{exampleblock}{Example}
Consider the set of binary digits:
\[
B=\{0,1\}.
\]
Therefore,
\[
|B|=2.
\]
\end{exampleblock}

\begin{alertblock}{Important}
If an element is repeated in a description of a set, it is still counted only
once.
\end{alertblock}
\end{frame}

\section{Types of Sets}

\begin{frame}{1. Finite Set}
A finite set contains a limited number of distinct elements.

\begin{exampleblock}{Data Science example}
Suppose a classification model uses four labels:
\[
C=\{\text{cat},\text{dog},\text{bird},\text{fish}\}.
\]
Then $|C|=4$, so $C$ is finite.
\end{exampleblock}

\[
C=\{x\mid x\text{ is one of the four chosen class labels}\}.
\]
\end{frame}

\begin{frame}{2. Infinite Set}
An infinite set has no finite number of elements.

\begin{exampleblock}{Computing example}
The set of possible real-valued weights of a machine-learning model can be
represented by
\[
W=\{x\mid x\in\mathbb{R}\}.
\]
Since there are infinitely many real numbers, $W$ is infinite.
\end{exampleblock}
\end{frame}

\begin{frame}{3. Null (Empty) Set}
An empty set contains no elements. It is denoted by $\varnothing$.

\begin{exampleblock}{AI example}
Suppose a search system is asked to return products satisfying an impossible
combination of filters. If no product satisfies the query,
\[
R=\varnothing.
\]
Thus $R$ is an empty set.
\end{exampleblock}
\end{frame}

\begin{frame}{4. Countable Set}
A set is countable when its elements can be listed one by one.

\begin{exampleblock}{Computing example}
The first six HTTP status codes in a selected list can be written as
\[
S=\{200,201,204,301,400,404\}.
\]
They can be individually indexed, so $S$ is countable.
\end{exampleblock}

\[
S=\{x\mid x\text{ is one of the six selected status codes}\}.
\]
\end{frame}

\begin{frame}{5. Power Set}
The power set $\mathcal P(A)$ is the set of all subsets of $A$.

\begin{exampleblock}{Example}
Let
\[
A=\{\text{CPU},\text{GPU},\text{RAM}\}.
\]
Since $|A|=3$,
\[
|\mathcal P(A)|=2^3=8.
\]
\end{exampleblock}

The power set contains $\varnothing$, the three one-element subsets, the
three two-element subsets, and $A$ itself.
\end{frame}

\begin{frame}{6. Subset}
If every element of $A$ is also an element of $B$, then
\[
A\subseteq B.
\]

\begin{exampleblock}{Data example}
Let
\[
A=\{\text{mean},\text{median}\},\qquad
B=\{\text{mean},\text{median},\text{mode}\}.
\]
Every element of $A$ occurs in $B$, hence
\[
A\subseteq B.
\]
\end{exampleblock}
\end{frame}

\begin{frame}{7. Equal Sets}
Two sets are equal when they contain exactly the same elements.

\begin{exampleblock}{Example}
\[
A=\{\text{red},\text{green},\text{blue}\},\qquad
B=\{\text{blue},\text{red},\text{green}\}.
\]
The order is different, but the elements are identical. Therefore
\[
A=B.
\]
\end{exampleblock}

\[
A=B\iff \forall x\;(x\in A\Leftrightarrow x\in B).
\]
\end{frame}

\begin{frame}{8. Equivalent Sets}
Two sets are equivalent if they have the same cardinality.

\begin{exampleblock}{Example}
Let
\[
A=\{10,20,30\},\qquad
B=\{\text{HTML},\text{CSS},\text{JavaScript}\}.
\]
Both sets have three elements, so
\[
|A|=|B|=3.
\]
Hence they are equivalent sets.
\end{exampleblock}
\end{frame}

\begin{frame}{9. Superset}
If $A\subseteq B$, then $B$ is a superset of $A$, written as
\[
B\supseteq A.
\]

\begin{exampleblock}{Example}
Let
\[
A=\{\text{train},\text{test}\},\qquad
B=\{\text{train},\text{validation},\text{test}\}.
\]
Then $A\subseteq B$, so
\[
B\supseteq A.
\]
\end{exampleblock}
\end{frame}

\begin{frame}{10. Singleton Set}
A singleton set contains exactly one element.

\begin{exampleblock}{AI example}
If a binary classifier produces one selected class for a particular record,
the set of that record's predicted classes can be
\[
P=\{\text{spam}\}.
\]
Thus,
\[
|P|=1,
\]
so $P$ is a singleton set.
\end{exampleblock}
\end{frame}

\section{Set Builder Form}

\begin{frame}{Set-Builder Form: Idea}
Set-builder notation describes a set by stating a property that its elements
must satisfy.

\[
A=\{x\mid P(x)\}.
\]

\begin{exampleblock}{Example}
The positive even integers below 12 are
\[
A=\{2,4,6,8,10\}.
\]
In set-builder form:
\[
A=\{x\in\mathbb N\mid x\text{ is even and }x<12\}.
\]
\end{exampleblock}
\end{frame}

\begin{frame}{Set-Builder Examples I}
\textbf{Q1. Multiples of 7 not exceeding 42}
\[
A=\{7,14,21,28,35,42\}
\]
\[
A=\{x\mid x=7n,\;1\le n\le6,\;n\in\mathbb N\}.
\]

\medskip
\textbf{Q2. Perfect squares from 1 through 81}
\[
B=\{1,4,9,16,25,36,49,64,81\}
\]
\[
B=\{x\mid x=n^2,\;1\le n\le9,\;n\in\mathbb N\}.
\]
\end{frame}

\begin{frame}{Set-Builder Examples II}
\textbf{Q3. Integers between $-5$ and $8$}
\[
C=\{x\mid x\in\mathbb Z,\;-5\le x\le8\}.
\]

\medskip
\textbf{Q4. Odd natural numbers below 20}
\[
D=\{1,3,5,7,9,11,13,15,17,19\}
\]
\[
D=\{x\mid x=2n+1,\;0\le n\le9,\;n\in\mathbb N_0\}.
\]
\end{frame}

\begin{frame}{Set-Builder Examples III}
\textbf{Q5. Positive integers divisible by 4}
\[
E=\{4,8,12,16,20,\ldots\}
\]
\[
E=\{x\in\mathbb N\mid 4\mid x\}.
\]

\medskip
\textbf{Q6. Numbers leaving remainder 2 when divided by 5}
\[
F=\{2,7,12,17,22,\ldots\}
\]
\[
F=\{x\mid x=5n+2,\;n\in\mathbb N_0\}.
\]
\end{frame}

\begin{frame}{Set-Builder Examples IV}
\textbf{Q7. Factors of 36}
\[
G=\{1,2,3,4,6,9,12,18,36\}
\]
\[
G=\{x\in\mathbb N\mid x\mid36\}.
\]

\medskip
\textbf{Q8. Ordered pairs with sum 10}
\[
H=\{(1,9),(2,8),(3,7),(4,6),(5,5),\ldots\}
\]
\[
H=\{(x,y)\in\mathbb N^2\mid x+y=10\}.
\]
\end{frame}

\begin{frame}{Set-Builder Examples V}
\textbf{Q9. Multiples of 9 below 60}
\[
I=\{9,18,27,36,45,54\}
\]
\[
I=\{x\mid x=9n,\;1\le n\le6,\;n\in\mathbb N\}.
\]

\medskip
\textbf{Q10. Integers whose absolute value is at most 3}
\[
J=\{-3,-2,-1,0,1,2,3\}
\]
\[
J=\{x\in\mathbb Z\mid |x|\le3\}.
\]
\end{frame}

\section{Inclusion--Exclusion}

\begin{frame}{Inclusion--Exclusion Principle}
The Inclusion--Exclusion Principle counts distinct elements in a union while
correcting for overlap.

For two sets:
\[
|A\cup B|=|A|+|B|-|A\cap B|.
\]

For three sets:
\[
\begin{aligned}
|A\cup B\cup C|
={}&|A|+|B|+|C|\\
&-|A\cap B|-|A\cap C|-|B\cap C|\\
&+|A\cap B\cap C|.
\end{aligned}
\]
\end{frame}

\begin{frame}{Inclusion--Exclusion: Computing Example}
In a class of 50 students:
\begin{itemize}
\item 28 know Python,
\item 22 know Java,
\item 12 know both.
\end{itemize}

The number who know at least one of the two languages is
\[
|P\cup J|=28+22-12=38.
\]

So \textbf{38 students} know Python or Java (or both).
\end{frame}

\begin{frame}{General Inclusion--Exclusion}
For finite sets $A_1,\ldots,A_n$,
\[
\left|\bigcup_{i=1}^{n}A_i\right|
=
\sum_i|A_i|
-\sum_{i<j}|A_i\cap A_j|
+\sum_{i<j<k}|A_i\cap A_j\cap A_k|
-\cdots.
\]

\begin{block}{Pattern}
Add individual sizes, subtract pairwise overlaps, add triple overlaps, and
continue with alternating signs.
\end{block}
\end{frame}

\section{Partially Ordered Sets}

\begin{frame}{Partially Ordered Sets (Posets)}
A partially ordered set is a set together with a relation satisfying:

\begin{enumerate}
\item \textbf{Reflexive:} $a\le a$.
\item \textbf{Antisymmetric:} $a\le b$ and $b\le a$ imply $a=b$.
\item \textbf{Transitive:} $a\le b$ and $b\le c$ imply $a\le c$.
\end{enumerate}

A poset is commonly written as $(P,\le)$.
\end{frame}

\begin{frame}{Poset Example: Divisibility}
Let
\[
P=\{1,2,4,8\}
\]
and define
\[
a\preceq b\iff a\mid b.
\]

For example:
\[
1\mid2,\qquad 2\mid4,\qquad 4\mid8,\qquad 1\mid8.
\]

This relation is reflexive, antisymmetric, and transitive, so $(P,\preceq)$
is a poset.
\end{frame}

\begin{frame}{Hasse Diagram: Divisibility Poset}
\centering
\begin{tikzpicture}[node distance=1.5cm, every node/.style={circle,draw,minimum size=8mm}]
\node (1) {$1$};
\node (2) [above=of 1] {$2$};
\node (4) [above=of 2] {$4$};
\node (8) [above=of 4] {$8$};
\draw (1)--(2)--(4)--(8);
\end{tikzpicture}

\medskip
Only the essential cover relations are drawn. Transitive edges such as
$1\mid4$ and $1\mid8$ are omitted.
\end{frame}

\begin{frame}{Hasse Diagram: Subset Poset}
Consider
\[
P=\{\varnothing,\{a\},\{b\},\{a,b\}\}
\]
ordered by $\subseteq$.

\centering
\begin{tikzpicture}[node distance=1.35cm]
\node (top) {$\{a,b\}$};
\node (a) [below left=of top] {$\{a\}$};
\node (b) [below right=of top] {$\{b\}$};
\node (bot) [below=of top,yshift=-1.0cm] {$\varnothing$};
\draw (top)--(a);
\draw (top)--(b);
\draw (a)--(bot);
\draw (b)--(bot);
\end{tikzpicture}
\end{frame}

\begin{frame}{Summary}
\begin{itemize}
  \item Sets provide a basic way to represent collections of objects.
  \item Cardinality measures the number of distinct elements.
  \item Set-builder notation describes elements through properties.
  \item Inclusion--Exclusion corrects double counting in unions.
  \item Posets model relations that are reflexive, antisymmetric, and
        transitive.
  \item Hasse diagrams give a compact visual representation of finite posets.
\end{itemize}

\begin{block}{Key idea}
These concepts are useful for organizing data, describing relationships,
and reasoning about discrete structures in computing.
\end{block}
\end{frame}

\begin{frame}
\centering
{\Huge Thank You}\\[1em]
{\large Haripriya H}
\end{frame}

\end{document}
