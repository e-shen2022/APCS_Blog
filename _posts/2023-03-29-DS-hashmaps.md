---
keywords: fastai
description: Observing hashmaps with python dictionaries
title: Data Structures- Hashmaps, Sets, Hash Tables, Hashing and Collisions
toc: true
categories: []
type: pbl
week: 28
nb_path: _notebooks/2023-03-29-DS-hashmaps.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2023-03-29-DS-hashmaps.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="What-is-a-Hashtable/Hashmap?">What is a Hashtable/Hashmap?<a class="anchor-link" href="#What-is-a-Hashtable/Hashmap?"> </a></h2><blockquote><p>A hashtable is a data structure that with a collection of key-value pairs, where each key maps to a value, and the keys must be unique and hashable.</p>
</blockquote>
<ul>
<li>In Python there is a built in hashtable known as a <b>dictionary</b>.</li>
</ul>
<blockquote><p>The primary purpose of a hashtable is to provide efficient lookup, insertion, and deletion operations. When an element is to be inserted into the hashtable, a hash function is used to map the key to a specific index in the underlying array that is used to store the key-value pairs. The value is then stored at that index. When searching for a value, the hash function is used again to find the index where the value is stored.</p>
<p>The key advantage of a hashtable over other data structures like arrays and linked lists is its average-case time complexity for lookup, insertion, and deletion operations.</p>
</blockquote>
<ul>
<li>The typical time complexity of a hashtable is <b>O(1)</b>. </li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="What-is-Hashing-and-Collision?">What is Hashing and Collision?<a class="anchor-link" href="#What-is-Hashing-and-Collision?"> </a></h2><blockquote><p>Hashing is the process of mapping a given key to a value in a hash table or hashmap, using a hash function. The hash function takes the key as input and produces a hash value or hash code, which is then used to determine the index in the underlying array where the value is stored. The purpose of hashing is to provide a quick and efficient way to access data, by eliminating the need to search through an entire data structure to find a value.</p>
<p>However, it is possible for two different keys to map to the same hash value, resulting in a collision. When a collision occurs, there are different ways to resolve it, depending on the collision resolution strategy used.</p>
<p>Python's dictionary implementation is optimized to handle collisions efficiently, and the performance of the dictionary is generally very good, even in the presence of collisions. However, if the number of collisions is very high, the performance of the dictionary can degrade, so it is important to choose a good hash function that minimizes collisions when designing a Python dictionary.</p>
</blockquote>
<h2 id="What-is-a-Set?">What is a Set?<a class="anchor-link" href="#What-is-a-Set?"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">my_set</span> <span class="o">=</span> <span class="nb">set</span><span class="p">([</span><span class="mi">1</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="mi">1</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="n">my_set</span><span class="p">)</span>  

<span class="c1"># Q: What do you notice in the output? </span>
<span class="c1"># A: Outputs only once of every number in the list, no duplicates (2 and 1)</span>

