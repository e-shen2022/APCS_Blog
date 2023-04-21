---
keywords: fastai
title: Individual CPT Submission Plan
toc: true 
badges: true
comments: true 
categories: [jupyter]
nb_path: _notebooks/2023-1-30-cptindividual.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2023-1-30-cptindividual.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>OUR TEAM SIZE PROJECT</strong></p>
<p>Problem: 60% of Americans feel uncomfortable about their skin and don’t know how to treat it</p>
<p>Solution: CSP (Customized Skin Products) --&gt; A fast &amp; free website that caters to our user’s specific skin type to recommend quality skin care products &amp; services that range from a face cleanser to a professional dermatologist in their area</p>
<p>Purpose:</p>
<ol>
<li>Help people of all ages to gain a thorough understanding of their own skin and how to treat it </li>
<li>Develop a skincare routine to ensure long-term maintenance of clear and healthy skin </li>
<li>Uplift inner and outer confidence! Looking good and feeling good to feel comfortable engaging with those around us and showing our personality to our full potential</li>
</ol>
<p>Audience: Pre-tween kids to young adults dealing with pubescent &amp; stress blemeches. Most vulnerable to future self-esteem issues stemming from skin problems</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>MY INDIVIDUAL CONTRIBUTION</strong>: Based on user-input from skin-type quiz, generate top 3 recommendations for a face cleanser product</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>HOW I PLAN TO FULFILL THE CB RUBRIC</strong></p>
<p><mark>Row 1</mark>: Program Purpose &amp; Function</p>
<ol>
<li><p>In the video: I will pretend I am a user and fill out the multiple choice skin-type quiz (input). Once I press generate results, it will show the output which is an in-depth evaluation of my skin type and how to treat it. Then, when I press on the "face cleansers" tab, it will show 3 products personally recommended. All of this together will show program functionality</p>
</li>
<li><p>In the written response (3A): I will clearly explain the overall purpose AND function.</p>
</li>
</ol>
<p>Function: CSP (Customized Skin Products) --&gt; A fast &amp; free website that caters to user’s specific skin type to produce in-depth evaluation of how to improve and recommend quality skin care product.</p>
<p>Purpose: Help teenagers to gain a thorough understanding of their own skin and how to treat it. Uplifting inner and outer confidence so that they feel comfortable engaging with those around them and showing their personality to their full potential.</p>
<p>Clarify input and output: input (user-inputted skin-type quiz) &amp; output (skin-type evaluation + face cleanser recommendation)</p>
<p><mark>Row 2</mark>: Data Abstraction</p>
<p>In the written response (3B):</p>
<ol>
<li>Code segment shows how data is being stored in a list --&gt; I plan to create an array with all the quiz questions and loop through them </li>
<li>Code segment shows the data in this same list being used as part of fulfilling the program’s purpose --&gt; in recommendation function, will show that I am looping through questions and if user's answer matches with a product's assigned answer, add one point to that recommended product. </li>
<li>Identifies name of variable representing list being used --&gt; quizQs</li>
<li>Describes what the data contained in this list is representing in the program --&gt; data contained in list represents questions that user will be asked to determine what their skin-type is and what face cleanser recommendation they should recieve </li>
</ol>
<p><mark>Row 3</mark>: Managing Complexity</p>
<p>In the written response (3B):</p>
<ol>
<li>Explains how list manages complexity + why vital to program: If program were to run without the "quizQs" list, it would make everything very inefficient because I would have to make new individual variables to store each question. By using "quizQs", I can consolidate all that information in one place, making it easier to use
and keep track of.</li>
</ol>
<p><mark>Row 4</mark>: Procedural Abstraction</p>
<p>In the written response (3C):</p>
<ol>
<li>Code segment that shows student-developed procedure with at least one parameter that has an effeect on the functionality of the procedure: I will create a recommendation function called "faceCleanserRec" which will take user's input to each question and +1 to the corresponding variable. Then whichever variable is the max will be printed as the recommended product. </li>
<li>Code segment where student-developed procedure is being called: I will show place where "faceCleanserRec" will be called</li>
<li>Describes identified procedure does and how contribute to overall functionality of the program: This recommendation function contributes to my project's key feature which is giving custom product recommendation. Without this backend code, when the user submits their quiz they will recieve no result </li>
</ol>
<p><mark>Row 5</mark>:  Algorithm Implementation</p>
<p>In the written response (3C):</p>
<ol>
<li>Code Segment in student-developed procedure that shows: </li>
</ol>
<ul>
<li>sequencing: Code runs in order from line at top to line at bottom (starts with list of questions --&gt; recommendation function to output face cleanser)</li>
<li>iteration: iterates through list of questions</li>
<li>selection: if/else statements to check which variable is the max to output what product to recommend</li>
</ul>
<ol>
<li>Explains in detailed steps how the identified algorithm works in enough detail that someone else could recreate it --&gt; will walk through entire algorithm line by line</li>
</ol>
<p><mark>Row 6</mark>: Testing</p>
<p>In the written response (3D):</p>
<p>1st call: question asks "Would you describe your skin as oily, dry, or a combination of both?" &amp; user chooses answer choice "oily"
2nd call: question asks "What is your age?" &amp; user chooses age group 14 - 17 years old</p>
<p>1st condition: if user chooses oily, 1 point is added to variable called "CetaPhil" which is a face cleansing brand that is good for oily skin 
2nd call: if user chooses answer option 14-17 years old, 1 point is added to variable called "humanAcne" which is a face washer good for teenage acne</p>
<p>1st result: One of top 3 face cleanser recommendations will be one from CetaPhil
2nd call: one of top 3 face cleanser recommendations will be for teenage acne</p>

</div>
</div>
</div>
</div>
 
