# Question a
For k = 2, it would be green since it's the closest to the test instance (1 green vs 1 red, the tie is broken by the shortest distance).
For k = 5, it would be blue since there are 3 neighbours belonging to that class.
For k = 7, it would be red: there are 3 blues, 3 reds and 1 green. The closest neighbour among the tied classes is red, so the test instance becomes red.
For k = 8, it would be red because we have 4 reds, 3 blues and 1 green.

# Question b
Instance-based learning doesn't really build a model, it stores the training examples and, at prediction time, compares the new sample to them with a similarity measure either the distance or something quantitative. Training is almost free, but prediction is slow and all the data must be kept.
Model-based learning uses the training data to learn the parameters of a model like the slope and intercept of a linear regression. Once trained, the data is no longer needed and prediction is fast.

# Question c
K-NN is instance-based because it memorizes the training set only.

# Question d
A larger K is useful when the data is noisy or when the classes overlap. Averaging over more neighbours reduces the influence of outliers, which in turn gives lower variance.

# Question e
If K is too large, the region are bigger, the neighbours are not local anymore and the model underfits. It tends to always predict the majority class. Small classes get ignored and the computation is also heavier.

# Question f
We can break the tie by taking the class of the closest neighbour among the tied classes, change K until the tie disappears, or pick randomly. For binary classification, using an odd K avoids ties.

# Question g
No. K-NN must store and compare against the whole training set, which is costly in memory and time for a large image dataset. Pixel distances don't capture the semantic content of images, and with 1'000 classes we need a lot of examples per class. It could work better on features extracted by a neural network, but on raw pixels it is a poor choice.

# Question h
The curse of dimensionality in this case is present. The nearest neighbour is almost as far as the farthest one and the notion of neighbours a,d regions loses its meaning with higher dimensionality. The amount of data needed to cover the space grows exponentially with the number of dimensions, and irrelevant features add noise to the distance.

# Question i
The error rate is 0%. Each training point is its own nearest neighbour (distance 0), so it always gets its own label. 

# Question j
Also 0%. The first neighbour is the point itself. If the second neighbour has the same class, the prediction is correct. If not, there is a 1–1 tie, which is broken by the shortest distance so the prediction is still correct.