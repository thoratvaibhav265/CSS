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