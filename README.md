# Package: statdistwiz

Package building exercise from Udacity course: AI Programming with Python.

This package contains code to plot Gaussian and Binomial distributions from a plain text file (one value per line) and perform basic statistical analysis of a data set, analogous to the popular Python package scipy.


## Installation

Recommend setting up a virtual environment before pip installing non standard Python packages in order to protect the main installation.

### Install using pip
```pip install statdistwiz```<br>
```!pip install statdistwiz #to install from Jupyter notebook```

#### Import the Gaussian and Binomial modules
```from statdistwiz import Gaussian, Binomial```

#### Dependencies
- Python
- matplotlib


## Description

### Package Contents


#### For a Gaussian (aka Normal) distribution: 
Calculate the mean, standard deviation (sample or population - distinction between sample and population standard deviations is an important concept in statistics), plot a histogram of the data set, calculate probability density function (PDF), plot histograms of the normalised data and PDF along the same range and add two binomial distributions.

##### Examining the Standard Deviation Equations: Focus on Sample and Population Scenarios 
In many practical scenarios, we work with samples of data rather than entire populations, so the sample standard deviation is commonly used for statistical analysis and inference. It provides an estimate of the population standard deviation based on the available sample data.

##### Example of Sample Standard Deviation (most common type used for general calculations)
To use sample standard deviation for the assay of a test sample if you were for example, a scientist, you would typically follow these steps:

- Collect Data: First, you would conduct the assay on the test sample multiple times to generate a set of data points representing the measurements of the analyte of interest.

- Calculate Mean: Calculate the mean (average) of the data points. This represents the central tendency of the measurements.

- Calculate Sample Standard Deviation: Calculate the sample standard deviation of the data points. This value quantifies the dispersion or variability of the measurements around the mean.

- Interpretation: Analyse the sample standard deviation to assess the precision of the assay. A smaller sample standard deviation indicates that the measurements are clustered closely around the mean, suggesting high precision. On the other hand, a larger sample standard deviation indicates more variability in the measurements, which may indicate lower precision.

- Quality Control: Compare the sample standard deviation to predefined acceptance criteria or thresholds. If the sample standard deviation exceeds the acceptable limits, it may indicate issues with the assay method or experimental conditions that need to be addressed.

- In Excel (where you would most likely use this routinely if required for you job), sample standard deviation can be calculated with with STDEV (compatible with earlier versions of Excel) or STDEV.S function.

##### Example of Population Standard Deviation 
If you work in a manufacturing plant that produces electronic components. One critical aspect of the manufacturing process is ensuring the consistency and reliability of the components' dimensions.

- To monitor the quality control of the components, you decide to measure the lengths of a sample of components from each production batch. However, instead of considering these measurements as a sample from a larger population (which would require using sample standard deviation), you treat these measurements as the entire population of interest.

- By calculating the population standard deviation of the component lengths, you can assess the variability and dispersion of the measurements within the entire production batch.

- A low population standard deviation indicates that the component lengths are very consistent and have minimal variation, which is desirable for maintaining quality standards.

- A high population standard deviation suggests that there is significant variability in the component lengths, which may indicate inconsistencies in the manufacturing process that need to be addressed.

- Using population standard deviation in this manufacturing setting allows you to evaluate the uniformity of the components' dimensions across the entire production batch, enabling you to identify and address any quality control issues effectively.

- In Excel population standard deviation can be calculated with with the STDEV.P function.

##### Gaussian Distribution Description 
In a Gaussian (aka Normal) distribution plot, the probability density function (PDF) is used to describe the likelihood of observing a given value or range of values (whole or decimal numbers) in the distribution. The Gaussian plot itself does take into account probability through the shape of the curve, which is determined by the mean and standard deviation of the distribution.

The Gaussian distribution is characterized by its mean (μ) and standard deviation (σ), which together determine the shape of the curve. The probability of observing a value within a certain range can be inferred from the area under the curve within that range.

Visually, this type of distribution looks like a bell curve. The mean, median, and mode are found at the centre of the distribution, and the standard deviation is the distance from the centre to the change of curvature points on either side. Curvature points also referred to as inflection points, are found using the standard deviation.

