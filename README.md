
# More Pandas

![more_pandas](https://media.giphy.com/media/H0Qi5W2KzU5UI/giphy.gif)

### Scenario
You have decided that you want to start your own animal shelter, but you want to get an idea of what that will entail and to get more information about planning. In this lecture, we'll look at a real data set collected by Austin Animal Center.  The code below will return the last 1000 animal outcomes that have occurred.  We will use our pandas skills from the last lecture and learn some new ones in order to explore these data further.




#### Our goals in this notebook are to be able to: <br/>

- Apply and use `.map()`, `apply()`, and `.applymap()` from the Pandas library
- Introduce lambda functions and use them in coordination with above functions
- Explain what a groupby object is and split a DataFrame using `.groupby()`


#### Getting started

Let's take a moment to download and to examine the [Austin Animal Center data set](https://data.austintexas.gov/Health-and-Community-Services/Austin-Animal-Center-Outcomes/9t4d-g238/data). 

Let's take a look at the data:

One way to become familiar with your data is to start asking questions. In your EDA notebooks, **markdown** will be especially helpful in tracking these questions and your methods of answering the questions.  

For example, a simple first question we might ask, after being presented with the above dataset, would be:

## What is the most commonly adopted animal type in the dataset?

We can then begin thinking about what parts of the DataFrame we need to answer the question.

    What features do we need?
     - 
    What type of logic and calculation do we perform?
     -  
    What type of visualization would help us answer the question?
     -

Questions lead to other questions. For the above example, the visualization begs the question, what Other animals are being adopted?

To find out, we need to know where the type of animal for Other is encoded.   
    
    What features do we need to answer what the most commonly adopted type of animal within the Other category is?

# Quick Exploration

Use fillna to fill animals with no name to 'unnamed'


```python
animals['name'] = animals['name'].fillna('unnamed')
```

### Applying and using map and applymap from the Pandas library

The built in **map** operator takes a function and applies it to every element of an iterable

The Pandas library has several similar methods associated with Dataframes and Series. Let's explore them.

# DataFrame.applymap(), Series.map()  Series.apply()

## DataFrame.applymap()
The ```.applymap()``` method takes a function as input that it will then apply to every entry in the dataframe.

# Series.map()

The **.map()** method takes a function as input that it will then apply to every entry in the Series.

Let's map a ternary class set to consolodate sex_upon_outcome to male, female, or unknown   

First, explore the unique values:

# Series.apply()

Series.apply() is similar to .map, except it only takes a function as a parameter, whereas .map can take a list, dictionary, or function.  .apply() is meant for more complex functions.

Now let's define a custom function that converts all ages upon outcome to days, and create a new column with .apply():

# Pair program #1: 
Take 10 minutes to fill in the function below with code that converts age upon outcome to days upon outcome.

Now, fill in the definition below to convert the ages to days

### Anonymous Functions (Lambda Abstraction)

Simple functions can be defined right in the function call. This is called 'lambda abstraction'; the function thus defined has no name and hence is "anonymous".

# Student Screen Share
Use another lambda function to convert days days upon outcome to weeks upon outcome <br>


# Methods for Re-Organizing DataFrames: .groupby()

Those of you familiar with SQL have probably used the GROUP BY command. (And if you haven't, you'll see it very soon!) Pandas has this, too.

The .groupby() method is especially useful for aggregate functions applied to the data grouped in particular ways.

Notice the object type [DataFrameGroupBy](https://pandas.pydata.org/pandas-docs/stable/user_guide/groupby.html) object. 

#### .groups and .get_group()

Once we know we are working with a type of object, it opens up a suite of attributes and methods. One attribute we can look at is groups.

We can group by multiple columns, and also return a DataFrameGroupBy object

#### Aggregating
