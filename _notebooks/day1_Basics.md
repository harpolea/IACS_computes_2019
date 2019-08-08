---
layout: post
title:  Basics
date:   2019-08-08
day: 1
---


# Jupyter Notebook Basics

This notebook is a guide to using Jupyter notebooks. We shall be using these in the rest of the course to develop and run our code.

Jupyter notebooks are interactive documents that can contain a mixture of text and code. They are made up of blocks called *cells*. We will be using two different types of cells. The first is called a *Markdown cell*. Markdown cells, when executed (described below), simply become paragraphs of text (just like in a text editor such as Microsoft Word). The second type of cell we will be using are *code cells*. Code cells, when executed, will run the code inside the cell. The easiest way to change the type of cell you are coding in is with the dropdown menu at the top of the screen. 

Keep note of this: one of the most common mistakes students have when beginning to use Jupyter notebooks is typing code into a markdown cell, or regular text into a code cell. This is easily fixed by changing the cell to the correct type.

What does it mean to *execute* a cell? We (the user) are telling the Jupyter notebook program to run everything we have typed in the cell, be it actual Python code or simple (markdown) text. To execute a cell, simply have that cell selected (be it in edit mode or command mode), hold `Shift` and hit the `Enter` key.

What is *edit mode*? Edit mode allows us to change the contents of the cell. It is indicated by a blue line in the left hand-margin and a blue cell border around the cell we've selected, as well as a prompt within the cell. You can access it by selecting the cell and pressing `Enter`, or by double clicking on the cell.

What is *command mode*? This mode allows you to edit the notebook as a whole. When a cell is selected in command mode, there is no blue border around the cell and no prompt, just a blue bar at the margin. Command mode is for navigating around notebook, and there are a number of keyboard shortcuts that allow you to do this.

Here's a list of basic commands keyboard shortcuts accessible in command mode:

1. Basic navigation: enter, shift-enter, up/k, down/j
2. Saving the notebook: s
3. Change Cell types: 
    - y (change to code)
    - m (change to markdown)
    - 1-6 (change to headline, larger number is smaller text)
4. Cell creation: a, b (these stand for "above" and "below")
5. Cell deletion: d (press twice)
6. Cell editing: x, c, v, d, z
7. Kernel operations: i, 0 (press twice)

Commands like this can greatly increase productivity and are always worth spending the time to learn.

Markdown is a type of *markup language*, which means we can format the text in Markdown cells using some special commands. We can make **bold** and *italics* as follows:
Here is some **bold** text, and here is some *italicized* text.
becomes

Here is some **bold** text, and here is some *italicized* text.

These notebooks will use *LaTeX* to format our mathematical expressions. LaTeX is another markup language and is often used by scientists for technical documents. It's pretty powerful and can get very complex, but we'll just use some basic commands to write out some symbols and formulae. We can write letters from the Greek alphabet, such as $\phi$ and $\theta$, as well as more complex mathematical expressions, such as 
$$
x = \frac{-b \pm \sqrt{b^2 - 4 a c}}{2a}.
$$