<span class="c1"># Q: Why do you think Sets are in the same tech talk as Hashmaps/Hashtables? </span>
<span class="c1"># A: Sets allow you to quickly and efficiently access data with no duplicates</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{1, 2, 3}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Dictionary-Example">Dictionary Example<a class="anchor-link" href="#Dictionary-Example"> </a></h2><p>Below are just some basic features of a dictionary. As always, documentation is always the main source for all the full capablilties.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">lover_album</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;title&quot;</span><span class="p">:</span> <span class="s2">&quot;Lover&quot;</span><span class="p">,</span>
    <span class="s2">&quot;artist&quot;</span><span class="p">:</span> <span class="s2">&quot;Taylor Swift&quot;</span><span class="p">,</span>
    <span class="s2">&quot;year&quot;</span><span class="p">:</span> <span class="mi">2019</span><span class="p">,</span>
    <span class="s2">&quot;genre&quot;</span><span class="p">:</span> <span class="p">[</span><span class="s2">&quot;Pop&quot;</span><span class="p">,</span> <span class="s2">&quot;Synth-pop&quot;</span><span class="p">],</span>
    <span class="s2">&quot;tracks&quot;</span><span class="p">:</span> <span class="p">{</span>
        <span class="mi">1</span><span class="p">:</span> <span class="s2">&quot;I Forgot That You Existed&quot;</span><span class="p">,</span>
        <span class="mi">2</span><span class="p">:</span> <span class="s2">&quot;Cruel Summer&quot;</span><span class="p">,</span>
        <span class="mi">3</span><span class="p">:</span> <span class="s2">&quot;Lover&quot;</span><span class="p">,</span>
        <span class="mi">4</span><span class="p">:</span> <span class="s2">&quot;The Man&quot;</span><span class="p">,</span>
        <span class="mi">5</span><span class="p">:</span> <span class="s2">&quot;The Archer&quot;</span><span class="p">,</span>
        <span class="mi">6</span><span class="p">:</span> <span class="s2">&quot;I Think He Knows&quot;</span><span class="p">,</span>
        <span class="mi">7</span><span class="p">:</span> <span class="s2">&quot;Miss Americana &amp; The Heartbreak Prince&quot;</span><span class="p">,</span>
        <span class="mi">8</span><span class="p">:</span> <span class="s2">&quot;Paper Rings&quot;</span><span class="p">,</span>
        <span class="mi">9</span><span class="p">:</span> <span class="s2">&quot;Cornelia Street&quot;</span><span class="p">,</span>
        <span class="mi">10</span><span class="p">:</span> <span class="s2">&quot;Death By A Thousand Cuts&quot;</span><span class="p">,</span>
        <span class="mi">11</span><span class="p">:</span> <span class="s2">&quot;London Boy&quot;</span><span class="p">,</span>
        <span class="mi">12</span><span class="p">:</span> <span class="s2">&quot;Soon You&#39;ll Get Better (feat. Dixie Chicks)&quot;</span><span class="p">,</span>
        <span class="mi">13</span><span class="p">:</span> <span class="s2">&quot;False God&quot;</span><span class="p">,</span>
        <span class="mi">14</span><span class="p">:</span> <span class="s2">&quot;You Need To Calm Down&quot;</span><span class="p">,</span>
        <span class="mi">15</span><span class="p">:</span> <span class="s2">&quot;Afterglow&quot;</span><span class="p">,</span>
        <span class="mi">16</span><span class="p">:</span> <span class="s2">&quot;Me! (feat. Brendon Urie of Panic! At The Disco)&quot;</span><span class="p">,</span>
        <span class="mi">17</span><span class="p">:</span> <span class="s2">&quot;It&#39;s Nice To Have A Friend&quot;</span><span class="p">,</span>
        <span class="mi">18</span><span class="p">:</span> <span class="s2">&quot;Daylight&quot;</span>
    <span class="p">}</span>
<span class="p">}</span>

<span class="c1"># Q: What data structures do you see?</span>
<span class="c1"># A: dictionary for the key tracks, list for the key genre </span>

