<!DOCTYPE html>
<html lang="" xml:lang="">
<head>

  <meta charset="utf-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <title>Nonparametric Smoothing</title>
  <meta name="description" content="Nonparametric Smoothing" />
  <meta name="generator" content="bookdown 0.44 and GitBook 2.6.7" />

  <meta property="og:title" content="Nonparametric Smoothing" />
  <meta property="og:type" content="book" />
  
  
  

  <meta name="twitter:card" content="summary" />
  <meta name="twitter:title" content="Nonparametric Smoothing" />
  
  
  

<meta name="author" content="David P. Hofmeyr" />



  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="apple-mobile-web-app-capable" content="yes" />
  <meta name="apple-mobile-web-app-status-bar-style" content="black" />
  
  


<script src="libs/jquery-3.6.0/jquery-3.6.0.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/fuse.js@6.4.6/dist/fuse.min.js"></script>
<link href="libs/gitbook-2.6.7/css/style.css" rel="stylesheet" />
<link href="libs/gitbook-2.6.7/css/plugin-table.css" rel="stylesheet" />
<link href="libs/gitbook-2.6.7/css/plugin-bookdown.css" rel="stylesheet" />
<link href="libs/gitbook-2.6.7/css/plugin-highlight.css" rel="stylesheet" />
<link href="libs/gitbook-2.6.7/css/plugin-search.css" rel="stylesheet" />
<link href="libs/gitbook-2.6.7/css/plugin-fontsettings.css" rel="stylesheet" />
<link href="libs/gitbook-2.6.7/css/plugin-clipboard.css" rel="stylesheet" />








<link href="libs/anchor-sections-1.1.0/anchor-sections.css" rel="stylesheet" />
<link href="libs/anchor-sections-1.1.0/anchor-sections-hash.css" rel="stylesheet" />
<script src="libs/anchor-sections-1.1.0/anchor-sections.js"></script>


<style type="text/css">
pre > code.sourceCode { white-space: pre; position: relative; }
pre > code.sourceCode > span { line-height: 1.25; }
pre > code.sourceCode > span:empty { height: 1.2em; }
.sourceCode { overflow: visible; }
code.sourceCode > span { color: inherit; text-decoration: inherit; }
pre.sourceCode { margin: 0; }
@media screen {
div.sourceCode { overflow: auto; }
}
@media print {
pre > code.sourceCode { white-space: pre-wrap; }
pre > code.sourceCode > span { display: inline-block; text-indent: -5em; padding-left: 5em; }
}
pre.numberSource code
  { counter-reset: source-line 0; }
pre.numberSource code > span
  { position: relative; left: -4em; counter-increment: source-line; }
pre.numberSource code > span > a:first-child::before
  { content: counter(source-line);
    position: relative; left: -1em; text-align: right; vertical-align: baseline;
    border: none; display: inline-block;
    -webkit-touch-callout: none; -webkit-user-select: none;
    -khtml-user-select: none; -moz-user-select: none;
    -ms-user-select: none; user-select: none;
    padding: 0 4px; width: 4em;
    color: #aaaaaa;
  }
