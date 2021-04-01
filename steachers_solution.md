Analysis of Teachers’ Recruitment in Saudi Arabia Between 1437 and 1440
================
Musab Isah
6 March 2021

Group Number:5

Group Members’ Names (IDs):

1.  Fawzaih Nazal(2201000429) – Team Leader 2.Manar Mansour(2201002883)
    – Member 1 3.Hajar Eid(2201002337) – Member 2 4.Fadiyah
    suliman(2201001182) ,wallaa Ali(2201002583) – Member 3

## Loading Libraries

Ensure you have the `tidyverse` and `readxl` packages installed by
running the 2 lines of code below. Both the team leader and members
should run the code below in the console of rstudio.

We then need to load the data from the MS Excel (.xlsx) file, named
teachers\_data.xlsx, to the R environment for processing.

*Note: Only Team Leader should run the code below*

``` r
tdata <- read_excel("teachers_data.xlsx")
```

# Wherever you see the text ‘\#Add some code’, it means you should delete the comment and add your code for the task.

# 2 Marks will be deducted for every deadline missed.

## Task 1

``` r
tdata = rename(tdata, administrative_regions = "المنطقة الإدارية")
tdata = rename(tdata, school_Level = "المرحلة")
tdata = rename(tdata, authority = "السلطة")
tdata = rename(tdata, Office_of_Education = "مكتب التربية")
tdata = rename(tdata, sex = "الجنس")
tdata = rename(tdata, School_type = "نوع المدرسة")
tdata = rename(tdata, Type_of_education = "نوع التعليم")
tdata = rename(tdata, school_system = "نظام الدراسة")
tdata = rename(tdata, Saudi_teacher = "معلم سعودي")
tdata = rename(tdata, Non_Saudi_teacher = "معلم غير سعودي")
tdata = rename(tdata, Teachers = "معلمين جملة")
tdata = rename(tdata, the_year = "السنة")
```

Team Leader should *Knit, commit, and push changes to GitHub with an
appropriate commit message. Make sure to commit and push all changed
files so that your Git pane is cleared up afterwards.*

## Task2

Next Team Member should *Pull the changes made by Team Leader before
proceeding.*

1.  What are the different administrative\_regions (Al-Mandaqah
    Al-idariyyah) found in the data?

``` r
tdata %>% count(administrative_regions) %>% arrange(desc(n))
```

    ## # A tibble: 13 x 2
    ##    administrative_regions     n
    ##    <chr>                  <int>
    ##  1 الرياض                 31617
    ##  2 مكة المكرمة            26944
    ##  3 عسير                   15462
    ##  4 الشرقية                15034
    ##  5 المدينة المنورة        10012
    ##  6 القصيم                  9449
    ##  7 جازان                   9229
    ##  8 حائل                    5302
    ##  9 تبوك                    4722
    ## 10 الباحة                  4220
    ## 11 الجوف                   3442
    ## 12 نجران                   2933
    ## 13 الحدود الشمالية         2072

Comments about your answer:the biggest regions -&gt;{riyadh: 31617 ,
makkah : 26944 }

and the smallest-&gt; {alhudood alshmalya : 2072 , najran : 2933}.

2.  Based on your knowledge of the administrative regions in Saudi
    Arabia, is there any region that has not recruited any teacher
    during the period under review (1437 - 1440 Hijri)? List the Saudi
    regions shown in the data.

``` r
tdata %>% filter(the_year>=1437 ,the_year<=1440, Teachers==0)%>% count(administrative_regions)
```

    ## # A tibble: 0 x 2
    ## # ... with 2 variables: administrative_regions <chr>, n <int>

