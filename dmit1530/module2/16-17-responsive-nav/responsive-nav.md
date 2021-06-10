---
layout: page
title: Responsive Navigation
---
<style>
    .css-class{
        color: firebrick;
        font-weight: bold;
    }
    .html-class{
        color: blue;
        font-weight: bold;
    }
</style>

The following files are required for this lesson:
* [demo-single-level-nav-main.zip](files/demo-single-level-nav-main.zip)
* [demo-multi-level-nav-main.zip](files/demo-multi-level-nav-main.zip)

## Introduction
This lesson will be taught in two parts:
* [Part 1: Single-level Navigation](#single)
* [Part 2: Mulit-level Navigation](#multi)

## Demo Instructions
You can follow along with your instructor to complete this build and/or you can use this document as a guide in completing the demo build.

## Steps - <a ID="single">Part 1</a>: Single-level Navigation
1.	Download the **demo-single-level-nav-main.zip** file and extract its contents to a folder **named demo-single-level-nav-main**.
2.	The completed output should look like:<br>
![single-nav-01.jpg](files/single-nav-01.jpg)<br>
Note: When the browser is resized, the menu will start to wrap to the next row.
3.	The index.html file needs to be updated as follows:<br>
    <ol type="a">
        <li>Modify the <span class="html-class">&lt;head&gt;</span> to be:<br>
        <img src="files/single-index-01.jpg" alt="single-index-01">
        </li>
        <li>Add the following to the <span class="html-class">&lt;body&gt;</span>:<br>
        <img src="files/single-index-02.jpg" alt="single-index-02">
        </li>
    </ol>
4.	The web page should now look like:<br>
![single-nav-02.jpg](files/single-nav-02.jpg)<br>
**Question**: What needs to be done to the menu?
5.	Open the **styles.css** and add the following style rules:<br>
    <ol type="a">
        <li>Style the <span class="html-class">&lt;body&gt;</span> element:<br>
        <img src="files/single-css-styles-01.jpg" alt="single-css-styles-01">
        </li>
        <li>Style the <span class="html-class">&lt;header&gt;</span>:<br>
        <img src="files/single-css-styles-02.jpg" alt="single-css-styles-02">
        </li>
        <li>Style the menu <span class="html-class">&lt;ul&gt;</span>:<br>
        <img src="files/single-css-styles-03.jpg" alt="single-css-styles-03">
        </li>
        <li>Style the <span class="html-class">&lt;a&gt;</span> elements of the menu:<br>
        <img src="files/single-css-styles-04.jpg" alt="single-css-styles-04"><br>
        Your web page should now look like:<br>
        <img src="files/single-nav-03.jpg" alt="single-nav-03"><br>
        <b>Question</b>: what needs to be done next?
        </li>
        <li>Now add the media query:<br>
        <img src="files/single-css-styles-05.jpg" alt="single-css-styles-05"><br>
        <b>Question</b>: What does this media query do? What size is <span class="css-class">30em</span>?
        </li>
        <li>When you resize your browser, you should see something like:<br>
        <img src="files/single-nav-04.jpg" alt="single-nav-04">
        </li>
    </ol>
6.	The `img` folder contains several SVG files. As a challenge, add these to your menu items and modify your **styles.css** code to produce the following output:<br>
![single-nav-05.jpg](files/single-nav-05.jpg)<br>
**Note**: the green text is a hover effect.

## Steps - <a ID="multi">Part 2</a>: Multi-level Navigation
1.	Download the **demo-multi-level-nav-main.zip** file and extract its contents to a folder named **demo-multi-level-nav-main**.
2.	The completed output should look like:
_insert image here…_
3.	More notes to follow...

### [Lesson Home](16-17-responsive-nav.md)
### [Module Home](../module2.md)
### [DMIT1530 Home](../../)
