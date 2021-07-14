# Code Commenting - Level 6 <!-- omit in toc -->

## 1. Table of Contents

- [1. Table of Contents](#1-table-of-contents)
- [2. Introduction](#2-introduction)
- [3. API Documentation](#3-api-documentation)
  - [3.1. Why Document APIs?](#31-why-document-apis)
  - [3.2. How to Document your API](#32-how-to-document-your-api)
- [4. References](#4-references)

## 2. Introduction

The question most people ask is "Why do we need code comments anyway?"

Code commenting is a very simple way to let someone know what your code is meant to be doing, even if their background in code is weak. Good comments make for easy reading and easy understanding for those who are perhaps not as tech savvy as yourself. Code commenting also explains why you wrote something. At Level 6, the expectation is that you will write concise and informative code comments that follow coding standards outlined in the Level 5 Code Commenting Document for the specific programming language you are working in. The document can be found [here](../level-5/level5-code-commenting.md).

These are meant for anyone who is likely to consume your source code, but they aren't likely to read through it in any real depth. Code comments are also used by different tools for automatic generation of documentation.
If you are building something such as a **Library** or **Framework** that you would expect other developers to be using, then you need some form of documentation alongside that, with which comments help the basis of understanding.

It is worth mentioning that several organisations, and open source projects, define specific code style guidelines that must be adhered to.
If they don’t, however, or you are on your own, keeping this stuff in mind will not only make your job easier in the future, but will also help out anyone who comes after you, too.

More information on basic code commenting can be found in the Level 4 Code Commenting Document found [here](../level-4/level4-code-commenting.md).  

## 3. API Documentation

API documentation is a technical content deliverable, containing instructions about how to effectively use and integrate with an API. It’s a concise reference manual containing all the information required to work with the API, with details about the functions, classes, return types, arguments and more, supported by tutorials and examples. API Documentation has traditionally been done using regular content creation and maintenance tools and text editors.

### 3.1. Why Document APIs?

Documentation is very important, even for APIs. Documentation is also an area that is showing a lot of growth now, the need for documentation for your API is starting to become even more important than it ever has been before. It is easier to implement code, than it is to write good documentation. This is because of its direct impact, growing adoption and usage. At level 6, you will need to create documentation for any APIs that you create for your projects.  
But why do you need to do this anyway? Lets take an example from a popular Machine Learning Library API used within Python: SKLearn. Here is an example of code using guidelines specified on the SKLearn documentation, this gives the user guidelines they should follow when writing code using their Library/API, The API documentation can be found [here](https://scikit-learn.org/stable/developers/develop.html#coding-guidelines).

```python
from sklearn.utils import check_array, check_random_state

def choose_random_sample(X, random_state=0):
    """Choose a random point from X.

    Parameters
    ----------
    X : array-like of shape (n_samples, n_features)
        An array representing the data.
    random_state : int or RandomState instance, default=0
        The seed of the pseudo random number generator that selects a
        random sample. Pass an int for reproducible output across multiple
        function calls.
        See :term:`Glossary <random_state>`.

    Returns
    -------
    x : ndarray of shape (n_features,)
        A random point selected from X.
    """
    X = check_array(X)
    random_state = check_random_state(random_state)
    i = random_state.randint(X.shape[0])
    return X[i]
```

The benefits of good documentation, especially in your time after University and in the workplace are:

- **Improved User Adoption** - A big reason for having documentation in the first place is that you want users to adopt your software. API documentation improves the experience of developers using your API, which has a direct **correlation** on API adoption. People adopt products that they enjoy using (and that they find easy to troubleshoot)

- **Increased Awareness** - Users beget users. Networking is the most prominent phenomenon of the western market, good networking means stronger possibility to promote your API, leading to increased awareness. Good documentation further improves upon this concept. Don't you always recommend a good product to a friend? Think like that in this instance too, its the same deal

- **Saves Support Time and Costs** - Poor or no documentation leads to more frustrated users relying on your team (or yourself) to understand how to work with your API. On the contrary, when you give users the ability to try out the API before implementing it, and arm them with detailed documentation to get started, you’ll save your team (and yourself) countless hours responding to support emails and calls

- **Easier Maintenance** - Good documentation leads to good product maintenance. It helps your internal teams know the details of your resources, methods, and their associated requests and responses. A popular way that 3rd party developers get help on fixing issues in their API is through using Github to host and allow other developers to fix issues within their software

### 3.2. How to Document your API

There are a number of ways you can document your API. It really depends on which method of API design you have decided on. If you are building your API from scratch, then [**OpenAPI**](http://spec.openapis.org/oas/v3.0.3) is a useful tool in helping to automate the process, which will make things easier for you  

When it comes to using API description formats, two important schools of thought have emerged, **Design First** and **Code First**. **Code First** is a more traditional style and approach to developing your API, where you develop the code before the API documentation itself, with **Design First** being the absolute opposite. For Level 6, exploration of **Design First** is recommended if it makes sense to use it, but if you are not comfortable with this idea or it is not suitable, then sticking with the more traditional approach is fine too, as long as where necessary you explain your approach direction and justify *why* you chose this approach. The **Design First** approach is generally a newer approach and thus doesn't have as extensive a background as the traditional approach of **Code First** does.

Choose **Design First** if:

- Developer Experience Matters
- Delivering Mission Critical APIs
- You Need To Ensure Good Communication  

Choose **Code First** if:

- Delivery Speed Matters
- Developing Internal APIs

If you want to choose one of these approaches, how do you decide which approach is going to work best for you though?  

- Design First - The plan is converted to a human and machine readable contract, from which the code is built
- Code First   - Based on the business plan, API is directly coded, from which a human or machine readable document can be generated  
An image showing the approaches compared against each other is included (see figure 1).

![Design First vs Code First](https://static1.smartbear.co/swagger/media/blog/wp/designvscode.jpg)  
*Figure 1: Swagger.io Design First vs Code First*

## 4. References

[What is API Documentation, and why it matters: Swagger.io Blog](https://swagger.io/blog/api-documentation/what-is-api-documentation-and-why-it-matters/)  
[SKLearn: Developing scikit-learn estimators - Coding Guidelines section](https://scikit-learn.org/stable/developers/develop.html#coding-guidelines)  
[OpenAPI Specification version 3.0.3.](http://spec.openapis.org/oas/v3.0.3)  
[Design First or Code First: What's the best approach to API Development?](https://swagger.io/blog/api-design/design-first-or-code-first-api-development/)  
