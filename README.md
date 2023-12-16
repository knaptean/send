# send
```css
/*
////////////////////////////////////////////////
|||||||||||||||||| Variables ||||||||||||||||||
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
*/

:root {

    /*||||||||||[ Colors ]||||||||||*/

    /* Button states: active, hover, pressed, disabled */
    /* Button types: primary, secondary, danger, default, menu, icon, highlight */
    /* Framing elements: background, section, card, input, modal, modal overlay, link, menu, tooltip, codeblock */
    /* Text colors: Title, subtitle, body, note, figcaption, placeholder, tooltip */

    --color-primary: #202020;
    --color-primary-light: #22334a;
    --color-primary-dark: #000;
    --color-secondary: #0044ff;
    --color-secondary-light: #0088ff;
    --color-secondary-dark: #0033aa;
    --color-background1: #fff;
    --color-background2: #f0f8fa;
    --color-background3: #eee;
    --color-background4: #ddd;
    --color-background5: #ccc;
    --color-content1: #000;
    --color-content2: #333;
    --color-content3: #666;
    --color-content4: #888;
    --color-content5: #aaa;
    --color-success: #000000;
    --color-success-light: #000000;
    --color-success-dark: #000000;
    --color-danger: #000000;
    --color-danger-light: #000000;
    --color-danger-dark: #000000;
    --color-info: #0044ff;
    --color-info-light: #000000;
    --color-info-dark: #000000;
    --color-warning: #000000;
    --color-warning-light: #000000;
    --color-warning-dark: #000000;

    /*||||||||||[ Typography ]||||||||||*/

    --font-heading: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;;
    --font-body: Roboto, Oxygen, Ubuntu, Cantarell, system-ui, -apple-system, BlinkMacSystemFont, 'Open Sans', 'Helvetica Neue', sans-serif;
    --font-mono: monospace;

    --text-small: .75rem;

    /*||||||||||||[ Spacing ]|||||||||||*/

    --radius-inner: 3px;
    --radius-outer: 6px;

    --elev0: 0 0 3px var(--color-background1);
    --elev1: 0 0 2px #00000020;
    --elev2: 0 0 3px #00000030;
    --elev3: 0 0 4px #00000040;
    --elev-glow: 0 1px 5px #0000ff40;

}

/*
////////////////////////////////////////////////
||||||||||||||||||| Global ||||||||||||||||||||
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
*/

* {
    font-family: var(--font-body);
}

html {
    background: var(--color-background2);
}

/*
////////////////////////////////////////////////
||||||||||||||||| Components ||||||||||||||||||
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
*/

.container {
    padding: 1rem;
}

button {
    min-width: 6rem;
    border: none;
    font-size: 1rem;
    border-radius: var(--radius-inner);
    padding: .2rem 1rem;
    color: var(--color-content-dark);
    background: none;
    cursor: pointer;
    box-shadow: var(--elev2);
    transition: box-shadow 250ms;
}

button:hover {
    color: var(--color-content-light);
    box-shadow: var(--elev-glow);
}

button.primary:hover {
    color: white;
    background: var(--color-primary-light);
}

button.primary {
    color: white;
    background: var(--color-primary);
}

.btn-grp{
    font-size: 0;
    display: inline-block;
    box-shadow: var(--elev2);
    border-radius: var(--radius-inner);
}
.btn-grp>button{
    border-radius: 0;
    display: inline-block;
    box-shadow: none;
    border-right: 1px solid var(--color-background3);
}
.btn-grp>button:hover{
    border-color: none;
    box-shadow: var(--elev-glow),var(--elev0);
}
.btn-grp>button:first-child{
    border-radius: var(--radius-inner) 0 0 var(--radius-inner);
}
.btn-grp>button:last-child{
    border-radius: 0 var(--radius-inner) var(--radius-inner) 0;
    border:none
}

div.card {
    padding: 1rem;
    display: inline-block;
    margin: .5rem;
    background: var(--color-background1);
    border-radius: var(--radius-outer);
    box-shadow: var(--elev1);
}

.menu {
    width: 8rem;
    box-shadow: var(--elev3);
    background: var(--color-background1);
    border-radius: var(--radius-inner);
    overflow: hidden;
}
.menu>button{
    margin:0;
    width: 100%;
    box-shadow: none;
    text-align: left;
    border-radius: 0;
    font-size: var(--text-small);
}
.menu>button:not(:last-child){
    border-bottom: 1px solid var(--color-background4);
}
.menu>button:first-child{
    border-radius: var(--radius-inner) var(--radius-inner) 0 0;
}
.menu>button:last-child{
    border-radius: 0 0 var(--radius-inner) var(--radius-inner);
}
.menu>button:hover{
    background: var(--color-background3);
}

button.i {
    min-width: 1rem;
}

input{
    border:none;
    background: var(--color-background3);
    border-radius: var(--radius-inner);
}

.wysiwyg {
    margin-top: .4rem;
    padding: .4rem;
    outline: none;
    background-color: var(--color-background1);
}
```
