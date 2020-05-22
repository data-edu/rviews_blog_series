Teaching R Using Everyday Examples in Education
================
Ryan Estrellado
5/21/2020

Timothy Gallwey wrote in *The Inner Game of Tennis*, “What I have tried
to illustrate is that there is a natural learning process which operates
within everyone, if it is allowed to. This process is waiting to be
discovered by all those who do not know of its existence … It can be
discovered for yourself, if it hasn’t been already. If it has been
experienced, trust it.” I learn new R concepts first by discovering
them, but it doesn’t click until I see somebody use it. For example, I
learned about random forest models when I read about them in [An
Introduction to Statistical Learning
(ISL)](https://www.amazon.com/Introduction-Statistical-Learning-Applications-Statistics/dp/1461471370).
Then I imagined myself using them when I watched [Julia Silge fit a
random forest model](https://youtu.be/LPptRkGoYMg) to predict attendance
at NFL games. I need the reading to give me language for what I see data
scientists do. Then I need to see what data scientists do for me to
imagine myself doing what I’ve read.

Still, for most people using R in their jobs, there’s another step. They
have to imagine how to apply what they’ve read and seen to the problems
they’re solving at work. But what if we used education datasets to help
them imagine using R on the job, just as the authors of ISL use words
and code to teach about models and Julia Silge uses video to inspire
coding?

We learned from writing [*Data Science in Education Using R
(DSIEUR)*](https://datascienceineducation.com) that we can combine
words, code, and professional context. Professional context includes
scenarios, language, and data that readers will recognize in their
education jobs. We wanted readers to feel motivated and engaged by
seeing words and data that reminds them of their everyday work tasks.
This connection to their professional lives is a hook for readers as
they engage R syntax which is, if you’ve never used it, literally a
foreign language.

Let’s use `pivot_longer()` as an example. We’ll describe this process in
three steps: discovering the concept, seeing how the concept is used,
and seeing how the concept is used *in education*.

**Step 1: See the concept**

When I read something like “Use `pivot_longer()` to transform a dataset
from wide format to long format”, I can imagine a dataset going from
wide to long. Imagining what happens with the variables and their
contents is much harder. I’ve been using R for over five years and I’d
still struggle to visualize the contents of many columns rearranging
themselves into one.

**Step 2: See how the concept is used**

The concept gets much clearer when you add an example–even one with
little context–to the explanation. Here’s one from the `pivot_longer()`
vignette, which you can view with `vignette("pivot")`:

``` r
library(tidyverse)
```

``` r
# Simplest case where column names are character data
relig_income
```

    #> # A tibble: 18 x 11
    #>    religion `<$10k` `$10-20k` `$20-30k` `$30-40k` `$40-50k` `$50-75k` `$75-100k`
    #>    <chr>      <dbl>     <dbl>     <dbl>     <dbl>     <dbl>     <dbl>      <dbl>
    #>  1 Agnostic      27        34        60        81        76       137        122
    #>  2 Atheist       12        27        37        52        35        70         73
    #>  3 Buddhist      27        21        30        34        33        58         62
    #>  4 Catholic     418       617       732       670       638      1116        949
    #>  5 Don’t k…      15        14        15        11        10        35         21
    #>  6 Evangel…     575       869      1064       982       881      1486        949
    #>  7 Hindu          1         9         7         9        11        34         47
    #>  8 Histori…     228       244       236       238       197       223        131
    #>  9 Jehovah…      20        27        24        24        21        30         15
    #> 10 Jewish        19        19        25        25        30        95         69
    #> 11 Mainlin…     289       495       619       655       651      1107        939
    #> 12 Mormon        29        40        48        51        56       112         85
    #> 13 Muslim         6         7         9        10         9        23         16
    #> 14 Orthodox      13        17        23        32        32        47         38
    #> 15 Other C…       9         7        11        13        13        14         18
    #> 16 Other F…      20        33        40        46        49        63         46
    #> 17 Other W…       5         2         3         4         2         7          3
    #> 18 Unaffil…     217       299       374       365       341       528        407
    #> # … with 3 more variables: `$100-150k` <dbl>, `>150k` <dbl>, `Don't
    #> #   know/refused` <dbl>

``` r
relig_income %>%
 pivot_longer(-religion, names_to = "income", values_to = "count")
```

    #> # A tibble: 180 x 3
    #>    religion income             count
    #>    <chr>    <chr>              <dbl>
    #>  1 Agnostic <$10k                 27
    #>  2 Agnostic $10-20k               34
    #>  3 Agnostic $20-30k               60
    #>  4 Agnostic $30-40k               81
    #>  5 Agnostic $40-50k               76
    #>  6 Agnostic $50-75k              137
    #>  7 Agnostic $75-100k             122
    #>  8 Agnostic $100-150k            109
    #>  9 Agnostic >150k                 84
    #> 10 Agnostic Don't know/refused    96
    #> # … with 170 more rows

Sharing an idea by pairing an abstract programming concept with a
reproducible example is a common practice for experienced R programmers.
[Community guidelines for Stack Overflow
posts](https://stackoverflow.com/questions/5963269/how-to-make-a-great-r-reproducible-example)
and the [{reprex}](https://www.tidyverse.org/help/) package are two
artifacts of a popular R community norm: help folks understand an idea
by using words *and* code.

**Step 3: See how the concept is used in education**

Combining the explanation and a reproducible example makes
`pivot_longer()` more concrete by showing how it works. What happens
when we connect the explanation and reproducible example to the everyday
work of a data scientist in education?

In [chapter seven](https://datascienceineducation.com/c07.html) of
*DSIEUR*, we used `pivot_longer()` to transform a dataset of survey
responses from wide to narrow. Before using `pivot_longer()`, the
dataset had a column for each survey question. After using
`pivot_longer()`, the name of each survey question moved to a single
column called “question”. Another new column was added, “response”,
which contains the corresponding response to each survey question.

To run this code, you’ll need the *DSIEUR* companion R package,
[{dataedu}](https://github.com/data-edu/dataedu):

``` r
# Install the {dataedu} package if you don't have it
# devtools::install_github("data-edu/dataedu")
library(dataedu)
```

View the survey data in its original, wide format:

``` r
# Wide format
pre_survey
```

    #> # A tibble: 1,102 x 12
    #>    opdata_username opdata_CourseID Q1Maincellgroup… Q1Maincellgroup…
    #>    <chr>           <chr>                      <dbl>            <dbl>
    #>  1 _80624_1        FrScA-S116-01                  4                4
    #>  2 _80623_1        BioA-S116-01                   4                4
    #>  3 _82588_1        OcnA-S116-03                  NA               NA
    #>  4 _80623_1        AnPhA-S116-01                  4                3
    #>  5 _80624_1        AnPhA-S116-01                 NA               NA
    #>  6 _80624_1        AnPhA-S116-02                  4                2
    #>  7 _80624_1        AnPhA-T116-01                 NA               NA
    #>  8 _80624_1        BioA-S116-01                   5                3
    #>  9 _80624_1        BioA-T116-01                  NA               NA
    #> 10 _80624_1        PhysA-S116-01                  4                4
    #> # … with 1,092 more rows, and 8 more variables: Q1MaincellgroupRow3 <dbl>,
    #> #   Q1MaincellgroupRow4 <dbl>, Q1MaincellgroupRow5 <dbl>,
    #> #   Q1MaincellgroupRow6 <dbl>, Q1MaincellgroupRow7 <dbl>,
    #> #   Q1MaincellgroupRow8 <dbl>, Q1MaincellgroupRow9 <dbl>,
    #> #   Q1MaincellgroupRow10 <dbl>

… and now transform the survey dataset to a long format, where a column
called “question” contains the question names and a column called
“response” contains the corresponding responses:

``` r
# Pivot the dataset from wide to long format
pre_survey %>%
  pivot_longer(cols = Q1MaincellgroupRow1:Q1MaincellgroupRow10,
               names_to = "question",
               values_to = "response")
```

    ## # A tibble: 11,020 x 4
    ##    opdata_username opdata_CourseID question             response
    ##    <chr>           <chr>           <chr>                   <dbl>
    ##  1 _80624_1        FrScA-S116-01   Q1MaincellgroupRow1         4
    ##  2 _80624_1        FrScA-S116-01   Q1MaincellgroupRow2         4
    ##  3 _80624_1        FrScA-S116-01   Q1MaincellgroupRow3         4
    ##  4 _80624_1        FrScA-S116-01   Q1MaincellgroupRow4         1
    ##  5 _80624_1        FrScA-S116-01   Q1MaincellgroupRow5         5
    ##  6 _80624_1        FrScA-S116-01   Q1MaincellgroupRow6         4
    ##  7 _80624_1        FrScA-S116-01   Q1MaincellgroupRow7         1
    ##  8 _80624_1        FrScA-S116-01   Q1MaincellgroupRow8         5
    ##  9 _80624_1        FrScA-S116-01   Q1MaincellgroupRow9         5
    ## 10 _80624_1        FrScA-S116-01   Q1MaincellgroupRow10        5
    ## # … with 11,010 more rows

When you put it all together, the learning thought process is something
like this:

  - There’s a function called `pivot_longer()`, which turns a wide
    dataset into a long dataset
  - `pivot_longer()` does this by putting multiple column names into its
    own column, then creating a new column that pairs each column name
    with a value
  - I can use `pivot_longer()` to change an education survey dataset
    that has question names for columns into one that has a “question”
    column and a “response” column

We’ll be back with the next post in about two weeks. Until then, do
share with us about the people and tools that inspire you to work on
collaborative projects. You can reach us on Twitter: Emily
\[@ebovee09\](<https://twitter.com/ebovee09>), Jesse
\[@kierisi\](<https://twitter.com/kierisi>), Joshua
\[@jrosenberg6432\](<https://twitter.com/jrosenberg6432>), Isabella
\[@ivelasq3\](<https://twitter.com/ivelasq3>), and me
\[@RyanEs\](<https://twitter.com/RyanEs>).
