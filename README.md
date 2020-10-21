## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/danma9023/danma.github.io/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

## Getting Started

The purpose of this document is to illustrate some of the main working flows as well as the key self-designed python libraries used for the Average Price Table (APT) project. This project aims to derive and publish the average price of the grocery goods for statistical inference and other purposes. The outcome of this project can be found [here](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1810000201). In short, this project envolves the collection of the grocery purchase data and classification of these records for the final average price calculation. The focus of this document will be the classification flow of APT and the main python libraries (`classification_utils` \& `general_utils`) and used in this process. 

## Working Flow
## General Introduction
The goal of the classification task is to classify the grocery records into the right Elementary Aggregate (EA), where the EA is APT labels here. The main model used for classification is [Support Vector Machine](https://en.wikipedia.org/wiki/Support_vector_machine) (SVM). This model has been tested and proved to be the optimal model for the classification task with excellent performance. For example, the job could be classify the product "Women's Skirt with Rose Pattern" into "Women's bottom" category. This project runs monthly with collected data from the retailers every month. More details about the working process of this task is shown below:

## 1.Data 
The data are mainly monthly scanner data from several of the main retailer in Canada. The data is at the product level. Scanner data includes retail purchase information (such as price, brand, product size, amount purchased) gathered at the point of purchase by an electronic device that reads a coded ticket on the product through the use of an electronic reader over which the product passes. The text information of the products are the key features used for the classification. These features include product description, product category, product name and different level of desctiptions (e.g. 1_DESC_EN, LVL2_ENG_DESC). The product category is the targe tfeature that one tries to classifies into. 

## 2. Data Processing
This steps envolves cleaning and processing the text features. The main work done in this step is:
1. Eliminate irrevelant text, such as stop_words and non-alphabetic signs. Specificially, this is achieved through the `data_cleaning` function nested in the `classification_utils` library. 
2. `sklearn.feature_extraction.text.TfidfVectorizer()` then is used for text feature transformation into numerical features that can be used for SVM model classification.

```markdown
Syntax highlighted code block



The data used for APT classification 
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/danma9023/danma.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