<span class="c1"># Printing the dictionary</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{&#39;title&#39;: &#39;Lover&#39;, &#39;artist&#39;: &#39;Taylor Swift&#39;, &#39;year&#39;: 2019, &#39;genre&#39;: [&#39;Pop&#39;, &#39;Synth-pop&#39;], &#39;tracks&#39;: {1: &#39;I Forgot That You Existed&#39;, 2: &#39;Cruel Summer&#39;, 3: &#39;Lover&#39;, 4: &#39;The Man&#39;, 5: &#39;The Archer&#39;, 6: &#39;I Think He Knows&#39;, 7: &#39;Miss Americana &amp; The Heartbreak Prince&#39;, 8: &#39;Paper Rings&#39;, 9: &#39;Cornelia Street&#39;, 10: &#39;Death By A Thousand Cuts&#39;, 11: &#39;London Boy&#39;, 12: &#34;Soon You&#39;ll Get Better (feat. Dixie Chicks)&#34;, 13: &#39;False God&#39;, 14: &#39;You Need To Calm Down&#39;, 15: &#39;Afterglow&#39;, 16: &#39;Me! (feat. Brendon Urie of Panic! At The Disco)&#39;, 17: &#34;It&#39;s Nice To Have A Friend&#34;, 18: &#39;Daylight&#39;}}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;tracks&#39;</span><span class="p">))</span>
<span class="c1"># or</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="p">[</span><span class="s1">&#39;tracks&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{1: &#39;I Forgot That You Existed&#39;, 2: &#39;Cruel Summer&#39;, 3: &#39;Lover&#39;, 4: &#39;The Man&#39;, 5: &#39;The Archer&#39;, 6: &#39;I Think He Knows&#39;, 7: &#39;Miss Americana &amp; The Heartbreak Prince&#39;, 8: &#39;Paper Rings&#39;, 9: &#39;Cornelia Street&#39;, 10: &#39;Death By A Thousand Cuts&#39;, 11: &#39;London Boy&#39;, 12: &#34;Soon You&#39;ll Get Better (feat. Dixie Chicks)&#34;, 13: &#39;False God&#39;, 14: &#39;You Need To Calm Down&#39;, 15: &#39;Afterglow&#39;, 16: &#39;Me! (feat. Brendon Urie of Panic! At The Disco)&#39;, 17: &#34;It&#39;s Nice To Have A Friend&#34;, 18: &#39;Daylight&#39;}
{1: &#39;I Forgot That You Existed&#39;, 2: &#39;Cruel Summer&#39;, 3: &#39;Lover&#39;, 4: &#39;The Man&#39;, 5: &#39;The Archer&#39;, 6: &#39;I Think He Knows&#39;, 7: &#39;Miss Americana &amp; The Heartbreak Prince&#39;, 8: &#39;Paper Rings&#39;, 9: &#39;Cornelia Street&#39;, 10: &#39;Death By A Thousand Cuts&#39;, 11: &#39;London Boy&#39;, 12: &#34;Soon You&#39;ll Get Better (feat. Dixie Chicks)&#34;, 13: &#39;False God&#39;, 14: &#39;You Need To Calm Down&#39;, 15: &#39;Afterglow&#39;, 16: &#39;Me! (feat. Brendon Urie of Panic! At The Disco)&#39;, 17: &#34;It&#39;s Nice To Have A Friend&#34;, 18: &#39;Daylight&#39;}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;tracks&#39;</span><span class="p">)[</span><span class="mi">4</span><span class="p">])</span>
<span class="c1"># or</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="p">[</span><span class="s1">&#39;tracks&#39;</span><span class="p">][</span><span class="mi">4</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>The Man
The Man
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">lover_album</span><span class="p">[</span><span class="s2">&quot;producer&quot;</span><span class="p">]</span> <span class="o">=</span> <span class="nb">set</span><span class="p">([</span><span class="s1">&#39;Taylor Swift&#39;</span><span class="p">,</span> <span class="s1">&#39;Jack Antonoff&#39;</span><span class="p">,</span> <span class="s1">&#39;Joel Little&#39;</span><span class="p">,</span> <span class="s1">&#39;Taylor Swift&#39;</span><span class="p">,</span> <span class="s1">&#39;Louis Bell&#39;</span><span class="p">,</span> <span class="s1">&#39;Frank Dukes&#39;</span><span class="p">])</span>

<span class="c1"># Q: What can you change to make sure there are no duplicate producers?</span>
<span class="c1"># A: use the set function </span>

<span class="c1"># Printing the dictionary</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{&#39;title&#39;: &#39;Lover&#39;, &#39;artist&#39;: &#39;Taylor Swift&#39;, &#39;year&#39;: 2019, &#39;genre&#39;: [&#39;Pop&#39;, &#39;Synth-pop&#39;], &#39;tracks&#39;: {1: &#39;I Forgot That You Existed&#39;, 2: &#39;Cruel Summer&#39;, 3: &#39;Lover&#39;, 4: &#39;The Man&#39;, 5: &#39;The Archer&#39;, 6: &#39;I Think He Knows&#39;, 7: &#39;Miss Americana &amp; The Heartbreak Prince&#39;, 8: &#39;Paper Rings&#39;, 9: &#39;Cornelia Street&#39;, 10: &#39;Death By A Thousand Cuts&#39;, 11: &#39;London Boy&#39;, 12: &#34;Soon You&#39;ll Get Better (feat. Dixie Chicks)&#34;, 13: &#39;False God&#39;, 14: &#39;You Need To Calm Down&#39;, 15: &#39;Afterglow&#39;, 16: &#39;Me! (feat. Brendon Urie of Panic! At The Disco)&#39;, 17: &#34;It&#39;s Nice To Have A Friend&#34;, 18: &#39;Daylight&#39;}, &#39;producer&#39;: {&#39;Louis Bell&#39;, &#39;Taylor Swift&#39;, &#39;Joel Little&#39;, &#39;Frank Dukes&#39;, &#39;Jack Antonoff&#39;}}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">lover_album</span><span class="p">[</span><span class="s2">&quot;tracks&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">update</span><span class="p">({</span><span class="mi">19</span><span class="p">:</span> <span class="s2">&quot;All Of The Girls You Loved Before&quot;</span><span class="p">})</span>
<span class="n">lover_album</span><span class="p">[</span><span class="s2">&quot;genre&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="s2">&quot;electropop&quot;</span><span class="p">)</span>

<span class="c1"># Q: How would add an additional genre to the dictionary, like electropop? </span>
<span class="c1"># A: .update and append the genre electropop to list </span>

<span class="c1"># Printing the dictionary</span>
<span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{&#39;title&#39;: &#39;Lover&#39;, &#39;artist&#39;: &#39;Taylor Swift&#39;, &#39;year&#39;: 2019, &#39;genre&#39;: [&#39;Pop&#39;, &#39;Synth-pop&#39;, &#39;electropop&#39;], &#39;tracks&#39;: {1: &#39;I Forgot That You Existed&#39;, 2: &#39;Cruel Summer&#39;, 3: &#39;Lover&#39;, 4: &#39;The Man&#39;, 5: &#39;The Archer&#39;, 6: &#39;I Think He Knows&#39;, 7: &#39;Miss Americana &amp; The Heartbreak Prince&#39;, 8: &#39;Paper Rings&#39;, 9: &#39;Cornelia Street&#39;, 10: &#39;Death By A Thousand Cuts&#39;, 11: &#39;London Boy&#39;, 12: &#34;Soon You&#39;ll Get Better (feat. Dixie Chicks)&#34;, 13: &#39;False God&#39;, 14: &#39;You Need To Calm Down&#39;, 15: &#39;Afterglow&#39;, 16: &#39;Me! (feat. Brendon Urie of Panic! At The Disco)&#39;, 17: &#34;It&#39;s Nice To Have A Friend&#34;, 18: &#39;Daylight&#39;, 19: &#39;All Of The Girls You Loved Before&#39;}, &#39;producer&#39;: {&#39;Louis Bell&#39;, &#39;Taylor Swift&#39;, &#39;Joel Little&#39;, &#39;Frank Dukes&#39;, &#39;Jack Antonoff&#39;}}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">for</span> <span class="n">k</span><span class="p">,</span><span class="n">v</span> <span class="ow">in</span> <span class="n">lover_album</span><span class="o">.</span><span class="n">items</span><span class="p">():</span> <span class="c1"># iterate using a for loop for key and value</span>
    <span class="nb">print</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">k</span><span class="p">)</span> <span class="o">+</span> <span class="s2">&quot;: &quot;</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">v</span><span class="p">))</span>

