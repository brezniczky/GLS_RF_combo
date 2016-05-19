## N-step generalized least squares combined with random forest

This stuff is the work of Janos Brezniczky (c) 2016 partly as a memento of 
scripts created earlier (but possibly never published) for the How Much Did It 
Rain II Kaggle competition.

If you find it interesting, feel free to contact me!

### Expected properties
(to be extensively/comparatively verified):

- more robust towards non-linearity and asymmetric distributions than GLS
- more robustness against high levels of noise than in case of the standard RF

Reducing the weights of highly deviating observations has been traditionally one
modelling strategy (extreme example: assign weght = 0, i.e. remove outliers).
It can, depending on the data and relationships, come useful in the case of even
the modern machine learning methods.

The reasoning is obvious: no generic learning algorithm can be fully unaffected
by the quality of the data - knowing, or being able to estimate how much 
individual observations are reliable is a valuable insight that should be 
leveraged as much as possible, if the efficiency is needed.

To achieve this, h2o.ai's random forest algorithm is used at the moment, as this
one allows for specifying a per observation weighting column for the training.

In the notebook I think I've left the demo "implementation" at N=3 steps, but 
it's very easy to generalize from that point.

So far I haven't found an earlier implementation of the concept, so I have hopes
and plans at improving it to be a fully fledged learning algorithm if found 
useful. Most likely it would not become much more than an option in some 
existing packages.
