# ==OPEN==

- [ ] cv up to date
  - [ ] `cv.md` header += `cv_pdf: cv.pdf`
  - [ ] `\_layouts\cv.html` wieder einkommentieren
- [ ] News entries
- [ ] Projects
- [ ] Dr beim Namen
- [ ] Paper preprints hochladen



# deploy

- git checkout main

- build container from their dockerfile, but mount docs(local) auf deren /srv/jekyll  WORKDIR folder

- run deploy script

- Push to gh-pages branch!

```
bundle install
export JEKYLL_ENV=production
bundle exec jekyll build --lsi

# Delete and move files
find . -maxdepth 1 ! -name '_site' ! -name '.git' ! -name 'CNAME' ! -name '.gitignore' -exec rm -rf {} \;
mv _site/* .
rm -R _site/

# Create `.nojekyll` file (bypass GitHub Pages Jekyll processing)
touch .nojekyll

# Push to DEPLOY_BRANCH
git add -fA
git commit --allow-empty -m "$(git log -1 --pretty=%B) [ci skip]"
[[ ${NO_PUSH} ]] || git push -f -q origin $DEPLOY_BRANCH

# Move back to SRC_BRANCH
git checkout $SRC_BRANCH

```



# General

markdown + javascript



Header Syntax: 

```
---
layout: post
title: a post with giscus comments
date: 2022-12-10 11:59:00-0400
description: an example of a blog post with giscus comments
subtitle: bal basdfslusd
tags: formatting links
categories: sample-posts external-services
giscus_comments: false
related_posts: false
redirect: /assets/pdf/example_pdf.pdf
---
```

Zeilen weglassen wenn nicht gewünscht!



wenn in navigation-bar enthalten: 

```
nav: true
nav_order: 1
```





## blog posts and news

### lightweight, on start page

`_news/XXX.md`

> Announcements and news can be much longer than just quick inline posts. In fact, they can have all the features available for the standard blog posts. See below. **(announcent_2 in template)**

```
---
layout: post
title: A long announcement with details
date: 2015-11-07 16:11:00-0400
inline: false
related_posts: false
---

Announcements and news can be much longer than just quick inline posts. In fact, they can have all the features available for the standard blog posts. See below.

***

Jean shorts raw denim Vice normcore, art party High Life PBR skateboard stumptown vinyl kitsch. Four loko meh 8-bit, tousled banh mi tilde forage Schlitz dreamcatcher twee 3 wolf moon. Chambray asymmetrical paleo salvia, sartorial umami four loko master cleanse drinking vinegar brunch. <a href="https://www.pinterest.com">Pinterest</a> DIY authentic Schlitz, hoodie Intelligentsia butcher trust fund brunch shabby chic Kickstarter forage flexitarian. Direct trade <a href="https://en.wikipedia.org/wiki/Cold-pressed_juice">cold-pressed</a> meggings stumptown plaid, pop-up taxidermy. Hoodie XOXO fingerstache scenester Echo Park. Plaid ugh Wes Anderson, freegan pug selvage fanny pack leggings pickled food truck DIY irony Banksy.

#### Hipster list
<ul>
    <li>brunch</li>
    <li>fixie</li>
    <li>raybans</li>
    <li>messenger bag</li>
</ul>

Hoodie Thundercats retro, tote bag 8-bit Godard craft beer gastropub. Truffaut Tumblr taxidermy, raw denim Kickstarter sartorial dreamcatcher. Quinoa chambray slow-carb salvia readymade, bicycle rights 90's yr typewriter selfies letterpress cardigan vegan.

***

Pug heirloom High Life vinyl swag, single-origin coffee four dollar toast taxidermy reprehenderit fap distillery master cleanse locavore. Est anim sapiente leggings Brooklyn ea. Thundercats locavore excepteur veniam eiusmod. Raw denim Truffaut Schlitz, migas sapiente Portland VHS twee Bushwick Marfa typewriter retro id keytar.

> We do not grow absolutely, chronologically. We grow sometimes in one dimension, and not in another, unevenly. We grow partially. We are relative. We are mature in one realm, childish in another.
> —Anais Nin

Fap aliqua qui, scenester pug Echo Park polaroid irony shabby chic ex cardigan church-key Odd Future accusamus. Blog stumptown sartorial squid, gastropub duis aesthetic Truffaut vero. Pinterest tilde twee, odio mumblecore jean shorts lumbersexual.

```

