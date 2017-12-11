# XGBoost_Example
XGBoost learning notes and code instances
## Table of Contents
1. The XGBoost Advantage
2. Understand XGBoost Parameters
3. Tuning Parameters(with python exmaples)
## 1. The XGBoost Advantage
1. **Regularization**
    + Standard GBM implementation has no regularization like XGBoost, therefore it also helps to reduce overfitting.  
    + In fact, XGBoost is also known as ‘regularized boosting‘ technique.
2. **Parallel Processing**
    + XGBoost implements parallel processing and is blazingly faster as compared to GBM.
    + But hang on, we know that boosting is sequential process so how can it be parallelized? We know that each tree can be built only            after the previous one, so what stops us from making a tree using all cores? I hope you get where I’m coming from. Check this link        out to explore further.
    + XGBoost also supports implementation on Hadoop.
3. **High Flexibility**
    + XGBoost allow users to define custom optimization objectives and evaluation criteria.
    + This adds a whole new dimension to the model and there is no limit to what we can do.
4. **Handling Missing Values**
    + XGBoost has an in-built routine to handle missing values.
    + User is required to supply a different value than other observations and pass that as a parameter. XGBoost tries different things as        it encounters a missing value on each node and learns which path to take for missing values in future.
5. **Tree Pruning**
    + A GBM would stop splitting a node when it encounters a negative loss in the split. Thus it is more of a **greedy algorithm**.
    + XGBoost on the other hand make **splits upto the max_depth** specified and then start **pruning** the tree backwards and remove splits beyond which there is no positive gain.
    + Another advantage is that sometimes a split of negative loss say -2 may be followed by a split of positive loss +10. GBM would stop        as it encounters -2. But XGBoost will go deeper and it will see a combined effect of +8 of the split and keep both.
6. **Built-in Cross-Validation**
    + XGBoost allows user to run a **cross-validation at each iteration** of the boosting process and thus it is easy to get the exact optimum        number of boosting iterations in a single run.
    + This is unlike GBM where we have to run a grid-search and only a limited values can be tested.
7. **Continue on Existing Model**
    + User can start training an XGBoost model from its last iteration of previous run. This can be of significant advantage in certain         specific applications.
    + GBM implementation of sklearn also has this feature so they are even on this point.
