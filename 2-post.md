Open-Source Authorship of Data Science in Education Using R
================
Joshua Rosenberg
6/28/2020

*Joshua M. Rosenberg, Ph.D., is Assistant Professor of STEM Education
and the University of Tennessee, Knoxville.*

In earlier posts, we wrote about how we wrote [*Data Science in
Education Using R*](http://datascienceineducation.com/) as an open book
([Post 1](https://rviews.rstudio.com/2020/05/26/community-and-collaboration-writing-our-book-in-the-open/),
[Post 2](https://rviews.rstudio.com/2020/06/11/learning-r-with-education-datasets/)).
In this post, we describe what we consider to be the open-source
authorship process we took to write the book.

We think of *open-source authorship* as a broader—and perhaps
better\!—term for describing what authors of some (especially data
science-related) open books undertake. Open-source authorship draws upon
open-source software (OSS) values and components of open science that
establish the importance of scholarly work beyond original, discovery
research, while simultaneously promoting the spirit of open educational
resources (OER). While OSS and open science emphasize the sharing of
technical work (including technology and code) and OER emphasizes the
sharing of resources, technical books have not been as much a focus of
the conversation.

The way in which the conversation about open books has taken place in
different communities and contexts means that some books that are open
do not fully receive the attention (for being openly available) that
they merit from those interested in OER. This also might mean that those
involved with OSS development and open science may fail to recognize the
creation of a book as a substantial contribution. In this way, we argue
for open-source authorship as an important, new type of work, one that
we increasingly see by the authors of other books, especially in the R
community<sup>\[<https://bookdown.org/yihui/rmarkdown/>\]
</sup>\[<https://geocompr.robinlovelace.net/>\]
<sup>\[<http://adv-r.had.co.nz/>\] </sup>\[<https://r4ds.had.co.nz/>\].
After describing how we wrote our book in an open way, we elaborate on
what we consider these ideas that inform open-source authorship.

## How We Wrote Data Science in Education Using R as an Open Book

### Available to Access from the Start to the Finish

Early in our process, we determined that we wanted to share the book in
an open way. Since we were using GitHub as a [repository for the
book](https://github.com/data-edu/data-science-in-education/), it was
easy for the contents of the book to be available for anyone to
view–even before and as the book was being written. Despite the
benefits of using GitHub, GitHub can be difficult to navigate for those
who are unfamiliar with it, and so sharing the book in a more
widely-accessible way was also important. To do this, we used
[bookdown](https://bookdown.org/) and
[Netlify](https://www.netlify.com/) to share the book as a website.
Additionally, we chose an easy-to-remember URL
(<http://datascienceineducation.com/>) to help others (and us\!) to be
able to access it easily.

### Available to Contribute To

Being available for others to contribute was important. Because we used
GitHub, we were able to receive feedback at a very early-stage on
[issues such as how we referred to data (as data or
datum)](https://github.com/data-edu/data-science-in-education/issues/20).
Other [issues (by non-authors) raised questions about whether certain
content was in scope—such as content on
gradebooks](https://github.com/data-edu/data-science-in-education/issues/9),
which we included a chapter on. We found that apart from the five of us
as authors, 15 individuals made contributions, and another 144
individuals starred the repository\[1\]. Moreover, we received feedback
through Twitter and an email account we created for the book for those
unfamiliar with GitHub (or Twitter) to be able to provide feedback
directly to us. In this way, making the book available to contribute to
made the book better, and points to the importance of sharing work at
only one stage of the writing process.

### Open in its Entirety

Lastly, we shared products that could be seen as tangential to the book,
but which were important given its focus on data science and R. Namely,
we created an R package,
[{dataedu}](https://data-edu.github.io/dataedu/), to accompany the book.
This package includes code to install the packages necessary to
reproduce the book as well as all of the data sets used in it. By doing
so, we invited others to contribute to the book in ways not related to
its prose. This also led to surprising contributions by others,
including the creation of [an iPython Notebook with python code to carry
out comparable steps as those carried in a walkthrough chapter of our
book](https://colab.research.google.com/drive/1f7CpetOWP9T2XaJCNrcwWj3CMKsQNmtw).

## Drawing Inspiration from Other, Related Ideas and Efforts

### Open-Source Software (OSS)

Originally a niche effort, open-source software (OSS) and OSS
development are now widespread \[2\]. There are some insights that can
be gained from efforts to understand how OSS development proceeds. For
example, in foundational, work Mockus et al. found that OSS is often
characterized by a core group of 10-15 individuals contributing around
80% of the code, but that a group an order of magnitude larger than that
core will repair specific problems, and a group another order of
magnitude larger will report issues\[3\]; proportions (generally)
similar to those we found for those who contributed to our book.

### Open Science

Open science is both a perspective about how science should operate and
a set of practices that reflect a perspective about how science should
proceed
<sup>\[<https://www.nap.edu/catalog/25116/open-science-by-design-realizing-a-vision-for-21st-century>\]
</sup>\[<https://journals.sagepub.com/doi/full/10.1177/2332858418787466>\].
Related to open science is open scholarly practices. Others trace the
origin of the idea of open scholarly practices to [a book by
Boyer](https://eric.ed.gov/?id=ED326149), who shared a broad description
of the work academics do. This suggests that scholarly work is not only
original, discovery research; it also includes the applications of
advances in one’s own discipline (or “translational research”) and
sharing the results of research with multiple stakeholders. Open science
and open scholarly practices point to the scientific or scholarly
contributions of open books; while different from original, scientific
research, books such as our own—which focused on providing a language
for data science in education—may serve as helpful examples (of open
science) or forms of a broader view of scholarship.

### Open Educational Resources (OER)

OER are “teaching, learning, and research resources that reside in the
public domain or have been released under an intellectual property
license that permits their free use and re-purposing by others” \[4\].
These resources range from courses and books to tests and technologies.
By being open, they are not only available to others to use, but also to
reuse, redistribute (or share), revise (adapt or change the work), and
remix (combining existing resources to create a new one) \[5\]. OER can
serve as an inspiration for authors of open books, especially those who
see their books as being used to teach and learn from. At the moment,
OER and traditional publishing modes are largely separate: For most
books that are published, the publisher retains the copyright, and
authors are typically not allowed to share their book in the open,
though this may be changing. Many authors of books about R have
negotiated with their publisher to share their books in the open (often
as a website) in addition to sharing them through print and e-book
formats: this was the agreement we reached with our editor. In addition
to these “hybrid” modes of publishing, a number of platforms for
creating books that are OER are emerging; one example is [EdTech
Books](https://edtechbooks.org). There are increasing conversations
related to making materials, resources, and even education as an
enterprise more open; OER may be an area in which authors of books about
R and other technical books can both learn from the work of authors as
well as advance the conversation.

## *fin*

This post was an effort to step back from what we did to write our book
to reflect on what we meant by writing an open book and to attempt to
situate what we did (and what others have done) in broader conversations
about OSS, open science, and OER. In the spirit of one of the sets of
ideas we highlighted here—OER—we invite others to revise and remix the
ideas we advanced to continue to innovate around the process of writing
books in better ways.

You can reach us on Twitter: Emily
\[@ebovee09\](<https://twitter.com/ebovee09>), Jesse
\[@kierisi\](<https://twitter.com/kierisi>), Joshua
\[@jrosenberg6432\](<https://twitter.com/jrosenberg6432>), Isabella
\[@ivelasq3\](<https://twitter.com/ivelasq3>), and me
\[@RyanEs\](<https://twitter.com/RyanEs>).

See you in two weeks\! Josh, with help from Ryan, Emily, Jesse, Joshua,
and Isabella

  - *Ryan A. Estrellado is a public education leader and data scientist
    helping administrators use practical data analysis to improve the
    student experience.*

  - *Emily A. Bovee, Ph.D., is an educational data scientist working in
    dental education.*

  - *Jesse Mostipak, M.Ed., is a community advocate, Kaggle educator and
    data scientist.*

  - *Isabella C. Velásquez, MS, is a data analyst committed to nonprofit
    work with the aim of reducing racial and socioeconomic inequities.*

<!-- end list -->

1.  <https://joshuamrosenberg.com/posts/data-science-in-education-using-r-by-and-beyond-the-numbers/>

2.  <https://books.google.com/books?hl=en\&lr=\&id=bjMsCKvV9I4C\&oi=fnd\&pg=PR5\&dq=DIBONA,+C>.,+OCKMAN,+S.,+AND+STONE,+M.+1999.+Open+Sources:+Voices+from+the+Open+Source+Revolution.+O%E2%80%99Reilly,+Sebastopol,+Calif.\&ots=D\_l\_LXcDtB\&sig=zu1hkYJlSrqCUaxe3nYbProHlg8

3.  <https://dl.acm.org/doi/abs/10.1145/567793.567795>

4.  <https://hewlett.org/strategy/open-education/>

5.  <https://www.tandfonline.com/doi/full/10.1080/02680510903482132?casa\_token=S0sRaVJZiA4AAAAA%3ABO-fx7uNOQoNEdXl5-aQ8ooYpfTFohZdefU-ZJROwFDo3XL-W2oAbaOb3Un\_DwRItNN4gj8eBXUo9A>
