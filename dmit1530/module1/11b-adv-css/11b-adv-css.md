---
Layout: page
Title: Advanced CSS Selectors & Flex Order
---

<style>
    .shadow{
        text-shadow: 1px 1px;
    }
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
* [demo-selectors.zip](files/demo-selectors.zip)
* [demo-flex-order.zip](files/demo-flex-order.zip)
* [demo-flexbox-layout.zip](files/demo-flexbox-layout.zip)

## Introduction
This lesson will be taught in three parts:
* [Part 1: CSS Selectors](#selectors)
* [Part 2: Flex Order](#order)
* [Part 3: Flexbox Layout](#layout)

## Demo Instructions
You can follow along with your instructor to complete this build and/or you can use this document as a guide in completing the demo build.

## Steps - <a ID="selectors">Part 1</a>: CSS Selectors
1.	Download the demo-selectors.zip file and extract its contents to a folder named demo-selectors.
2.	The completed output should look like:<br>
![selectors-01.jpg](files/selectors-01.jpg)
3.	You need to add some code to the **index.html** file:<br>
    <ol type="a">
        <li>Add a flex container:<br>
        <img src="files/selectors-index-01.jpg" alt="selectors-index-01">
        </li>
        <li>Add <span class="html-class">&lt;section&gt;</span> blocks inside the flex container:<br>
        <img src="files/selectors-index-02.jpg" alt="selectors-index-02">
        </li>
        <li>Add a &lt;footer&gt;:<br>
        <img src="files/selectors-index-03.jpg" alt="selectors-index-03"><br>
        The output in your browser should look like:<br>
        <img src="files/selectors-02.jpg" alt="selectors-02">
        </li>
    </ol>
4.	Now you need to add style rules to the **styles.css** file:<br>
    <ol type="a">
        <li>Add a <span class="css-class">.flex-container</span> class:<br>
        <img src="files/selectors-css-styles-01.jpg" alt="selectors-css-styles-01"><br>
        <b>Question</b>: What does this style rule do?
        </li>
        <li>Add styling for the <span class="html-class">&lt;section&gt;</span> elements:<br>
        <img src="files/selectors-css-styles-02.jpg" alt="selectors-css-styles-02"><br>
        <img src="files/selectors-03.jpg" alt="selectors-03">
        </li>
        <li>As the individual <span class="html-class">&lt;section&gt;</span> blocks do not appear, you need to use a pseudo-selector to target the styling of each <span class="html-class">&lt;section&gt;</span>:
            <ol type="i">
                <li><span class="css-class">first-child</span>:<br>
                <img src="files/selectors-css-styles-03.jpg" alt="selectors-css-styles-03">
                </li>
                <li><span class="css-class">last-child</span>:<br>
                <img src="files/selectors-css-styles-04.jpg" alt="selectors-css-styles-04">
                </li>
                <li><span class="css-class">>nth-child(2)</span>:<br>
                <img src="files/selectors-css-styles-05.jpg" alt="selectors-css-styles-05">
                </li>
                <li><span class="css-class">nth-child(3)</span>:<br>
                <img src="files/selectors-css-styles-06.jpg" alt="selectors-css-styles-06"><br>
                Refresh your browser to see:<br>
                <img src="files/selectors-04.jpg" alt="selectors-04">
                </li>
                <li><span class="css-class">nth-last-child(3)</span>:<br>
                <img src="files/selectors-css-styles-07.jpg" alt="selectors-css-styles-07">
                </li>
                <li><span class="css-class">nth-last-child(2)</span>:<br>
                <img src="files/selectors-css-styles-08.jpg" alt="selectors-css-styles-08"><br>
                Refresh your browser to see the following making note of the colours you used for each <span class="html-class">&lt;section&gt;</span>’s background:<br>
                <img src="files/selectors-05.jpg" alt="selectors-05">
                </li>
            </ol>
        </li>
        <li>The <span class="html-class">&lt;footer&gt;</span> needs to have a different background colour:<br>
        <img src="files/selectors-css-styles-09.jpg" alt="selectors-css-styles-09"><br>
        <img src="files/selectors-06.jpg" alt="selectors-06">
        </li>
        <li>The nth of type selector can be used to target the position of a child element. Each <span class="html-class">&lt;section&gt;</span> has two <span class="html-class">&lt;p&gt;</span> elements, thus you can target each of these using:<br>
        <img src="files/selectors-css-styles-10.jpg" alt="selectors-css-styles-10"><br>
        <img src="files/selectors-07.jpg" alt="selectors-07"><br>
        Note: the font of the 1<sup>st</sup> paragraph is now <b>bolded</b> and has a slight text <span class="shadow">shadow</span>:
        </li>
        <li>Targeting the other paragraphs is done using:<br>
        <img src="files/selectors-css-styles-11.jpg" alt="selectors-css-styles-11">
        </li>
    </ol>

## Steps - <a ID="order">Part 2</a>: Flex Order