![Alt Text](https://github.com/NatashaTechwiz/stadistwiz/blob/main/images/gaussian_curve_ex.png) <br>
image source: https://calcworkshop.com/exploring-data/normal-distribution/

The Gaussian distribution is commonly used to model continuous variables (those that can theoretically have an infinite number of possible values within a specified interval) such as height, weight, temperature, and time.

The Gaussian plot does not explicitly require manual calculation of probabilities for individual data points because the continuous curve represents the relative likelihood of observing different values in the distribution. The curve is normalized such that the total area under the curve is equal to 1, representing the total probability of observing any value in the distribution.

Therefore, the Gaussian plot inherently encapsulates probability through the shape of the curve, making it unnecessary to explicitly calculate probabilities for individual data points within the distribution.

##### Histogram of Data vs Normalised Histogram of Data and Gaussian Distribution Curve

If the initial histogram plot approximates to a bell curve, this is characteristic of a gaussian distribution. If it is not, you will need to employ a different technique on the data set, outside the scope of this package to calculate density function.<br>
![Alt Text](https://github.com/NatashaTechwiz/stadistwiz/blob/main/images/gaussian_hist_ex.png) <br>

By plotting the normal distribution curve based on the sample mean and sample standard deviation alongside the normalised histogram of the data, you can visually compare the actual data distribution with the expected normal distribution. This comparison helps in assessing how closely the data aligns with the characteristics of a normal distribution.<br>
![Alt Text](https://github.com/NatashaTechwiz/stadistwiz/blob/main/images/normed_hist.png)


#### For a Bimomial distribution:
Calculate the mean, standard deviation (given that you know the probability of the event occurring and the number of trails) , plot a bar chart of the outcomes, calculate probability mass function (PMF) and plot a bar chart of the PMF of the binomial distribution and add two binomial distributions with the same probability value.

##### Binomial Distribution Description 
The binomial distribution is commonly used to model scenarios involving binary outcomes, such as coin flips, pass/fail experiments, or success/failure trials. It is a fundamental distribution in probability theory and statistics for analysing discrete random variables with fixed trial numbers and constant success probabilities. Values are usually whole numbers typically represented as 1 for 'success' and 0 for 'failure'.

- Discrete random variables take on a countable number of distinct values from 0 to the total number of trials.
- These probabilities sum to 1, reflecting all possible outcomes of the experiment.

PMF is used for discrete random variables, where each possible value has a non-zero probability. In the case of the binomial distribution, the PMF calculates the probability of getting a specific number of successes in a fixed number of trials. The shape of the PMF depends on the specific distribution being considered and therefore may not be a bell shaped curve.


![Alt Text](https://github.com/NatashaTechwiz/stadistwiz/blob/main/images/neg_binomial.png) <br>
Example plot for a PMF with a negative binomial distribution (the number of trials required to reach a fixed number of successes) e.g. modeling the number of calls a call center operator needs to make before a certain number of successful sales.

##### Characteristics of a Binomial Distribution:
A binomial distribution is characterised by several key parameters that define its shape and behavior. The main values that characterize a binomial distribution are:

Number of Trials (n):
- Represents the fixed number of independent trials or experiments.
- Each trial has two possible outcomes: success or failure.

Probability of Success (p):
- Indicates the probability of success for each individual trial.
- The probability of failure is complementary to p and is denoted as 1 - p.

Random Variable (X):
- Represents the number of successes in the n trials.
- Possible values for the random variable X range from 0 to n.

Probability Mass Function (PMF):
- The PMF of a binomial distribution calculates the probability of obtaining a specific - number of successes (k) in n trials given the probability of success (p).


Shape:
- The shape of a binomial distribution is influenced by n and p.
- When the probability of success p is exactly 0.5, it represents a balanced scenario where success and failure are equally likely in each trial. In this case, the binomial distribution tends to be more symmetric and balanced. As p deviates from 0.5, the distribution becomes more skewed and exhibits different shapes based on the imbalance between the probabilities of success and failure.
- These values collectively characterize the binomial distribution and allow for the calculation of probabilities related to the number of successes in a fixed number of independent trials with a constant probability of success

##### Probability Based Mean and Standard Deviation Equation
Mean (Expected Value):
- The mean of a binomial distribution is given by mean = n * p.
- It represents the average number of successes expected in n trials.

Variance and Standard Deviation:
- The variance of a binomial distribution is given by variance = n * p * (1 - p).
- The standard deviation is the square root of the variance, providing a measure of the spread or variability of the distribution.


__NOTES__
This package was built using current guidelines as provided in (accessed April 2024): <br>
https://setuptools.pypa.io/en/latest/userguide/pyproject_config.html

Exert: 'Starting with PEP 621, the Python community selected pyproject.toml as a standard way of specifying project metadata. Setuptools has adopted this standard and will use the information contained in this file as an input in the build process'

A simple setup.py file script is also provided to allow for compatibility and prevent error messages occurring during local installation (e.g. test its functionality, verify dependencies, and ensure that it works as expected before publishing it to PyPI for wider distribution).

If using the functions to add two distribution curves together, visualisation of the combined plot is outside the scope of this package.


## Authors

Contributors names and contact info

Natasha Techwiz  <br>
natasha.techwiz@gmail.com

## Version History

- 1.0.0
    - Initial Release

## License

Refer to the LICENSE file for details


## Executing Program


```python
#code to create an example data set .txt file for a gaussian distribution
numbers_gaussian_test = [1, 3, 99, 100, 120, 32, 330, 23, 76, 44, 31]

#The .txt file should have one number (int or float) per line
# Write each number on a new line in the text file without adding an extra newline at the end
#this file will be saved to the same directory as your Python script or Jupyter Notebook
with open('numbers_gaussian_test.txt', 'w') as file:
    for i, num in enumerate(numbers_gaussian_test):
        file.write(str(num))
        if i < len(numbers_gaussian_test) - 1:
            file.write('\n')
```


```python
numbers_dec_gaussian_test = [2.447, 3.618, 3.064, 3.298, 1.091, 3.101, 2.99, 2.583, 2.442, 2.914, 3.381, 2.829, 2.441, 2.558, \
2.789, 2.178, 3.008, 2.708, 2.442, 1.637, 2.439, 1.97, 2.318, 2.78, 1.94, 2.4, 2.119, 1.69, 2.387, \
3.309, 2.791, 2.41, 2.267, 2.209, 2.026, 2.463, 1.962, 2.47, 2.398, 2.073, 2.063, 2.347, 2.072, \
1.913, 1.909, 3.258, 2.621, 2.344, 1.442, 2.949, 3.198, 2.314, 3.1, 2.846, 2.343, 2.986, 1.801, \
2.761, 1.728, 2.893, 3.133, 2.372, 3.272, 1.993, 2.204, 1.827, 2.161, 2.641, 2.343, 2.192, 2.573, \
2.269, 3.12, 2.323, 3.781, 3.278, 2.494, 1.998, 2.709, 3.372, 2.512, 2.328, 3.102, 4.688, 3.859, \
3.838, 3.963, 2.968, 2.882, 4.102, 2.757, 3.03, 3.333, 3.401, 2.843, 3.367, 2.793, 3.459, 2.704, 2.917]

#The .txt file should have one number (int or float) per line
# Write each number on a new line in the text file without adding an extra newline at the end
#this file will be saved to the same directory as your Python script or Jupyter Notebook
with open('numbers_dec_gaussian_test.txt', 'w') as file:
    for i, num in enumerate(numbers_dec_gaussian_test):
        file.write(str(num))
        if i < len(numbers_dec_gaussian_test) - 1:
            file.write('\n')

```


```python
#code to create an example data set .txt file for a binomial distribution
numbers_binomial_test = [0, 1, 1, 1, 1, 1, 0, 1, 0, 1, 0, 1, 0]

##The .txt file should have one number (typically int with values 0 or 1) per line
# Write each number on a new line in the text file without adding an extra newline at the end
#this file will be saved to the same directory as your Python script or Jupyter Notebook
with open('numbers_binomial_test.txt', 'w') as file:
    for i, num in enumerate(numbers_binomial_test):
        file.write(str(num))
        if i < len(numbers_binomial_test) - 1:
            file.write('\n')
```


```python
#perform some tasks using the file; numbers_dec_gaussian_test
#Create an instance of the Gaussian class without supplying values for mean and std dev 
#as this will be calculated based on the data set supplied
gaussian_dec = Gaussian()

# Read data from a file and calculate mean and standard deviation
gaussian_dec.read_data_file('numbers_dec_gaussian_test.txt')

# Calculate the mean
mean_value = gaussian_dec.calculate_mean()

# Calculate the standard deviation with sample=True
#when sample=TRUE for SAMPLE std dev the divisor formula is n-1
#when sample=FALSE for POPULATION std dev n is length|total data points
stdev_value = gaussian_dec.calculate_stdev(sample=True)

# Use the __repr__ function - print mean and std dev of the data set
print(repr(gaussian_dec)) #Output- mean 2.66, standard deviation 0.61

# Plot a histogram of the data
gaussian_dec.plot_histogram()

```


```python
# Confirm that the initial histogram plot approximates to a bell curve 
#characteristic of a gaussian distribution
# If yes, calculate PDF. If no, you will need to employ a different technique on the data set

# Calculate the probability density function at a specific point/x value
x_value = 2.5 #Output- PDF at x=2.5: 0.63
pdf_value = gaussian_dec.pdf(x_value)
rounded_pdf_value = round(pdf_value, 2)
print(f'PDF at x={x_value}: {rounded_pdf_value}')

# Plot the normalized histogram and the PDF along the same range
#When you increase the n_spaces value, you are essentially increasing 
#the resolution or granularity of the plot. More points will be evaluated 
#along the x-axis, resulting in a smoother representation of the normal distribution curve
gaussian_dec.plot_histogram_pdf(n_spaces=10)

#a tuple with two lists will also be printed after gaussian_dec.plot_histogram_pdf
#The first list represents the x-values or bin edges for the histogram bins.
#The second list represents the y-values or heights for the corresponding histogram bins, 
#which are the probabilities or frequencies associated with each bin
```


```python
#to just get SAMPLE mean and std dev for the file; numbers_gaussian_test.txt
# Create an instance of the Gaussian class
gaussian_whole = Gaussian()

# Read data from a file 
gaussian_whole.read_data_file('numbers_gaussian_test.txt')

# Calculate the mean
mean_value = gaussian_whole.calculate_mean()

# Calculate the standard deviation with sample=True
stdev_value = gaussian_whole.calculate_stdev(sample=True)

print("Mean:", round(mean_value, 2)) # Output- Mean: 78.09
print("Standard Deviation:", round(stdev_value, 2)) # Output- Standard Deviation: 92.87
```


```python
#Add two gaussian plots
gaussian_sum = gaussian_dec + gaussian_whole
# Use the __repr__ function - print mean and std dev of the combined data set
print(repr(gaussian_sum)) # Output- mean 2.66, standard deviation 1.17
```


```python
#Initialise a binomial class with values for prob and size
binomial = Binomial(0.4, 20)
#check class initiates correctly
print(binomial.p)  # Output: 0.4
print(binomial.n)  # Output: 20
```


```python
#Replace Stats using data file; numbers_binomial_test.txt
binomial.read_data_file('numbers_binomial_test.txt')
p, n = binomial.replace_stats_with_data()
print(round(p, 3))  # Output: 0.615
print(n)  # Output: 13
```


```python
#PMF Calculations
#generate pmf without associating a data set 
binomial2 = Binomial(prob=0.4, size=20)
print(round(binomial2.pmf(5), 5))  # Output: 0.07465
print(round(binomial2.pmf(3), 5))  # Output: 0.01235

#generate pmf again, this time associating a data set which will change the output
binomial2.read_data_file('numbers_binomial_test.txt')  # Load data from file
binomial2.replace_stats_with_data()
print(round(binomial2.pmf(5), 5))  # Output: 0.05439
print(round(binomial2.pmf(3), 5))  # Output: 0.00472
```


```python
# Generate a bar plot of the data outcomes
binomial2.plot_bar()
```


```python
#Generate a PMF bar plot of the data
binomial2.plot_bar_pmf()

#a tuple with two lists will also be printed after binomial2.plot_bar_pmf()
#The x-axis represents the possible values of the random variable for which 
#the PMF is being calculated
#y-axis of a PMF chart represents the probability mass 
#(likelihood of a particular outcome occurring) associated with each value 
#of the random variable on the x-axis

```


```python
#Add two binomial distributions
binomial_one = Binomial(0.4, 20)
binomial_two = Binomial(0.4, 60)
binomial_sum = binomial_one + binomial_two
print(binomial_sum.p)  # Output: 0.4
print(binomial_sum.n)  # Output: 80
```


```python
# Add the two instances together and directly access the n 
#attribute of the resulting distribution
print((binomial_one + binomial_two).n) #Output: 80 
```


```python
#Use the __repr__ function - print mean, std dev, p and n of the data set
print(repr(binomial_one)) #Output: mean 8.0, standard deviation 2.19, p 0.4, n 20
print(repr(binomial_two)) #Output: mean 24.0, standard deviation 3.79, p 0.4, n 60
```



