3 Ways to add CSS
1.Inline
2.External
3.
We can set background as image or color
<style></style>

Selector Type	                            Specificity Points
Inline style (style="...")	                            1000
ID (#id)	                                             100
Class (.class),pseudo class and attribute                 10
Element/Tag (h1, p, div) and pseudo element selector	   1

1) DESCENDANT COMBINATOR (space)
------------------------------------------------------------
div p {
  color: blue;
  /* div ke ANDAR kahin bhi (kitna bhi neeche nested ho) jo <p> hoga, match hoga */
}

<div>
  <p>Match ✅ (direct child)</p>
  <section>
    <p>Match ✅ (nested hone ke bawajood)</p>
  </section>
</div>

Use case: Container ke saare andar wale elements style karna, depth se farak nahi padta.


2) CHILD COMBINATOR (>)
------------------------------------------------------------
ul > li {
  color: green;
  /* ul ka SIRF DIRECT child <li> match hoga */
}

<ul>
  <li>Match ✅ (direct child)</li>
  <li>
    <ul>
      <li>Match NAHI ❌ (yeh li ka child hai, ul ka nahi)</li>
    </ul>
  </li>
</ul>

Use case: Sirf ek level neeche wale elements chahiye ho (jaise navbar top-level items).


3) ADJACENT SIBLING COMBINATOR (+)
------------------------------------------------------------
h1 + p {
  font-weight: bold;
  /* h1 ke TURANT BAAD aane wala p (bilkul agla bhai) hi match hoga */
}

<h1>Title</h1>
<p>Match ✅ (h1 ke bilkul turant baad)</p>
<p>Match NAHI ❌ (doosre p ke baad hai, h1 ke nahi)</p>

Use case: Heading ke turant neeche wale paragraph ko special style dena.


4) GENERAL SIBLING COMBINATOR (~)
------------------------------------------------------------
h1 ~ p {
  color: purple;
  /* h1 ke BAAD aane wale SAARE p siblings match honge */
}

<h1>Title</h1>
<p>Match ✅</p>
<span>Kuch aur</span>
<p>Match ✅ (beech mein span aane ke bawajood)</p>

Use case: Kisi element ke baad aane wale saare siblings style karna.


CHEAT SHEET (ek nazar mein)
------------------------------------------------------------
div p     -> Descendant: div ke andar kahin bhi p
div > p   -> Child: div ka DIRECT child p
div + p   -> Adjacent: div ke turant baad wala p
div ~ p   -> General sibling: div ke baad ke saare p

VISUAL TRICK:
(space) -> sabse "loose" connection (kahin bhi andar)
>       -> "tight" connection (sirf apna bête)
+       -> "next-door neighbor" (ek hi)
~       -> "sab neighbors jo baad mein aaye" (multiple)

-----------------------------------------------------------------------
CSS Box Model:
body{
  margin:0;
}

If we got two block elements Margin Collpses then we can use margin top or bottom  

"TEXT wale properties INHERIT hote hain (jaise DNA), BOX wale properties INHERIT NAHI hote (jaise Property/Paisa)"

box-sizing:border-box

<ul class="main-nav__items">
                <li class="main-nav__item"><a href="packages/index.html">Packages</a></li>
                <li class="main-nav__item"><a href="cutomers/index.html">Customers</a></li>
                <li class="main-nav__item"><a href="start-hosting/index.html">Start Hosting</a></li>
            </ul> ab main le last wale anchor tag ko pading diya 20 px toh left aur right se lgega but li ko diya toh all 4 sides se lgega aisa kyu

Mnemonic:
"Inline-block Row mein sabko FIT hona zaroori — ek ne 100% maang li toh doosre ko NEXT LINE jaana padega!"
Isiliye calc(100% - 60px) sahi tha:
Logo(~60px) + Nav(100% - 60px) = Exactly 100% → Same line pe fit! ✅
----------------------------------------------------------------------
Selector and Other Features:


--------------------------------------------------------
Background Images:
background:




-----------------------------------------------------------------------
SCSS/SASS:
