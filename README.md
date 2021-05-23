# unit14_deep_learning
Homework for unit 14, Deep Learning

## Overview
This homework evaluates a dataset consisting of a Crypto Fear & Greed Index along with Crypto Closing Prices.  The main objective is to evaluate the data with a LTSM Neural Network to see which feature, the Fear & Greed Index, or the Previous Closing Prices, is better at predicting future pricing.

## Approach

Two separate notebooks were used for this homework, one that used the Fear & Greed Index as the feature, while the other used previous Crypto Closing Prices.  Both models were tweaked to see if certain parameters improved the accuracy of the model.

## Fear and Greed Index Results

Running the LTSM with the default settings (Window Size of 10, 10 Epochs, Batch Size of 1, and 3 Layers) produces a loss of .1088.  Predicted values were not in line with Real prices as evidenced by the Plot (See FnGWindowSize10.html).  The first change was to decrease the windows size to 5 and keep all other parameters the same.  The loss produced with this adjustment was slightly lower at 0.1001.  Since there was a slight improvement with a windows size of 5, this was kept the same, while the Epochs were increased to 20 and the batch size 2.  This had no impact on the loss score as it remained .1001.  The last change was to return the Window Size to 10, Epochs 10, batch size 1, and a layer was removed leaving 2.  The resulting loss score was .0805.

## Closing Price Results

Running this LTSM with the default settings (Window Size of 10, 10 Epochs, Batch Size of 1, and 3 Layers) produces a loss of .0435.  Predicted values seem to follow Real prices, but there is room for improvement with this model (see ClosingWindowSize10.html).  Reducing the Window to 5, had no substantial change, generating a loss of .0444.  When we kept the Window Size 5, but changed the Epochs to 20 and Batch Size to 2, the loss dropped to .0340.  The last change was to keep the parameters the same as the last test (5,20,2) but drop a layer in the network bringing it down to 2.  This made a significant improvement with a loss of 0.0138.

## Final Results

For this experiment, the Closing Prices are clearly a better feature for predicting future Crypto prices.  A smaller windows size (5) and 2 layers in the network, provided a lower loss and a more accurate model as evidenced by the graph trendlines (See ClosingWinSz5Epochs20Bat2Layer2.html). Both models appeared to benefit from a reduction in layers going from 3 to 2.
