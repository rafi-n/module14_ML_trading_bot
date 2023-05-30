# Venture Funding with Deep Learning
---
## Tuning the Baseline Trading Algorithm

### Step 1
We adjusted the size of the training and testing set. We started with 3 months for the training set and the remained in the test set. Then we looked at the difference between 3 months, 1 month and 6 months. The results are shown below.

![Training Set 1 Month S4L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_1_months_SMAS_4_SMAL_100.png)

<p style="text-align: center;">Training Set 1 Month, SMA Short 4, SMA Long 100</p>

---

![Training Set 3 Months S4L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_3_months_SMAS_4_SMAL_100.png)

<p style="text-align: center;">Training Set 3 Months, SMA Short 4, SMA Long 100</p>

---

![Training Set 7 Months S4L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_4_SMAL_100.png)

<p style="text-align: center;">Training Set 7 Months, SMA Short 4, SMA Long 100</p>

---

*What impact resulted from increasing or decreasing the training window?*

The 7 month training window provides the best result. The 3 month window shows the strategy outperforming the actual for all points in time. However, the 7 month window provides strategy return of 1.852 at the end, despite falling below the actual between 2019 and 2020. A larger training window provides more data points for our algorithm to learn from and produce better results.

### Step 2
Using the 7 month training window, which performed best, we'll try adjusting the SMA windows. 

#### SMA Adjustment 1
In this adjustment, we're decreasing the short window to 2 and keeping the long window at 100.

![Training Set 7 Months S2L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_2_SMAL_100.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 2, SMA Long 100</p>

Final Strategy Return = 1.603

---

#### SMA Adjustment 2
In this adjustment, we're increasing the short window to 8 from its original value and keeping the long window at 100.

![Training Set 7 Month S8L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_8_SMAL_100.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 8, SMA Long 100</p>

Final Strategy Return = 1.222

---

#### SMA Adjustment 3
Increasing the short window further to 20 and keeping the long window at 100.

![Training Set 7 Month S20L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_20_SMAL_100.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 20, SMA Long 100</p>

Final Strategy Return = 1.386

---

#### SMA Adjustment 4
Although the strategy returns are smaller than our 7 month training window from Step 1, they seem to be increasing. We'll increase the short window further to 50 and keeping the long window at 100.

![Training Set 7 Month S50L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_50_SMAL_100.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 50, SMA Long 100</p>

Final Strategy Return = 1.491

---

#### SMA Adjustment 5
The strategy return is still increasing so we'll try one more with a short window of 80, keeping the long window at 100.

![Training Set 7 Month S80L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_80_SMAL_100.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 80, SMA Long 100</p>

Final Strategy Return = 1.491

---

#### SMA Adjustment 6
It appears that a short window of 50 may be best when looking at short SMA windows larger than 4. Now, we'll start increasing the size of the large window to 200.

![Training Set 7 Month S50L200](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_50_SMAL_200.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 50, SMA Long 200</p>

Final Strategy Return = 1.256

---

#### SMA Adjustment 7
Since the best return came from a long-to-short window of 25:1, we'll try try a long window of 1250, while keeping the short window at 50.

![Training Set 7 Month S50L1250](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_50_SMAL_1250.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 50, SMA Long 1250</p>

Final Strategy Return = 1.32

---

#### SMA Adjustment 8
We're still underperforming, so let's see if increasing the long window to 1875 improves it.

![Training Set 7 Month S50L1875](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_50_SMAL_1875.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 50, SMA Long 1875</p>

Final Strategy Return = 1.202

---

#### SMA Adjustment 9
Due to the poor performance of the previous adjustment, we'll go back to a long window of 1250, but increase the size of the short window to 625.

![Training Set 7 Month S625L1250](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_625_SMAL_1250.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 625, SMA Long 1250</p>

Final Strategy Return = 1.32

---

#### SMA Adjustment 10
We'll now see what effect reducing the short window has while keeping the previous long window size.

![Training Set 7 Month S4L1250](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_4_SMAL_1250.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 4, SMA Long 1250</p>

Final Strategy Return = 1.32

---

#### SMA Adjustment 11
The previous trial didn't show any improvement. Looking back at the strategy employed, we said that a sell or buy signal would be executed the day after the change in returns. So keeping both windows relatively small, maybe we can better predict sell and buy signals.

![Training Set 7 Month S4L8](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_4_SMAL_8.png)

<p style="text-align: center;">Training Set 7 Month, SMA Short 4, SMA Long 8</p>

Final Strategy Return = 1.171

---

*What impact resulted from increasing or decreasing either or both of the SMA windows?*

Both increasing and decreasing the short and long windows produced lower returns. Increasing the size of the long window made the strategy returns very closely track the actual returns. 

### Step 3

The best performance was found using the following parameters:
<pre>
- training set:     7 months
- SMA short window: 4
- SMA long window:  100
</pre>
![Training Set 7 Months S4L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/cumprod_plot_act_vs_strat_offset_7_months_SMAS_4_SMAL_100.png)

<p style="text-align: center;">Training Set 7 Months, SMA Short 4, SMA Long 100</p>

Final Strategy Return = 1.852

---

## Evaluate a New Machine Learning Classifier
Here are the results of using the AdaBoost Classifier with the original settings.

Settings:
<pre>
- training set:     3 months
- SMA short window: 4
- SMA long window:  100
</pre>
![ABC Training Set 3 Months S4L100](https://github.com/rafi-n/module14_ML_trading_bot/blob/main/Images/abc_cumprod_plot_act_vs_strat_offset_3_months_SMAS_4_SMAL_100.png)

<p style="text-align: center;">AdaBoost Training Set 3 Months, SMA Short 4, SMA Long 100</p>

Final Strategy Return = 1.602

*Did this new model perform better or worse than the provided baseline model?*
While the ultimate return was the same, over most of the time it outperformed the actual returns.

*Did this new model perform better or worse than your tuned trading algorithm?*
The tuned algorithm ultimately performed better since it provided at return of 1.852 vs. 1.602 for the new AdaBoost model.

## Summary Evaluation Report

This analysis looked at SVM and AdaBoost models to improve the returns based on the given data. Several variations to the model parameters were made to determine what changes would improve the results. The variations explored were:

    1. Changing the size of the training set
    2. Increasing and decreasing the size of the SMA short and log window
    3. Changing the classifier from SVM to AdaBoost

1. Changing the size of the training set

    The greatest improvement was found through increasing the size of the training set. The graph of 'Training Set 7 Months, SMA Short 4, SMA Long 100' from Step 1 above, show that at 7 months worth of training data, we got a better return. Our model was able to better learn the data and make predictions with more data without overfitting.
    
2. Increasing and decreasing the size of the SMA short and long window

    Several attempts were made to adjust both SMA windows, as seen in Step 2 above. A larger SMA long window made the results track very closely to the actual returns. When the short and long windows are relatively close to each other, the results also track closer to the actual returns. None of the adjustments were able to match the original window size results.

3. Changing the classifier from SVM to AdaBoost

    Returning to the original parameters and applying the AdaBoost classifier did not improve the results. The results from this change were the same compared to the original. This can be seen from the graph of 'AdaBoost Training Set 3 Months, SMA Short 4, SMA Long 100' above.

Summary table of best settings and outcome:

|Parameter|Value|
|:---|:---:|
|Training Set Size|7 months|
|SMA Short Window|4|
|SMA Long Window|100|
|Strategy Return (result)|1.852|