---
layout: post
title: 13 Cascading Style Sheets - CSS
date:  2016-10-22 00:00:00
description: Codi per modificar les classes CSS utilitzant pseudoclasses
---

Cascading Style Sheets (CSS) és un full d'estil que descriu els estils de text que utilitza el llenguatge html per renderitzar una pàgina web.

Podem adaptar aquest full d'estil al nostre sistem autilitzant **pseudoclasses** que són xicotetes variacions d'una classe. Així utilitzarem ordres per a dir com es comportarà la pàgina web abans o després de l'aplicació d'un estil.

Hem aprofitat aquest manual [Styling ordered list numbers](http://www.456bereastreet.com/archive/201105/styling_ordered_list_numbers/) per modificar el llistat de nombres de manera que ara apareixeran modificats, destacats com voliem.

Si utilitzem el codi que aparta aquest manual i l'afegim al final de l'arxiu .css canviarà les característiques d'aquestes ordres, funcionant les últimes característiques que llisca de l'arxiu.


```
ol {
	counter-reset:li; /* Initiate a counter */
	margin-left:0; /* Remove the default left margin */
	padding-left:0; /* Remove the default left padding */
}
ol > li {
	position:relative; /* Create a positioning context */
	margin:0 0 6px 2em; /* Give each list item a left margin to make room for the numbers */
	padding:4px 8px; /* Add some spacing around the content */
	list-style:none; /* Disable the normal item numbering */
	border-top:2px solid #666;
	background:#f6f6f6;
}
ol > li:before {
	content:counter(li); /* Use the counter as content */
	counter-increment:li; /* Increment the counter by 1 */
	/* Position and style the number */
	position:absolute;
	top:-2px;
	left:-2em;
	-moz-box-sizing:border-box;
	-webkit-box-sizing:border-box;
	box-sizing:border-box;
	width:2em;
	/* Some space between the number and the content in browsers that support
	   generated content but not positioning it (Camino 2 is one example) */
	margin-right:8px;
	padding:4px;
	border-top:2px solid #666;
	color:#fff;
	background:#666;
	font-weight:bold;
	font-family:"Helvetica Neue", Arial, sans-serif;
	text-align:center;
}
li ol,
li ul {margin-top:6px;}
ol ol li:last-child {margin-bottom:0;}
```

Podem obtenir aquest resultat.

Llista d'animals:

<ol>
    <li>Gos</li>
    <li>Gat</li>
    <li>Talpó</li>
    <li>Cuc</li>
    <li>Rabosa</li>
    <li>Mosquit</li>
    <li>Teuladí</li>
</ol>

