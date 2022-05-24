---
layout: page
title: 17 - Layout with Content
---
The following file is required for this lesson:
* [layout-with-content.zip](files/layout-with-content.zip)

## Demo Instructions
You can follow along with your instructor to complete this build and/or you can use this document as a guide in completing the demo build.

## Steps
1. Download the **layout-with-content.zip** file and extract its contents to a folder called **layout-with-content**.
2. The result of this demo should look like:<br>
![Layout-final.jpg](files/layout-final.jpg)
3. Calculate the width of each `<li>` in the `<ul class="menu">` using the following steps:
    *  Subtract the final right margin: **960 - 15 = 945**
    *  Subtract the left margin from each `<li>`: **945 – 75 = 870**
    *  Subtract the left and right border of each `<li>`: **870 – 20 = 850**
    *  Divide that result by 5: **850 / 5 = 170**
    *  Calculate the width of the each `<section>`:
        *  Subtract the final right margin: **960 – 15 = 945**
        *  Subtract the left margin for each `<div>`: **945 – 30 = 915**
        *  Subtract the left and right borders: **915 – 8 = 907**
        *  Subtract the left and right padding: **907 – 60 = 847**
        *  Divide the result by 2: **847 / 2 = 423.5**
4. In the **css** folder add the following code to the **styles.css** file:
    *  Style the typography:<br>
       ![css-styles-a](files/css-styles-a.jpg)
    *  Style the `.site-header` class:<br>
       ![css-styles-b](files/css-styles-b.jpg)
    *  Style the `.site-header nav` class:<br>
       ![css-styles-c](files/css-styles-c.jpg)
    *  Style the `.menu`:<br>
       ![css-styles-d](files/css-styles-d.jpg)
    *  Style the `<li>` in the `<nav>`:<br>
       ![css-styles-e](files/css-styles-e.jpg)
    *  Style the `<main>` element:<br>
       ![css-styles-f](files/css-styles-f.jpg)
    *  Style the `<section>` elements in the `<main>`:<br>
       ![css-styles-g](files/css-styles-g.jpg)
5. Open the **index.html** file in your browser. If the result is different, make any necessary corrections, and refresh your browser.
6. In your browser, open the developer tools and examine the widths of each of the <code>class="menu"</code>:<br>
![width-menu.jpg](files/width-menu.jpg)
7. Now examine a single `<li>` element:<br>
![width-li.jpg](files/width-li.jpg)
8. Now examine a `<section>` element:<br>
![width-section.jpg](files/width-section.jpg)
9. Now the `<main>`:<br>
![width-main.jpg](files/width-main.jpg)

## Exercise Instructions
There are no exercises related to this demo.

#### [Module Home](../)
#### [COMP1017 Home](../../)