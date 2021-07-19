##  Unsupervised Learning [^2]

With supervised learning, each example is labled as either a positive or negative example (e.g. benign or malignant tumor) — we're told explicitly what is the so-called "right" answer.  In unsupervised learning, we're given data that doesn't have any labels, or otherwise no explicit indication of what is the "right" answer.  

### Clustering

So, given a dataset, can one find some structure, or patterns, or clusters in the data?

E.g. Google News: every look at 10s of thousands of new stories on the web and groups them into clusters.  So stories that are all about the same topic get displayed together.

E.g. DNA microarray data, put a group of individauls together and for each of them you measure how much they do or do nto have s specific gene.  Then you run a clustering algorithm to group individuals into different categories or different types of people.

### Cocktail Party Algorithm

Clustering is just one example of unsupervised learning.  Another one is _cocktail party problem_.  Given a party where everyone is talking, lots of overlapping voices.  Imagine two people speaking at the same time, and two microphones at different positions recording the voices.  Each microphone records a different combination of these two speaker voices.  Maybe one speaker is a bitl louder than the other. A CP algorithm can separate out these two audio sources, and be able to draw conclusions about them discretely.

While this seems like a complex problem it can be done with one line of code:

```octave
[W,s,v] = svd((repmat(sum(x.*x, 1), size(x, 1), 1). *x) *x');
```

While not easy, when you use the right programming environment, many learning algorithms can be really short programs.

E.g. `svd` function stands for singular value decomposition.  This is a linear algegra routine that is built into Octave.  In C++ or Java this would be many complex lines of code.