<span class="c1"># Write your own code to print tracks in readable format</span>
<span class="n">tracks_dict</span> <span class="o">=</span> <span class="n">lover_album</span><span class="p">[</span><span class="s2">&quot;tracks&quot;</span><span class="p">]</span>
<span class="n">track</span> <span class="o">=</span> <span class="mi">1</span> 
<span class="k">for</span> <span class="n">song</span> <span class="ow">in</span> <span class="n">tracks_dict</span><span class="o">.</span><span class="n">values</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Track &quot;</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">track</span><span class="p">)</span> <span class="o">+</span> <span class="s2">&quot;: &quot;</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">song</span><span class="p">))</span>
    <span class="n">track</span> <span class="o">+=</span> <span class="mi">1</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>title: Lover
artist: Taylor Swift
year: 2019
genre: [&#39;Pop&#39;, &#39;Synth-pop&#39;, &#39;electropop&#39;]
tracks: {1: &#39;I Forgot That You Existed&#39;, 2: &#39;Cruel Summer&#39;, 3: &#39;Lover&#39;, 4: &#39;The Man&#39;, 5: &#39;The Archer&#39;, 6: &#39;I Think He Knows&#39;, 7: &#39;Miss Americana &amp; The Heartbreak Prince&#39;, 8: &#39;Paper Rings&#39;, 9: &#39;Cornelia Street&#39;, 10: &#39;Death By A Thousand Cuts&#39;, 11: &#39;London Boy&#39;, 12: &#34;Soon You&#39;ll Get Better (feat. Dixie Chicks)&#34;, 13: &#39;False God&#39;, 14: &#39;You Need To Calm Down&#39;, 15: &#39;Afterglow&#39;, 16: &#39;Me! (feat. Brendon Urie of Panic! At The Disco)&#39;, 17: &#34;It&#39;s Nice To Have A Friend&#34;, 18: &#39;Daylight&#39;, 19: &#39;All Of The Girls You Loved Before&#39;}
producer: {&#39;Louis Bell&#39;, &#39;Taylor Swift&#39;, &#39;Joel Little&#39;, &#39;Frank Dukes&#39;, &#39;Jack Antonoff&#39;}
Track 1: I Forgot That You Existed
Track 2: Cruel Summer
Track 3: Lover
Track 4: The Man
Track 5: The Archer
Track 6: I Think He Knows
Track 7: Miss Americana &amp; The Heartbreak Prince
Track 8: Paper Rings
Track 9: Cornelia Street
Track 10: Death By A Thousand Cuts
Track 11: London Boy
Track 12: Soon You&#39;ll Get Better (feat. Dixie Chicks)
Track 13: False God
Track 14: You Need To Calm Down
Track 15: Afterglow
Track 16: Me! (feat. Brendon Urie of Panic! At The Disco)
Track 17: It&#39;s Nice To Have A Friend
Track 18: Daylight
Track 19: All Of The Girls You Loved Before
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">search</span><span class="p">():</span>
    <span class="n">search</span> <span class="o">=</span> <span class="nb">input</span><span class="p">(</span><span class="s2">&quot;What would you like to know about the album?&quot;</span><span class="p">)</span>
    <span class="k">if</span> <span class="n">lover_album</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">search</span><span class="o">.</span><span class="n">lower</span><span class="p">())</span> <span class="o">==</span> <span class="kc">None</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Invalid Search&quot;</span><span class="p">)</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">lover_album</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">search</span><span class="o">.</span><span class="n">lower</span><span class="p">()))</span>

<span class="n">search</span><span class="p">()</span>

<span class="c1"># This is a very basic code segment, how can you improve upon this code?</span>
<span class="c1"># implementing crud &amp; can also add a spot for error check. if the input is invalid give them feedback on how to input corrrect format</span>
<span class="c1">#</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Taylor Swift
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Hacks">Hacks<a class="anchor-link" href="#Hacks"> </a></h2><ul>
<li>Answer <em>ALL</em> questions in the code segments</li>
<li>Create a diagram or comparison illustration (Canva).<ul>
<li>What are the pro and cons of using this data structure? </li>
<li>Dictionary vs List<br>
<img src="https://i.imgur.com/10X0ctO.png" alt=""></li>
</ul>
</li>
<li>Expand upon the code given to you, possible improvements in comments</li>
<li>Build your own album showing features of a python dictionary</li>
</ul>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">beatopia_album</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s2">&quot;title&quot;</span><span class="p">:</span> <span class="s2">&quot;beatopia&quot;</span><span class="p">,</span>
    <span class="s2">&quot;artist&quot;</span><span class="p">:</span> <span class="s2">&quot;beebadoobee&quot;</span><span class="p">,</span>
    <span class="s2">&quot;year&quot;</span><span class="p">:</span> <span class="mi">2022</span><span class="p">,</span>
    <span class="s2">&quot;genre&quot;</span><span class="p">:</span> <span class="p">[</span><span class="s2">&quot;Indie pop&quot;</span><span class="p">,</span> <span class="s2">&quot;Alternative rock&quot;</span><span class="p">,</span> <span class="s2">&quot;Dream pop&quot;</span><span class="p">],</span>
    <span class="s2">&quot;tracks&quot;</span><span class="p">:</span> <span class="p">{</span>
        <span class="mi">1</span><span class="p">:</span> <span class="s2">&quot;Beatopia Cultsong&quot;</span><span class="p">,</span>
        <span class="mi">2</span><span class="p">:</span> <span class="s2">&quot;10:36&quot;</span><span class="p">,</span>
        <span class="mi">3</span><span class="p">:</span> <span class="s2">&quot;Sunny day&quot;</span><span class="p">,</span>
        <span class="mi">4</span><span class="p">:</span> <span class="s2">&quot;See you Soon&quot;</span><span class="p">,</span>
        <span class="mi">5</span><span class="p">:</span> <span class="s2">&quot;Ripples&quot;</span><span class="p">,</span>
        <span class="mi">6</span><span class="p">:</span> <span class="s2">&quot;the perfect pair&quot;</span><span class="p">,</span>
        <span class="mi">7</span><span class="p">:</span> <span class="s2">&quot;broken cd&quot;</span><span class="p">,</span>
        <span class="mi">8</span><span class="p">:</span> <span class="s2">&quot;Talk&quot;</span><span class="p">,</span>
        <span class="mi">9</span><span class="p">:</span> <span class="s2">&quot;Lovesong&quot;</span><span class="p">,</span>
        <span class="mi">10</span><span class="p">:</span> <span class="s2">&quot;Pictures of Us&quot;</span><span class="p">,</span>
        <span class="mi">11</span><span class="p">:</span> <span class="s2">&quot;fairy song&quot;</span><span class="p">,</span>
        <span class="mi">12</span><span class="p">:</span> <span class="s2">&quot;Don&#39;t get the deal&quot;</span><span class="p">,</span>
        <span class="mi">13</span><span class="p">:</span> <span class="s2">&quot;tinkerbell is overreated feat. PinkPantheress&quot;</span><span class="p">,</span>
        <span class="mi">14</span><span class="p">:</span> <span class="s2">&quot;You&#39;re here that&#39;s the thing &quot;</span><span class="p">,</span>
    <span class="p">}</span>
<span class="p">}</span>
<span class="nb">print</span><span class="p">(</span><span class="n">beatopia_album</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{&#39;title&#39;: &#39;beatopia&#39;, &#39;artist&#39;: &#39;beebadoobee&#39;, &#39;year&#39;: 2022, &#39;genre&#39;: [&#39;Indie pop&#39;, &#39;Alternative rock&#39;, &#39;Dream pop&#39;], &#39;tracks&#39;: {1: &#39;Beatopia Cultsong&#39;, 2: &#39;10:36&#39;, 3: &#39;Sunny day&#39;, 4: &#39;See you Soon&#39;, 5: &#39;Ripples&#39;, 6: &#39;the perfect pair&#39;, 7: &#39;broken cd&#39;, 8: &#39;Talk&#39;, 9: &#39;Lovesong&#39;, 10: &#39;Pictures of Us&#39;, 11: &#39;fairy song&#39;, 12: &#34;Don&#39;t get the deal&#34;, 13: &#39;tinkerbell is overreated feat. PinkPantheress&#39;, 14: &#34;You&#39;re here that&#39;s the thing &#34;}}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">beatopia_album</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;genre&#39;</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>[&#39;Indie pop&#39;, &#39;Alternative rock&#39;, &#39;Dream pop&#39;]
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">tracks_dict</span> <span class="o">=</span> <span class="n">beatopia_album</span><span class="p">[</span><span class="s2">&quot;tracks&quot;</span><span class="p">]</span>
<span class="n">track</span> <span class="o">=</span> <span class="mi">1</span> 
<span class="k">for</span> <span class="n">song</span> <span class="ow">in</span> <span class="n">tracks_dict</span><span class="o">.</span><span class="n">values</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Track &quot;</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">track</span><span class="p">)</span> <span class="o">+</span> <span class="s2">&quot;: &quot;</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="n">song</span><span class="p">))</span>
    <span class="n">track</span> <span class="o">+=</span> <span class="mi">1</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Track 1: Beatopia Cultsong
Track 2: 10:36
Track 3: Sunny day
Track 4: See you Soon
Track 5: Ripples
Track 6: the perfect pair
Track 7: broken cd
Track 8: Talk
Track 9: Lovesong
Track 10: Pictures of Us
Track 11: fairy song
Track 12: Don&#39;t get the deal
Track 13: tinkerbell is overreated feat. PinkPantheress
Track 14: You&#39;re here that&#39;s the thing 
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

</div>
 