```
```





### heavy weight blog posts

as `.md` under `_posts`.



Anschließend

```
# normaler Markdown content
Möglichkeiten, siehe Template
- Link zu PDFs
- Code
- Diagramme
- Github Comment section
- verschiedene Bilder
```



## Publications

`_pages/publications.md`

normales Bib file ergänzen. 

zusatzoptionen:

```
  bibtex_show={true},
  preview={publication-icon.png}
  pdf={.. .pdf}
    doi={10.1103/PhysRev.47.777},
  url={http://link.aps.org/doi/10.1103/PhysRev.47.777},
    selected={true} -- for selected publications to appear on the start page
```





# Texts



### About me

In 2023, I joined msg research, a cross-cutting department of the [msg group](https://www.msg.group/) that focuses both on innovation projects and advanced education, as well as engaging in consulting and customer projects.



Between 2018 and 2023 I worked as a Research Associate and PhD student at the Chair of Software and Systems Engineering of Prof. Pretschner at the Technical University of Munich. My dissertation "On Machine Learning Assisted Software Maintainability Assessments" is concerned with expert analyses of large software systems and how machine learning techniques can help identify problematic source code. 

Prior to joining the chair, I studied [Software Engineering](https://elite-se.informatik.uni-augsburg.de/) in an elite graduate program hosted by the TU Munich in cooperation with the Ludwig-Maximilians University Munich and the University of Augsburg. These studies included stays at Capgemini and[ Lero - the Irish Software Research Institute](https://www.lero.ie/). I am also an alumnus of the [German Academic Scholarship Foundation](https://www.studienstiftung.de/en/) (Studienstiftung des deutschen Volkes), the [Elite Network of Bavaria](https://www.elitenetzwerk.bayern.de/en/home) (Elitenetzwerk Bayern) as well as the [Lothar and Sigrid Rohde-Foundation](https://www.rohde-stiftung.de/en/home.html).



Current and past [research interests](#Research interests) and a [list of publications](Publications) can be found below (link)



### Research interests

My area of research is Software Quality. Software quality is viewpoint-specific and multi-dimensional. The aspects I am most interested in include

- Software maintainability and its assessment. This includes analyzing source code or designs for their comprehensibility, readability, adequate scoping and other attributes.
- Regression test selection: This discipline is concerned with selecting a subset of test cases from a large test suite to reduce the cost and time of testing while still finding all bugs.
- Requirements Engineering: Arguably, high-quality software satisfies its stakeholders' needs. However, eliciting, modeling, validating and managing requirements is not trivial, especially in agile development processes.

In summary, I am interested in doing things right in the first place and assessing the quality of created artifacts. In the longshot, my goal is to establish software quality analyses that are fast, cheap, reliable and require only little human expert interaction. Still, I strongly believe that final conclusions about the state of a system have to remain in the hands of experienced engineers due to the complexity of the system's context.





### Teaching

I have been involved with several teaching activities both during my time at Technical University of Munich and msg research: 

- Requirements Engineering: Exercise, Lecture preparation, Exams  (5 semester)
- Seminar on Software Quality: Organization, Thesis supervision (7 semesters)
- Introduction to Programming: Tutorials (1 semester)
- Thesis supervision (~20 theses)



Supervised theses include: 

- Vectorizing Software for Machine Learning *

- Investigating Inter-Class Attributes for Capturing Software Maintainability **

- Using Text Classification and Image-based Learning to Predict Software Quality ***

- Automatic Identification and Rating of the Usefulness of Source Code Comments

- Mining Repositories for Quality Indicators

- Detecting Smells in Data Models

- Quality Evaluation of Data Models

- Cornering Cohesion: Investigating new Ways to Measure Cohesion

- Measuring Cohesion and Coupling: a Comparison of Different Metrics and their Usefulness for Software Quality Analyses

- A Labeling Platform for Source Code

- Requirements documentation and analysis for changes to existing business systems

- Assessing the Quality of Code comments using machine learning

- Identification of generated Code

- Identifier Dictionaries

- Configuration of Static Analysis Tools for Effective Bug Detection

- Detecting Code Smells using Graph Neural Networks

- A Super-Metric for Measuring *Adequacy* in the Context of Software  Architecture and Software Programming

  

  

​	*awarded the Pelkoven Award for excellent Master's Thesis

​	**extended and then published at SANER 2023

​	***extended and then published at Software Quality Days 2022, Best Research Paper Award





### Publications

These are my profiles on [Google Scholar](https://scholar.google.de/citations?hl=de&user=XNp5tm4AAAAJ) and [dblp](https://dblp.org/pid/227/5293.html). 

- Gregor, Lena; **Schnappinger**, **Markus**; Pretschner, Alexander: Revisiting Inter-Class Maintainability Indicators. 30th IEEE International Conference on Software Analysis, Evolution and Reengineering (SANER), IEEE, 2023 
- **Schnappinger, Markus**; Zachau, Simon; Fietzke, Arnaud; Pretschner, Alexander: A Preliminary Study on Using Text- and Image-Based Machine Learning to Predict Software Maintainability. In: Software Quality: The Next Big Thing in Software Engineering and Quality. Springer International Publishing, 2022; **Best Research Paper Award**
- Elsner, Daniel; Wuersching, Roland; **Schnappinger, Markus**; Pretschner, Alexander; Graber, Maria; Dammer, René; Reimer, Silke: Build System Aware Multi-language Regression Test Selection in Continuous Integration. 2022 IEEE/ACM 44th International Conference on Software Engineering: Software Engineering in Practice (ICSE-SEIP), 2022
- Elsner, Daniel; Wuersching, Roland; **Schnappinger, Markus**; Pretschner, Alexander: Probe-based Syscall Tracing for Efficient and Practical File-level Test Traces. 2022 IEEE/ACM International Conference on Automation of Software Test (AST), 2022
- **Schnappinger, Markus**; Streit, Jonathan: Efficient Platform Migration of a Mainframe Legacy System Using Custom Transpilation. 2021 IEEE International Conference on Software Maintenance and Evolution (ICSME), IEEE, 2021
- **Schnappinger, Markus**; Fietzke, Arnaud; Pretschner, Alexander: Human-level Ordinal Maintainability Prediction Based on Static Code Metrics. Evaluation and Assessment in Software Engineering, ACM, 2021
- **Schnappinger, Markus**; Fietzke, Arnaud; Pretschner, Alexander: Defining a Software Maintainability Dataset: Collecting, Aggregating and Analysing Expert Evaluations of Software Maintainability. 2020 IEEE International Conference on Software Maintenance and Evolution (ICSME), IEEE, 2020 
- **Schnappinger, Markus**; Fietzke, Arnaud; Pretschner, Alexander: A Software Maintainability Dataset. 2020 
- **Schnappinger, Markus**; Osman, Mohd Hafeez; Pretschner, Alexander; Fietzke, Arnaud: Learning a Classifier for Prediction of Maintainability Based on Static Analysis Tools. 2019 IEEE/ACM 27th International Conference on Program Comprehension (ICPC), IEEE, 2019
- **Schnappinger, Markus**; Osman, Mohd Hafeez; Pretschner, Alexander; Pizka, Markus; Fietzke, Arnaud: Software quality assessment in practice. Proceedings of the 12th ACM/IEEE International Symposium on Empirical Software Engineering and Measurement - ESEM '18, ACM Press, 2018 



In addition, I received honorable mentions for contributions by: 

- Aldenhoven, Celine; Engelschall, Ralf S.: The beauty of software architecture, International Conference on Software Architecture (ICSA), 2023
- Elsner, Daniel; Hauer, Florian; Pretschner, Alexander; Reimer, Silke: Empirically Evaluating Readily Available Information for Regression Test Optimization in Continuous Integration. International Symposium on Software Testing and Analysis (ISSTA), 2021
- Lipp, Stephan; Banescu, Sebastian; Pretschner, Alexander: An empirial study on the effectivness of static C code analyzers for vulnerability detection, International Symphosium on Software Testing and Analysis (ISSTA), 2022



I also serve as a Journal reviewer for the Springer Journal on Software and System Modeling (SoSym)
