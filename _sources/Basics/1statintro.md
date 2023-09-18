# Introduction to Data Analysis

Statistics is about analysis of numbers. We refer to what we study as *data*.

## Types of Data

- Qualitative Data:
Not inherently numerical, for example, Gender, or eye color.
Any allocation of numbers to express this type of data is arbitrary.

- Discrete Data:
This is data that uses numbers, but there a gaps between the numbers. Discrete data is data we cant count. For example, goals scored in a sports game or the number of people in the stadium.

- Continous Data:
Continous data is also numerical in nature, however, all possible values are attainable. For example, height or time.


## Measurment Scales

When talking about numerical data, we can have *nominal* and *ordinal* scales. Put simply, with an *ordinal* scale the order of the numbers matter i.e. 1 is better than 2 which is better than 2 etc.
A nominal sale is one which the numbers dont matter. For example a student ID is rather arbitrary, the numbers chosen for student don't have an meaning other than being unique for each student - their relative order does not matter.

## Graphical Representations

Data visualization helps display data in meaningful ways, if the correct representation is chosen. The following graphical representations exist:

See https://www150.statcan.gc.ca/n1/edu/power-pouvoir/ch9/5214821-eng.htm for visuals.

- Pictograms:
With pictograms we use pictures to represent data.

- Bar Charts:
Bar charts should be used when you are showing segments of information.
They can be horizontal, vertical, grouped, and stacked. 

- Pie Charts:
Looks like a pie. Is seperated into segments to represent different categories.

- Stem and Leaf Plots:
This one is best explained using an example and is good for displaying distributions of data.

    Example: 

    Given The data set : 12, 23, 34, 45, 56, 67, 78, 89, 90, 23, 34, 45, 56, 67, 78, 12, 23, 34, 45, 56

    We sort the data : 12, 12, 23, 23, 23, 34, 34, 34, 45, 45, 45, 56, 56, 56, 67, 67, 78, 78, 89, 90

    Then we make it into a Stem and Leaf plot:

    9 | 0
    8 | 9
    7 | 8 8
    6 | 7 7
    5 | 6 6 6
    4 | 5 5 5
    3 | 4 4 4
    2 | 3 3 3
    1 | 2 2

- Histograms:
This looks lik a bar graph, but it is for continous data and is good in visualizing distributions of data. A bar chart may displays something like how many of each animal does a zoo have (each animal will have it's own bar)

- Cumulative frequency curves:
This is like a lin chart, but the data is cumalitive.

# Representative statistics

This the basics. No need for too many words.

- Datum Notation:
we use a subscript to label a datums place in a set of data i.e. $x_1, x_2, x_3... $

- Sum Notation:
You will see the "sigma" symbol a lot. It looks like this: $\Sigma$ 
    
    This symbol is used for sum in the following manner:
$\Sigma_{i=1}^{n}x_i = x_1 +x_2 + x_3 + .... x_n$

- Mean: 
This is the average.
    
     $\bar{x} = \frac{1}{n}\Sigma_{i=1}^{n}x_i$

- Median:
This is the middle. Sort the data, find the middle datum.

- Mode: 
This is the most common value in the data. If there are two modes, the data is called bimodal. The mode is easy to find by sorting the data and see which value repeats the most.

- Sample Variance:
Denoted $s^2$ and measures how disperse a data set is.

    $s^2 = \frac{1}{n}\Sigma_{i=1}^{n}(x_i-\bar{x})^2$

- Standard Deviation:
Denoted $s$ and is the positive square root of the sample variance.

    $|\sqrt{s^2}| = s$