pre.numberSource { margin-left: 3em; border-left: 1px solid #aaaaaa;  padding-left: 4px; }
div.sourceCode
  {   }
@media screen {
pre > code.sourceCode > span > a:first-child::before { text-decoration: underline; }
}
code span.al { color: #ff0000; font-weight: bold; } /* Alert */
code span.an { color: #60a0b0; font-weight: bold; font-style: italic; } /* Annotation */
code span.at { color: #7d9029; } /* Attribute */
code span.bn { color: #40a070; } /* BaseN */
code span.bu { color: #008000; } /* BuiltIn */
code span.cf { color: #007020; font-weight: bold; } /* ControlFlow */
code span.ch { color: #4070a0; } /* Char */
code span.cn { color: #880000; } /* Constant */
code span.co { color: #60a0b0; font-style: italic; } /* Comment */
code span.cv { color: #60a0b0; font-weight: bold; font-style: italic; } /* CommentVar */
code span.do { color: #ba2121; font-style: italic; } /* Documentation */
code span.dt { color: #902000; } /* DataType */
code span.dv { color: #40a070; } /* DecVal */
code span.er { color: #ff0000; font-weight: bold; } /* Error */
code span.ex { } /* Extension */
code span.fl { color: #40a070; } /* Float */
code span.fu { color: #06287e; } /* Function */
code span.im { color: #008000; font-weight: bold; } /* Import */
code span.in { color: #60a0b0; font-weight: bold; font-style: italic; } /* Information */
code span.kw { color: #007020; font-weight: bold; } /* Keyword */
code span.op { color: #666666; } /* Operator */
code span.ot { color: #007020; } /* Other */
code span.pp { color: #bc7a00; } /* Preprocessor */
code span.sc { color: #4070a0; } /* SpecialChar */
code span.ss { color: #bb6688; } /* SpecialString */
code span.st { color: #4070a0; } /* String */
code span.va { color: #19177c; } /* Variable */
code span.vs { color: #4070a0; } /* VerbatimString */
code span.wa { color: #60a0b0; font-weight: bold; font-style: italic; } /* Warning */
</style>

<style type="text/css">
  
  div.hanging-indent{margin-left: 1.5em; text-indent: -1.5em;}
</style>

</head>

<body>



  <div class="book without-animation with-summary font-size-2 font-family-1" data-basepath=".">

    <div class="book-summary">
      <nav role="navigation">

<ul class="summary">
<li class="chapter" data-level="1" data-path=""><a href="#nonparametric-smoothing"><i class="fa fa-check"></i><b>1</b> Nonparametric Smoothing</a>
<ul>
<li class="chapter" data-level="1.1" data-path=""><a href="#smoothing-as-local-averaging"><i class="fa fa-check"></i><b>1.1</b> Smoothing as Local Averaging</a></li>
<li class="chapter" data-level="1.2" data-path=""><a href="#decision-trees"><i class="fa fa-check"></i><b>1.2</b> Decision Trees</a></li>
</ul></li>
</ul>

      </nav>
    </div>

    <div class="book-body">
      <div class="body-inner">
        <div class="book-header" role="navigation">
          <h1>
            <i class="fa fa-circle-o-notch fa-spin"></i><a href="./">Nonparametric Smoothing</a>
          </h1>
        </div>

        <div class="page-wrapper" tabindex="-1" role="main">
          <div class="page-inner">

            <section class="normal" id="section-">
<div id="header">
<h1 class="title">Nonparametric Smoothing</h1>
<p class="author"><em>David P. Hofmeyr</em></p>
</div>
<div id="nonparametric-smoothing" class="section level1 hasAnchor" number="1">
<h1><span class="header-section-number">1</span> Nonparametric Smoothing<a href="#nonparametric-smoothing" class="anchor-section" aria-label="Anchor link to header"></a></h1>
<p>So far in all the models we have investigated there has been (at least implicitly) some <em>parameterised</em> structure. In the (generalised) linear models the regression coefficients and the distribution family used to model the response fully characterised the model(s). When we looked at basis expansions, even when we applied the kernel trick to bypass many of the calculations, within the feature space there was still the implicit setting of a set of optimal coefficients for the basis functions.</p>
<p>In this chapter we look at an alternative way of fitting models using what is known as <em>nonparametric smoothing</em>. We then go on to look at a very important group of models known as <em>Decision Trees</em> (DTs), which may be seen as combining the optimisation approach used in parametric models with the local averaging approach of nonparametric smoothing. DTs are highly nonlinear models yet despite this they can be highly interpretable. In addition DTs are by far the most popular models used within <em>ensemble</em> predictive models, which we cover in the next chapter.</p>
<div id="smoothing-as-local-averaging" class="section level2 hasAnchor" number="1.1">
<h2><span class="header-section-number">1.1</span> Smoothing as Local Averaging<a href="#smoothing-as-local-averaging" class="anchor-section" aria-label="Anchor link to header"></a></h2>
<p>The appropriateness of estimating a function for prediction using a “local average” is most intuitively communicated from the point of view of regression. Recall that in the standard regression setting we have <span class="math display">\[
Y = g^*(X) + \epsilon,
\]</span> where the residual, <span class="math inline">\(\epsilon\)</span>, has mean zero.</p>
<div id="nearest-neighbours" class="section level3 hasAnchor" number="1.1.1">
<h3><span class="header-section-number">1.1.1</span> Nearest Neighbours<a href="#nearest-neighbours" class="anchor-section" aria-label="Anchor link to header"></a></h3>
<div id="model-selection-for-knn" class="section level4 hasAnchor" number="1.1.1.1">
<h4><span class="header-section-number">1.1.1.1</span> Model Selection for <em>k</em>NN<a href="#model-selection-for-knn" class="anchor-section" aria-label="Anchor link to header"></a></h4>
</div>
</div>
</div>
<div id="decision-trees" class="section level2 hasAnchor" number="1.2">
<h2><span class="header-section-number">1.2</span> Decision Trees<a href="#decision-trees" class="anchor-section" aria-label="Anchor link to header"></a></h2>
<p>Decision trees also use the idea of a “local average” in order to fit predictive models, however instead of using a fixed “smoothing parameter” (like the <span class="math inline">\(k\)</span> in <span class="math inline">\(k\)</span>NN), they split up the input space into non-overlapping regions in a semi-optimal way; using the training data in order to choose how the splits are determined. They then use the averages from the training data in each of these regions in order to make predictions.</p>
<ul>
<li>It is certainly possible to have more complex models within each of the regions than just choosing the average value, but this is beyond the scope of the course</li>
</ul>
<p>The reason the models are referred to as decision <em>trees</em>, is that the partitioning of the covariate (input) space can be described in relation to a tree in the <em>graph theory</em> sense (don’t worry, you don’t have to know anything about graph theory). We can also think of them as trees in that, starting from a “root” <em>node</em>, observations are subjected to a rule/decision which results in a “branching” (splitting the observations based on the outcome of the rule/decision), after which the observations face another rule/decision which leads to further “branching”, and a further division of the input space, etc.</p>
<p>The following figure (taken from <em>Introduction to Statistical Learning</em>, James et al.) shows (left) a division of the two-dimensional space in <span class="math inline">\(X_1\)</span> and <span class="math inline">\(X_2\)</span> into five non-overlapping rectangular regions; (middle) a pictoral representation of the decisions/rules which lead to this partition (like an upside-down tree, with the root node at the top and the branches heading downwards); (right) the corresponding fitted function where the vertical direction shows the values the function assumes in each of the five regions.</p>
<p><img src="./figures/isl_cart.png" /></p>
<ul>
<li>If you choose a pair of values for <span class="math inline">\(X_1\)</span> and <span class="math inline">\(X_2\)</span> and then apply the rules in the tree in the middle figure above (starting from the top), following the left “branch” if the result of applying the rule is true and the right “branch” if it is false, until you reach one of the terminal nodes (called <em>leaves</em>), you will see that the tree representation agrees with the “flat” representation of the different regions in the left figure.</li>
</ul>
<p>Notice that the rectangular regions into which a decision tree partitions the input space have their sides parallel with the variable axes. The reasons for this, as opposed to allowing diagonal splits, are (i) it is much more computationally efficient to fit trees in this way even if it may not lead to as good a fit to the data and (ii) the interpretation of the outputs of decision trees is made far simpler when each of the decisions/rules is based only on one of the variables.</p>
<div id="fitting-and-pruning-decision-trees" class="section level3 hasAnchor" number="1.2.1">
<h3><span class="header-section-number">1.2.1</span> Fitting and Pruning Decision Trees<a href="#fitting-and-pruning-decision-trees" class="anchor-section" aria-label="Anchor link to header"></a></h3>
<p>As mentioned previously decision trees are fit in a semi-optimal manner. What this means is that the pairs of variables and <em>split points</em> which determine the different regions, are chosen in order to minimise a loss function. However the final fitted model is very far from guaranteed to contain the best possible splitting of the input space even if we are restricted to axis-parallel rectangles. The reason for this is that the <em>Classification And Regression Trees</em> (CART) algorithm uses a <em>greedy optimisation</em> approach in which the rules in the tree are determined sequentially, and once a rule/split is added it cannot be removed. That is, first the pair of covariate and split point for the root node is chosen, and then it is kept fixed as the next splits are chosen, which are then fixed, and the next are chosen, etc.</p>
<p>Let’s suppose we have the regions in a tree denoted as <span class="math inline">\(\R_1, ..., \R_R\)</span>, and for any potential vector of covariates, <span class="math inline">\(\x\)</span>, let’s write <span class="math inline">\(\R(x)\)</span> to be the region into which <span class="math inline">\(\x\)</span> falls. Since there is a single fixed value predicted in each region (determined from the averages of the responses from the points falling in these regions), we can write the training error as
<span class="math display">\[
\frac{1}{n}\sum_{i=1}^n L(y_i, \hat y_{\R(\x_i)}),
\]</span>
where <span class="math inline">\(\hat y_{\R}\)</span> is the fitted value in region <span class="math inline">\(\R\)</span>. But since <span class="math inline">\(\hat y_{\R(\x)}\)</span> is the same for all <span class="math inline">\(\x \in \R\)</span> we can also write this as</p>
<p><span class="math display">\[
\frac{1}{n}\sum_{r=1}^R \sum_{i:\x_i \in \R_r} L(y_i, \hat y_{\R_r}).
\]</span>
In other words the training error can be split into the errors/losses from each of the regions/leaf nodes in the tree. The total loss from a leaf node is often referred to as the <em>impurity</em> of the node. When choosing which split to add next during the sequential fitting of a tree, then, one just needs to find the region whose impurity can be improved the most by splitting it into two new regions.</p>
<p>It should be clear that as more and more splits/regions are added to a tree, the resulting model will be able to fit better and better to the training data. Indeed if eventually every single point is in its own leaf node, then the training error will be zero. We know that fitting too well to the training data will very likely lead to overfitting and poor generalisation performance. The simplest approach for limiting the complexity of a decision tree is simply to terminate the sequential splitting either when a maximum number of leaf nodes is reached, or the <em>depth</em> (the maximum number of rules/splits taken from the root node to any leaf node) reaches some chosen maximum. Given our understanding of how regularisation can be used to fit models with good generalisation, an alternative is to use a penalised objective function
<span class="math display">\[
\frac{1}{n}\sum_{r=1}^R \sum_{i:\x_i \in \R_r} L(y_i, \hat y_{\R_r}) + \lambda R.
\]</span>
In the above <span class="math inline">\(R\)</span> is simply the number of splits/leaves/regions, and the penalty for increasing the complexity of the tree by adding an additional split is fixed equal to <span class="math inline">\(\lambda\)</span>. That is, there is no fixed maximum number of regions, and new regions can be added provided they improve the fit (i.e. reduce the training error) by at least <span class="math inline">\(\lambda\)</span>.</p>
<p>But here we reach a potential problem which comes about as a result of the <em>semi</em>-optimal manner in which trees are fit. What if by adding a “not-so-great” split fairly high up in the tree one is able to find a subsequent split which massively improves the overall fit? It is certainly possible that the high quality second split is not possible until the “not-so-great” split is added. A way around this is known as <em>pruning</em>. First a very deep/complex tree is fit, and then some of the branches are “pruned away” leaving a simpler tree in its place which gives a better penalised objective value. In this way it is possible to add the combination of a “not-so-great” split followed by a fantastic split instead of two mediocre splits (and, of course, more complex combinations of splits of varying quality).</p>
<p>In the context of what is known as <em>cost-complexity pruning</em> the penalty parameter <span class="math inline">\(\lambda\)</span> is often referred to as the <em>complexity parameter</em>, and this can simply be chosen using our ubiquitous cross validation.</p>
<div id="regression-trees" class="section level4 hasAnchor" number="1.2.1.1">
<h4><span class="header-section-number">1.2.1.1</span> Regression Trees<a href="#regression-trees" class="anchor-section" aria-label="Anchor link to header"></a></h4>
<p>Describing regression trees, given the above and what we already know about the standard regression problem, is relatively straightforward. As before a natural loss function to use when fitting regression trees is the squared error loss function, and we also learned when looking at likelihood based estimation in generalised linear models that minimising the squared error is equivalent to maximum likelihood when the response is normally distributed, i.e. when <span class="math inline">\(Y = g^*(X) + \epsilon\)</span> where <span class="math inline">\(\epsilon \sim N(0, \sigma_{\epsilon}^2)\)</span>.</p>
<p>The squared error loss function is also computationally preferred in the context of decision trees since when scanning over the potential splits along one of the covariate axes calculation of the total loss can be done recursively.</p>
<p><strong>Regression Trees in R</strong></p>
<p>The <code>caret</code> package can be used to fit (and tune) decision trees, however we will also be making use of the <code>rpart</code> package. We will also use the package <code>rpart.plot</code> which provides nice visualisations of fitted decision trees.</p>
<div class="sourceCode" id="cb1"><pre class="sourceCode r"><code class="sourceCode r"><span id="cb1-1"><a href="#cb1-1" tabindex="-1"></a><span class="do">### Start by loading the libraries we need</span></span>
<span id="cb1-2"><a href="#cb1-2" tabindex="-1"></a><span class="fu">library</span>(ISLR2)</span>
<span id="cb1-3"><a href="#cb1-3" tabindex="-1"></a><span class="fu">library</span>(rpart)</span>
<span id="cb1-4"><a href="#cb1-4" tabindex="-1"></a></span>
<span id="cb1-5"><a href="#cb1-5" tabindex="-1"></a><span class="do">### Let&#39;s quickly inspect</span></span>
<span id="cb1-6"><a href="#cb1-6" tabindex="-1"></a><span class="fu">dim</span>(Hitters)</span></code></pre></div>
<pre><code>## [1] 322  20</code></pre>
<p>Similar to the function <code>train</code> in <code>caret</code> the <code>rpart</code> function uses a “control” object which tells it how to perform fitting and pruning. For starters we will simply use a fixed complexity parameter (<code>cp</code>) and set the minimum number of observations allowed in any terminal node (<code>minbucket</code>).</p>
<div class="sourceCode" id="cb3"><pre class="sourceCode r"><code class="sourceCode r"><span id="cb3-1"><a href="#cb3-1" tabindex="-1"></a><span class="do">### Set up the control object</span></span>
<span id="cb3-2"><a href="#cb3-2" tabindex="-1"></a>contr <span class="ot">&lt;-</span> <span class="fu">rpart.control</span>(<span class="at">minbucket =</span> <span class="dv">10</span>, <span class="at">cp =</span> <span class="fl">0.001</span>)</span>
<span id="cb3-3"><a href="#cb3-3" tabindex="-1"></a></span>
<span id="cb3-4"><a href="#cb3-4" tabindex="-1"></a><span class="do">### Now we can fit our model, setting the seed to ensure</span></span>
<span id="cb3-5"><a href="#cb3-5" tabindex="-1"></a><span class="do">### reproducibility</span></span>
<span id="cb3-6"><a href="#cb3-6" tabindex="-1"></a><span class="fu">set.seed</span>(<span class="dv">123</span>)</span>
<span id="cb3-7"><a href="#cb3-7" tabindex="-1"></a>tree_model <span class="ot">&lt;-</span> <span class="fu">rpart</span>(<span class="fu">log</span>(Salary)<span class="sc">~</span>., <span class="at">data =</span> Hitters, <span class="at">control =</span> contr)</span></code></pre></div>
<p>By default when calling the <code>rpart</code> function cross validation is performed and the results for all complexity parameters greater than the value provided are stored. The cross validation results can be seen by using the function <code>plotcp</code>:</p>
<div class="sourceCode" id="cb4"><pre class="sourceCode r"><code class="sourceCode r"><span id="cb4-1"><a href="#cb4-1" tabindex="-1"></a><span class="fu">plotcp</span>(tree_model)</span></code></pre></div>
<p><img src="testing_files/figure-html/unnamed-chunk-3-1.png" width="672" /></p>
<p>The presentation of the results is slightly different from what we see from <code>caret</code>, where the <em>Relative Error</em> is shown representing the estimated prediction error relative to the model with no splits (i.e. one which simply uses the average in the entire data set). The horizontal dotted line also indicates the “one standard error rule” threshold. All relevant information is stored in the field <code>$cptable</code>, where the column <code>xerror</code> is the cross validation estimate of relative error and <code>rel error</code> is the <em>training</em> relative error:</p>
<div class="sourceCode" id="cb5"><pre class="sourceCode r"><code class="sourceCode r"><span id="cb5-1"><a href="#cb5-1" tabindex="-1"></a>tree_model<span class="sc">$</span>cptable</span></code></pre></div>
<pre><code>##             CP nsplit rel error    xerror       xstd
## 1  0.568937909      0 1.0000000 1.0072170 0.06567495
## 2  0.061287729      1 0.4310621 0.4722220 0.05346809
## 3  0.057784443      2 0.3697744 0.4657209 0.05537989
## 4  0.030786188      3 0.3119899 0.3964910 0.06113039
## 5  0.013096781      4 0.2812037 0.3513748 0.06089676
## 6  0.011700767      5 0.2681069 0.3745273 0.05898447
## 7  0.010933909      6 0.2564062 0.3691529 0.05819627
## 8  0.009209713      7 0.2454723 0.3698248 0.05808903
## 9  0.008216401      8 0.2362626 0.3736554 0.05929000
## 10 0.005492546      9 0.2280462 0.3898444 0.06430554
## 11 0.005158254     10 0.2225536 0.3828877 0.06503018
## 12 0.003910817     11 0.2173954 0.3901558 0.06991258
## 13 0.003753955     12 0.2134845 0.3914650 0.06991046
## 14 0.003390561     13 0.2097306 0.3914650 0.06991046
## 15 0.001000000     14 0.2063400 0.3974447 0.07122065</code></pre>
<p>To extract a model for a different setting of <code>cp</code> after fitting a first tree with <code>rpart</code> one can use the function <code>prune</code>. For example, for the values of <code>cp</code> which minimise the estimated prediction error and using the 1 standard error rule</p>
<div class="sourceCode" id="cb7"><pre class="sourceCode r"><code class="sourceCode r"><span id="cb7-1"><a href="#cb7-1" tabindex="-1"></a><span class="do">### Minimum cv error</span></span>
<span id="cb7-2"><a href="#cb7-2" tabindex="-1"></a>ix_min <span class="ot">&lt;-</span> <span class="fu">which.min</span>(tree_model<span class="sc">$</span>cptable[,<span class="st">&#39;xerror&#39;</span>])</span>
<span id="cb7-3"><a href="#cb7-3" tabindex="-1"></a>cp_min <span class="ot">&lt;-</span> tree_model<span class="sc">$</span>cptable[ix_min,<span class="st">&#39;CP&#39;</span>]</span>
<span id="cb7-4"><a href="#cb7-4" tabindex="-1"></a></span>
<span id="cb7-5"><a href="#cb7-5" tabindex="-1"></a>pruned_tree_min <span class="ot">&lt;-</span> <span class="fu">prune</span>(tree_model, <span class="at">cp =</span> cp_min)</span>
<span id="cb7-6"><a href="#cb7-6" tabindex="-1"></a></span>
<span id="cb7-7"><a href="#cb7-7" tabindex="-1"></a><span class="do">### One standard error rule</span></span>
<span id="cb7-8"><a href="#cb7-8" tabindex="-1"></a>ix_1se <span class="ot">&lt;-</span> <span class="fu">min</span>(<span class="fu">which</span>(tree_model<span class="sc">$</span>cptable[,<span class="st">&#39;xerror&#39;</span>] <span class="sc">&lt;=</span> tree_model<span class="sc">$</span>cptable[ix_min,<span class="st">&#39;xerror&#39;</span>] <span class="sc">+</span></span>
<span id="cb7-9"><a href="#cb7-9" tabindex="-1"></a>                      tree_model<span class="sc">$</span>cptable[ix_min,<span class="st">&#39;xstd&#39;</span>]))</span>
<span id="cb7-10"><a href="#cb7-10" tabindex="-1"></a>cp_1se <span class="ot">&lt;-</span> tree_model<span class="sc">$</span>cptable[ix_1se,<span class="st">&#39;CP&#39;</span>]</span>
<span id="cb7-11"><a href="#cb7-11" tabindex="-1"></a></span>
<span id="cb7-12"><a href="#cb7-12" tabindex="-1"></a>pruned_tree_1se <span class="ot">&lt;-</span> <span class="fu">prune</span>(tree_model, <span class="at">cp =</span> cp_1se)</span></code></pre></div>
<p><strong>Visualising and Interpreting Decision Trees</strong></p>
<p>One of the reasons decision trees are favoured by practicioners is the fact that they can very clearly and intuitively be visualised, provided they are not very complex. Let’s investigate the trees we fit above to the <code>Hitters</code> data set using the <code>prp</code> function in the <code>rpart.plot</code> package.</p>
<div class="sourceCode" id="cb8"><pre class="sourceCode r"><code class="sourceCode r"><span id="cb8-1"><a href="#cb8-1" tabindex="-1"></a><span class="do">### Load the package</span></span>
<span id="cb8-2"><a href="#cb8-2" tabindex="-1"></a><span class="fu">library</span>(rpart.plot)</span>
<span id="cb8-3"><a href="#cb8-3" tabindex="-1"></a></span>
<span id="cb8-4"><a href="#cb8-4" tabindex="-1"></a><span class="do">### The two trees selected using cross validation</span></span>
<span id="cb8-5"><a href="#cb8-5" tabindex="-1"></a><span class="fu">par</span>(<span class="at">mfrow =</span> <span class="fu">c</span>(<span class="dv">1</span>, <span class="dv">2</span>))</span>
<span id="cb8-6"><a href="#cb8-6" tabindex="-1"></a><span class="fu">prp</span>(pruned_tree_min, <span class="at">main =</span> <span class="st">&quot;Tree selected by minimum CV error&quot;</span>)</span>
<span id="cb8-7"><a href="#cb8-7" tabindex="-1"></a></span>
<span id="cb8-8"><a href="#cb8-8" tabindex="-1"></a><span class="fu">prp</span>(pruned_tree_1se, <span class="at">main =</span> <span class="st">&quot;Tree selected by 1 SE rule&quot;</span>)</span></code></pre></div>
<p><img src="testing_files/figure-html/unnamed-chunk-6-1.png" width="672" /></p>
<ul>
<li>It is hopefully not surprising that the model selected using the one standard error rule is simpler than the one which gave the lowest cross validation error estimate.</li>
</ul>
<p>Both trees clearly indicate how the predictions from the two models come about. For example, in the left tree we can see that the key determining factors (as captured by this model) in achieving the highest predicted salary (bottom right leaf of the tree) is to have variable <code>CAtBat</code> (number of times batting in entire career) at least 1452, <code>Hits</code> (total number of hits in the year 1986) at least 118, and <code>CRBI</code> (total number of runs scored in career) at least 273. None of the other variables affects <em>this particular</em> prediction, but the number of career hits <code>CHits</code> is an important variable for prediction when <code>CAtBat</code> is less than 1452.</p>
<p>The fact that different variables become more/less important depening on splits higher up the tree mean that decision trees are extremely well suited to capturing complex interactions between covariates. However, as alluded to above, being able to interpret the outputs of a tree model relies on its not being too complex. If we consider the original tree we fit, we see something less appealing</p>
<div class="sourceCode" id="cb9"><pre class="sourceCode r"><code class="sourceCode r"><span id="cb9-1"><a href="#cb9-1" tabindex="-1"></a><span class="fu">prp</span>(tree_model, <span class="at">main =</span> <span class="st">&quot;Tree with default cp = 0.001&quot;</span>)</span></code></pre></div>
<p><img src="testing_files/figure-html/unnamed-chunk-7-1.png" width="672" /></p>
<p>Although with only 320 observations and a minimum node size of 10 one cannot ever reach extreme levels of complexity, already in this model interpretation becomes more challenging than in the pruned models.</p>
</div>
<div id="classification-trees" class="section level4 hasAnchor" number="1.2.1.2">
<h4><span class="header-section-number">1.2.1.2</span> Classification Trees<a href="#classification-trees" class="anchor-section" aria-label="Anchor link to header"></a></h4>
</div>
</div>
<div id="interpreting-decision-trees" class="section level3 hasAnchor" number="1.2.2">
<h3><span class="header-section-number">1.2.2</span> Interpreting Decision Trees<a href="#interpreting-decision-trees" class="anchor-section" aria-label="Anchor link to header"></a></h3>
</div>
<div id="cost-complexity-pruning" class="section level3 hasAnchor" number="1.2.3">
<h3><span class="header-section-number">1.2.3</span> Cost Complexity Pruning<a href="#cost-complexity-pruning" class="anchor-section" aria-label="Anchor link to header"></a></h3>
</div>
<div id="some-further-comments-on-decision-trees" class="section level3 hasAnchor" number="1.2.4">
<h3><span class="header-section-number">1.2.4</span> Some further Comments on Decision Trees<a href="#some-further-comments-on-decision-trees" class="anchor-section" aria-label="Anchor link to header"></a></h3>
<ul>
<li><p>Handle combinations of categorical and continuous covariates well (where categorical variables are often tricky to handle for nonparametric models)</p></li>
<li><p>Handle missing data directly!</p></li>
<li><p>Instability!</p></li>
</ul>
</div>
</div>
</div>
            </section>

          </div>
        </div>
      </div>


    </div>
  </div>
<script src="libs/gitbook-2.6.7/js/app.min.js"></script>
<script src="libs/gitbook-2.6.7/js/clipboard.min.js"></script>
<script src="libs/gitbook-2.6.7/js/plugin-search.js"></script>
<script src="libs/gitbook-2.6.7/js/plugin-sharing.js"></script>
<script src="libs/gitbook-2.6.7/js/plugin-fontsettings.js"></script>
<script src="libs/gitbook-2.6.7/js/plugin-bookdown.js"></script>
<script src="libs/gitbook-2.6.7/js/jquery.highlight.js"></script>
<script src="libs/gitbook-2.6.7/js/plugin-clipboard.js"></script>
<script>
gitbook.require(["gitbook"], function(gitbook) {
gitbook.start({
  "sharing": {
    "github": false,
    "facebook": true,
    "twitter": true,
    "linkedin": false,
    "weibo": false,
    "instapaper": false,
    "vk": false,
    "whatsapp": false,
    "all": ["facebook", "twitter", "linkedin", "weibo", "instapaper"]
  },
  "fontsettings": {
    "theme": "white",
    "family": "sans",
    "size": 2
  },
  "edit": {
    "link": null,
    "text": null
  },
  "history": {
    "link": null,
    "text": null
  },
  "view": {
    "link": null,
    "text": null
  },
  "download": null,
  "search": false,
  "toc": {
    "collapse": "subsection"
  }
});
});
</script>

<!-- dynamically load mathjax for compatibility with self-contained -->
<script>
  (function () {
    var script = document.createElement("script");
    script.type = "text/javascript";
    var src = "true";
    if (src === "" || src === "true") src = "https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.9/latest.js?config=TeX-MML-AM_CHTML";
    if (location.protocol !== "file:")
      if (/^https?:/.test(src))
        src = src.replace(/^https?:/, '');
    script.src = src;
    document.getElementsByTagName("head")[0].appendChild(script);
  })();
</script>
</body>

</html>