``` r
tdata %>% filter(the_year>=1437 ,the_year<=1440, Saudi_teacher==0)%>% count(administrative_regions)%>%arrange(desc(n))
```

    ## # A tibble: 13 x 2
    ##    administrative_regions     n
    ##    <chr>                  <int>
    ##  1 الرياض                   652
    ##  2 مكة المكرمة              509
    ##  3 الشرقية                  289
    ##  4 المدينة المنورة          100
    ##  5 عسير                      51
    ##  6 الجوف                     32
    ##  7 حائل                      31
    ##  8 تبوك                      29
    ##  9 القصيم                    24
    ## 10 نجران                     22
    ## 11 جازان                     17
    ## 12 الحدود الشمالية           15
    ## 13 الباحة                     1

``` r
tdata %>% filter(the_year>=1437 ,the_year<=1440, Non_Saudi_teacher==0)%>% count(administrative_regions)%>%arrange(desc(n))
```

    ## # A tibble: 13 x 2
    ##    administrative_regions     n
    ##    <chr>                  <int>
    ##  1 الرياض                 25271
    ##  2 مكة المكرمة            22492
    ##  3 عسير                   14773
    ##  4 الشرقية                12160
    ##  5 المدينة المنورة         9220
    ##  6 القصيم                  9054
    ##  7 جازان                   8766
    ##  8 حائل                    5014
    ##  9 تبوك                    4211
    ## 10 الباحة                  4165
    ## 11 الجوف                   2852
    ## 12 نجران                   2661
    ## 13 الحدود الشمالية         1826

Comments about your answer:The year (1437 to 1440), one non-Saudi and
Saudis teacher was appointed by the administrative regions and most
regions, at least one teacher was appointed in Riyadh.

The Team Member should *Knit, commit, and push changes to GitHub with an
appropriate commit message.*

## Task3

The Next Team Member should *Pull the changes made by Member 1 before
proceeding.*

1.  Saudi Arabian education is divided into different stages/levels
    (Al-Marhala), list the different levels showed in the data in
    descDEADLINE: ENDing order of frequency. (4 points)

``` r
#Add some code
```

Comments about your answer:

2.  Which level recruit the most teachers? (4 points)

``` r
#Add some code
```

Comments about your answer:

The Team Member should *Knit, commit, and push changes to GitHub with an
appropriate commit message.*

The Next Team member should *Pull the changes made by Team Leader before
proceeding.*

3.  Plot the graph of region versus number of **Saudi** teachers
    recruited over the period. (4 points)

``` r
#Add some code
```

Comments about your answer:

4.  Plot the graph of region versus number of **Non-Saudi** teachers
    recruited over the period. (4 points)

``` r
#Add some code
```

Comments about your answer:

5.  Plot the graph of region versus number of **all teachers** recruited
    over the period. (4 points)

``` r
#Add some code
```

Comments about your answer:

The Team Member should *Knit, commit, and push changes to GitHub with an
appropriate commit message.*

## Task 4

The Next Team member should *Pull the changes made previously before
proceeding.*

1.  How many boys and how many girls schools are listed in the data? (4
    points)

``` r
#Add some code
```

Comments about your answer:

2.  Between boys and girls schools, which recruit more teachers? (4
    points)

``` r
#Add some code
```

Comments about your answer:

3.  What is the correlation between recruitment at boys schools and
    recruitment of girls schools? (4 points)

``` r
#Add some code
```

Comments about your answer:

The Team Member should *Knit, commit, and push changes to GitHub with an
appropriate commit message.*

## Task 5

The Next Team member should *Pull the changes made previously before
proceeding.*

1.  How many teachers are recruited each year, 1437, 1438, 1439, and
    1440?

``` r
#Add some code
```

Comments about your answer:

2.  Which region recruited the most teachers in each of the years under
    review? (4 points)

``` r
#Add some code
```

Comments about your answer:

3.  Plot the graph of number of teachers recruited vs the number of
    schools in an administrative region? What type or relationship exist
    between the two variables? (4 points)

``` r
#Add some code
```

Comments about your answer:

The Team Member should *Knit, commit, and push changes to GitHub with an
appropriate commit message.*

## If you are here, then congratulations!! You have completed the DSC 200 course project.
