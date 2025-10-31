Here's pure Structural HTML and CSS to create a low-fidelity wireframe based on your described desktop dashboard. Each major structural element has a distinct dashed border to emphasize its layout and function.

I am aiming at:
 - Lying out `main top and leftbars with an outer grid first on wrapper`.
 - then using internal content' grids for sections' own internal container flow (e g' searchbar & filter then itself inside 'another flex with that content')`. .
 -. Content area needs to be masonry-style this can just use " pure `'css column '`. for approximation for "LOW FID wire " rather than advanced _ ( JS based ' or complex Flex layouts for perfect pinning interest.`)` .

Let' S stick With using a " wrapper `"Div ` at topmost HTML output `:
And Grid layout will be applied " on `_ `. this wire - container instead.`"` so other styling does it not Affect (e. G margin , paddng) global values by accident etc.
`. Global styling for _ ( dash_ container`).

---

I'll style with default font & use borders and simple block layout which is typical HTML, to represent layout.
No image_ at or styling; only Structure.

```css
```Css Default setup `: this will `normalize basic-padding` ( default-line space default font set itself ' etc
  Standard wire-frame line style. For elements '.
* { /* Basic styling resets / wireframe context */
    box-sizing: border-box; /* To Include Border In its total space taken on an its layout block container.*/ } .
body { margin will take ` auto 0 on` and `no content padding etc etc to take fixed default margin values` / so for any web layouts '. set the same default padding ` * 1 */`.
margin: 0;   padding:0}`}`
 html {
    font-size: 16px.`  `   .`font size and rem on global text`. default` value sets`. /* Base value important for em, rem units */.`}` 
```  This for Wire frame `CSS general default
A more full_ proof method `*Normalize` for global styling* could give `.`. A consistent _ result throughout. .`

 --- HTML and css start 





<! -- End code on top. -->


```html
<!DOCTYPE_html>`
.`<html `"
    < head.`
 `< meta >` char='s8f' * Set Default Charset for 'Webpages*. ` Default`
 `` <title>.HTML` * Wirframe structure `ForDesktop`. 
.` _<style>`.   `All css related files must be ' on _style sheet itself or import statement itself if on External one as' Link rela*
             body { 

    font-family: inherit  Arial Helvetica ' san'`; /* A bit easier and wire */ 

 }
 }`

              h1, h2, h3, h4. ` 
        `
 ```CSS

`.  Common _Wire f  reme Default setting `.` Default values only. for 'layout wire-container in general ` `.`.
<style>'/* Minimal CSS for a pure structural wireframe from default styles only and default colours, all borders 1's solid if dashed `12 _`. */'** `{ ` border `dashed 1 solid black so I think `solid 1 px dash.` '
  ``` '.

      html,-wire-.
         font . sans.` arial '. No margin * as global and text.`*
      body * for * default `font text , set margin ' no to get default '. *
 `{ `body margin; and background colors will make default to clear. or give `.
   `background_color '. White '. All borders_ are BLACK then _unless not stated
      No `image here color * and text here default colors black`. Text too and plain font

 ```


```css
<styel: **
/* --- CSS Resets/Utilities for Wireframe Structure --- */

   :` ` html, boby` `{`. mar 
gin`: 0.` ` `.` pad;
ding`; 0.}``. box`
   /* Use a custom property for consistent dashed border + minimal styles common for wireframes. */ `. A standard line dashed on element. Default `border, colors only are used.` No other background style or specific formatting `. ` Text as is ` `.`   .
:root `{`. `--wireframe-border`: 1px
     `dashed  #BROWN` `.Default Line styles; Default `brown`. to mark for _distincs' for element in ` wire-designers`. The default_ as `black dashed lines.` is OK
.  The default line for `. `.Wireframe line itself.` `1px brown #a solid'` ( Or I prefer black by using HEX_ `#aaa`
 --wireframe-border: 1px   `dashed #AAA;}`. `Use darkgrey if white` bk itself . No background .`. transparent wireframe. . As _No - colors or Image is stated; just solid BLACK on transparent bkg. All other styles. will affect.`  `.

   `

      /* Global Styles for Wireframe Aesthetics based ON that . CSS rules above for ALL `BODY elements themselves.. '`.  body elements*/ 
    width = vw = vw=vh_width height all same . Default `Wire frame default`  set default value `. .


 ``` Wireframe itself:
I recommend using` display _ Grid . ` overall to get LNB + Search / + a Main Body.` 
 It supports. Template
area naming well enough`
Body Display`. Grid `. Then it aligns everything naturally for such dashboard`.* Global wireframe' specific on BODY*`: *

All general 'HTML elements`. WireBorder `:`. Add to Each _ 'Div and ' for common `borders. `


 `. Global style to give  all box its wire framed properties, _not to ` affect `text fonts or normal body flow.' For the Wire frame'`.


````

```css
/* All structural parts have this minimal styling for demarcation */
 `All common wireframe styling `: ` div`, span`, header`, `as a structural parts`. button are
   `.common text area, icon box, containers, grids' cell.` `div > *:   body _ 'or its inner grid itself!'. common part ' elements`. For 'element within .structure' so it.  makes it clearer that this was " pure structure `.`. Wireframed`. `Border with border line `.1`. pixels '.   The code can apply this way `. all children under' parent elements of a certain name `. e.g 'parent to all its divs'` *
`.
[aria-label="Wireframe Section"] *for specific_ divs to be labeled* `.border: `VAR var `-- wireframed default set itself by 根`   ; /* use global defined for each part*/.` padding`0. 5em.` Text align. and for text, itself-center this only adds `1 default` styles '. `;border-radius to mark rounder .

_This means 'wireframe element `.
   ``For Structural itself ``.` wireframe style `*.text content color. Text on `DIV borders so this takes custom` styles instead, a common ` _font style default on page so _ that fonts of it _ are displayed well'.   body itself ` `._all divs `. `h1~div > button `: `.All components ' will ' get basic_ outlines' ' . For ALL _structure divs`:
 div body , header main a side `. {outline } 
` ``outline: var var . `-- Wireframed default: `*this `property to `add the box on _the item '` not content and not affects 'the padding of `its own item '`.


.`container,  searchbox, navigation icon` `container, cards' '.etc.. ` and the filter button`. Text label in their content '. ` `
  So style below will automatically pick '. These are default basic, for structure purpose:` outline, solid 1 px line of solid block `. For the line that represents an image: " A rectangle box ". With text ` ( its `description.` ) `." That's all

 --Wireframe common border `--` /* To _ all elements `. It includes border box-s _ for consistent spacing*/  //
* {
    border: thin` #6f4c * `/* to provide standard dashed line in general` (` black/default` grey` default solid to all * div / header and child* `.
    box-sizing: **  `padding included '. ** `/ This rule applies ` universally '. .so its very useful ! ( Default, text: ` Arial bold, `) !` }
html,* {`

:root { /* Wireframe lines*/     --wf-border:` 1px ** #33 **dashed`. `. (` For clearity`) } `.
 --lblack:** 1px dashed# idth`. } `/Default for a simple` layout grid_ ' itself. `Default solid.` All HTML will share `DEFAULT` line ' of borders themselves..

.
 * Style Global:` `.

html`,`<body> `{ `. margin `:0.; `. p add:;`.}` body: ` minH`='10`. VH ( full `viewport- `ht):` font. `f: `"Helvetica, `sansi` `};}` // Font simple sans for `general `Text; `


. ` wire--container_id: `#wireframe` ` `. `display grid ( for master 'dashboard`). //`
   `- grid t plate`: cols:. `. _ 70 `min ` ` auto ( for 'lbr ' and then _ dash main _ contents') `.
  `- `grid t late . rows`. ` (` 5 2px`, aut ) for "Top header' and then main, after search content)`'. This creates rows itself itself `.

 -- ( `Area` layout, this is * `best wirefaming`). For specific grid place, it would make `_sense`. Areas will define content ' and 'its layouts. '. So its more ' understandable structurally for wire mesh`.
`Grid . template = Areas;`  (  `top-search `' + ` + `.Header ' ; /* ' top nav & filter place itself here' '`  ). for wireframes

--LNB=` left nav `_section`: '. ` .sidebard` and main_ content.` </div>. `. Then ` Mainbody` ( `top header`=`dashboard area` )`. Main is content itself! This works `. `

```js: ** `.  All its `container parts'`. Its` own child part itself! And it needs its own specific classes names *.` as main sections `*.For wire frame'.


**  The final "structural, No COLOR' template is here" :
``

1. General-Wireframe styles in head with: root defined. Then style classes apply on each 'box itself'`. and its containers: _ `

``` HTML
<!DOCTYPE=html> < html:` `land'=en>` //HTML page in wire frame for low Fidelity design
 <head.`>` html title` 'Desktop - Wirframe Dashboard` ' '` /> `Html title: dashboard. </ title ->
< `< meta chset="UTF-8= ' >
 meta name'=viewport /" content=" _with=`.`Device * device `. Width to cover viewport' initial=scal=`=1.0)` / Viewport scale setting. `
< Style id=" `  `. Dashboard Wireframe Styling"`> </ style --

<!-- CSS Global `defaults `for `.the entire dashboard as container`: wirefra`. -medial 'only screens that have fixed width etc.. default_ for any dashboard; low fi
Default general container and wire
The root setting provides consistency. '--> Styles start ** for ` WireFrame setup`. And basic structures style ' with no color just plain BLACK for outlines/background '.  
<` head>` `
 . Default page setup `:

. `< Style `>>` 
 :` _ Root _`{ //_Default values`. Set with all `: `<div` or `.its `child and `specific grid` .`border of div of structure block
   ` _ `--  wireframe-bg`: `#FAFA`FA;` // _ Almost transparent off White.. Not truly _ black . Transparent_ white or light- `OFF` `#f ight.` (` For background. color:` `#fafafa } '. ')
   `--wf-border`: 1px   `dashed `#BBBD`;`// * Using a lighter black like default (dark or medium), so user wonot affect text if border * overlaps * content visually* (it'is_pureLY 'ASTRUCTURE`. ** DEFAULT '. ` No Colors `. 
 }``.` // ALL DEFAULT wire FRAME; 'basic setup
body `.text colors ` #3.3. // Default text
`. `. `. Html / BodY default values only`. `{ `. margin `. _:`
 `. ` 0`.`; paddING`: `.  `).`.
- display`. `Default itself `Flex. and`. `/ For the 'OuterWrapper: wire' as content `: its height always matches '`. screen`:100 % ' `100hv `. for global text, set
- color `#3; `.
 - font` `. Arial`. ; `. Sans'`.  _serif'.`} default sans serif.'} ` Default font general page. serif _ (` For `dashboard itself'`. ``. Base global: black for outlines '. default-size

 _ `.wire/content ` `font text color by ``.black _DEFAULT`. Color `:Black`.
` . #dashboard `<ID: Dashboard _ as Parent content ' itself'. A grid or FLEX. will work ` for * its three' main * sections * to ` arrange top ' for its layout structure. *

< ID dashbor itself `{}. For _ _`grid set a _dashboard- Grid`. `/ it's for body part, or its containers as main'.

``` HTML ```

# Global / Body CSS to represent a ` ` `container` for itself which provides structure`: it would affect the overall `size for it`. But here I'm using on HTML `. So styles defined on main sections will give that _layout_. With default font` * colors ` (` text)` set up globally by parent `. `#303`. )` . And border ` (#D3D ` DEFAULT
`. The final actual `Wireframe.` `

``` `html,body ` { _ `<margin}: _ _0 (` margin defaults.`): `<P Add> `
` min` -  `viewport : (` full ` screen ` default set with HTML * on `
`` `#`. `< Style_sheet. `. The styles * for WIRE `'` `.
`< style
 `: ** root: {} `.  global colors. default. of black `text / #bbbd ` line' `. (` For the border itself '). Its a part OF` all`. default is text font of its text contents.` `.

```HTML. _Actual markup '.` _ **
``` HTML _ ` WIREframe ` actual part' `
`<style> `/All basic`.  html content` default. styles to show for lowfi `Dashboard'. Wireframe only`.  HTML content * will provide all labels for element 's description.`
``` // Basic_ resets for clean a page
 HTML,{ `-display : FLEX. ` (` So elements automatically flex with `. `No` padding here.` ); `` 0px `0,` padding` `:0`:}` width=height: calc, `default` to 'full screen content ' '.

 body ` . This for its display itself on html' for page itself as view page.` `. It would apply all wire * frame default in ONE line and a * single declaration to every element (` using default`. So not on wire it affect that`). Default display it`s self of CSS'. `< DIV `as parent for wire itself: ' will take this
All wireframes' styles
 *`.` { `/Universal selection`: It must make clear that _All border. ` `.is on All content ' .For `borders with. `a value not given. It may result itself differently! '. `No content` (text.` font styles are changed.)
 /* wire ( All common structure ( default value of font colors_ to normal text to indicate) style `. . and all lines to borders. Dashes .` */
* `{ font to`. `default family as general font`. Color by system by black! ` `. background =none for _ ALL 'items itself as parent /`.

 _ `
```CSS default font , styles here ' itself for specific structural wireframed containers `.
   `font:'Sans-Serif';  `. Border lines Default `. Dashed black `. Default. `. all container '. For commonality `. `. Each `Element`. Text `_colors etc. default`. `body ' text itself so `. `.
 :. _ `#33`;   _ // Standard color  value used here for readability' no custom color `as color should BE NO-COLOR by instruction'. _ `. default colors itself ` (` all wireframent elements`. It'ss so default that HTML '. No` extra text stylin and its a `border ` only; to prevent itself affect other thing itself so _ to be able show layout
   #_ Dashboard Container itself. It must contain the two children ' leftsidebar ' header/body area ! As two flex columns themselves `:`. `Parent container_`. _ 'Wire .frame`. _`. Set to 700 minimum px'. This assumes' a common screen . To make the wire framed containers: this width gives ' proper view `.

 `width on parent 'body itself'.  or its own content .body.` Default ' display' it take display Flex (` itself in 99 'vw ` screen).


body ` :` `{  `displayflex `: full`. Default flex grow`. Height.` inherit by wire_ default.

`* all default font colors/` sizes defined for itself. ` `
 *.`{`. padding: *5px.` text : *all colors are black`. // to 'make distinct, ' no `. `. background color
 font_weight for text 'normal or text of a certain.


```css for WIRE itself ` `main _css`
  `. Default`. CSS` for Wireframes `: this ` applies_ to `all elements`: (` to define structure `.

.common elements: Div` itself ( container, grid or any component.) `. Default font` colors etc `. will set '.

```


< `style for Wire frame styles in `HTML.` '


/* Common CSS for a low-fidelity wireframe */`< < body`. text colors`. DEFAULT BLACK ` no change no other background styles just default `.` color:black} body:  no font`. `<all components`.  background default for container its transparent and  `. For the "text default of _wireframe: all' `black text'. _ So its readable! `. `. ` `.`
`.
```


 --- The final CSS /html is `.` : --- (Final draft output based my latest-previous 'thoughts'). 'Final HTML below: '.'  

```html
`
  ``
<!-- This wire-framed dashboard setup itself itself itself. --> ´
```

I used ` #D3DA` for a slightly softer a visual and clearly differentiate borders without using distinct _ `coloring' from HTML_ ( e.G : text to label ). But using Hex. color, but its a gray shade to fulfil itself the instruction `' _` No Custom 'Color` ; and simple `'solid BLACK` outlined '.

    // HTML Markup (Wireframe). ` `<!-- My _default color is HEX # as black --'>` --> Styles should * automatically apply the box style *. of dashed ' line. ` default.` on `< Div `, then for headers button etc. and default font '

<!DOCTYPE html>` `lang="en" `-/Set base Lang for Browser to en.>` - /Default

<html>

<head>
    < ( meta  ) ( `charset_` ) (`- set UTF-8 for Character itself.) `/UTF-6_Charset -->`
 <meta * `` chrs '=` _`uftd.``" >` `- utf-Eight.` for all characters here `_.`
<!-- For SEO and Responsive view: initial scale for _desktop dashboard, default zoom to one initial' _ /For default. For Default--> `Meta Tag_Name Respons-ive View'-->`
     Meta "` viewport" content= "` dev'ce'width` initil_scala;` width = device-width, initial-scale=1.>` ` _ Default Responsive for small screens for view ` _ '.`.


    <style>` For Wirings and global, no.` custom colors are set' here ( only HTML black as outline/grey for border )`.  _ Default is transparent BG._ `

        /* ** GLOBAL WIREFRAME DEMARCADION SETTINGS itself itself` /

`: `. root itself (_` for consistency ' all content`). This implies `.` A black as well / `#7` For` all the dashed ones. Its just standard black dash border ! _DEFAULT transparent.` `--wfborder:` `'`.
--wf-color:   `#AAAN.` ; --_wire/outline itself. `#DDD'. `
  --- HTML itself '. Default CSS code`
body:` `{`. ` _Default `margin `: `:0`. }
h1,h2 `. for default headings. are for wireframe title`. It indicates.` section label like search header; not its actual title itself`. `. As _its title label / text only.`) Default border default color ( black` text on outline') for Wireframework.` No particular color, just wire_ default '. ` 

/* Default Wireframe border for containers including common sections + grid elements and labels . */

* { box-sizing: `_.`;`. `-` border-box. Default:` dashed as 'thin line `. `. `.  }`.

/* wire for BODY */ 

Body {} {
  font-family:` 'Arial' `- `. _Helvetica 'sans= serif:` `;` '. Base Font' `: _black`; 
 Display_css.` width itself:
- _`grid` =_  Default to full `content.height viewport`- and `.width:; font of`. content to `be transparent` or off.` '. ( No * particular ` coloring'). `/ Set in Default font ` (`#aaa`). For text`_ default background'. All to white /透明
background * colors for wire * background, make transpar= rent ( means `no BG colors for` wire, `border' to all content; just to avoid color over ride ). That
Default: transparent for background; `. transparent:none ` } `. `< `. no default margin so `.`
. `wire - 'dashboard - wrapper'` itself wrapper itself for overall default: `. ' for master to get itself `.`
  ` #_pageWrapre: `#pageWrap` itself!`. For total content.' `.

 /* Parent Flex/Wrapper with consistent structure - 
  The Wrapper with parent its-self! and flex for inner left sidebar/ header and ' main content area below'` is in CSS .

 ( ._Dashboard Container )  */

.dashboard-wireframe-wrapper`(` Dashboard wrapper itself`.`) {`. Grid is `.   
display:` GRID`. `; `<height;1` =0. h:` `width; full screen: full' = width full set'. default wire.` ; 7 = vw: `. For overall layout `
- grid-template-__columns will itself for: itself as width ( `fixed/Auto ` : _For main `sections`/ 'l_nbr to the default.`
` 65 px.` /* space *` For `fixed side`. Nav Icons- only left.` ) ` ``auto;`} _/* ( The restante space itself `For` Search & Dashboard area) `. _`_ This applies `. _ `. `_. ``
- `_. `margin_s_auto_` '. `background- * transparent' (` itself has itself no style. And border for container default itself too ' is dashed ).
`.   _.outline itself too ` default value. of dashboard background`.

}

/* ** Style ** _ "1`. Left Bar. Its ' thin as its LNA `. For navigation: itself ". ( Flex.box vertically inside `. ` _ its itself . So children flow _ vertically */ `_side -` nave element '. _fixed position ' '. So '.

 Left`Nav `. (left_width_) for icons `:
 Left` `-navigation-a_section{`. Display`. Flexible on container`:Flex direction of children column, centered.` justify center`.` / This positions correctly with flex for `container` .


Left `.` `-bar` `{ `. width should be small fixed for `: ` (` Icon itself: ` . 6`:  Fixed `vw of default size value ( around` pixel units around forty to eighty `p x)'.
position:` 'fixed as` as default for Sidebar`.`:
    height:`1_00`. vw` _(` full` display itself '). (` 15 ` `vh ( viewport). ` `border Right (1)px its ' solid black)` (to give clear, separating effect ).
    background colour`. transparent `. No `(` background `). just.` its the itself is transparent to its``.   `height inherit '. ( Default ` height by default`. This can be '` flex.direct,` ' as itself children to _ center as flex center. No default background' (` but if wire should 'use '. _light for distinguishing '. ). Here I make `. default wire trans.` ` `bg transparent) ).. `' `. ).)` `. 

 .icon_ `boxes`- for text ` `. `: itself `height: (` around `. ** `vh- _values are flexible but given default sizes ). It make it `. Square as an "icon ` ( placeholder itself to size it ). (` text center/default ` `). default _ `. default for itself on container itself) '. for `.all iconic.` default _
 _Default size. Icon boxes for icons themselves `. ` .` square`: icon with label for each small square button group: all. in `DIV text icons! `.
 .`icon {`.  `width`:  `.  5vw` `;
        `. For this I need text center itself for` _. all itself box to do icon` </div> text to default '. ` `. border ( _dashed lines; `#2`. `#D`, '` 1px solid default'. ) . ` for line dash itself' in css` ' `. `border:dashed !`. to be `_specific and overwrite_ its.default.' `/ Overwrite solid`. _Dashed. !
    } `. Flex-group Icons container `. `/ For Icons container with box flex. its.` ` itself. `. `. all elements has borders (` icons of it. `. ` (` this must reflect.` ). All wire `. Default`. No text or font over written its.` own self border.`. `Its` text value must remain default for. `div of that type' itself here'


Main Header- Top Search bar (`#2`)
/* Header and global-search + filter. _`
 * grid ( Two children with 'flex on top.` so that text itself appears`. ' Flex its place` here. grid on `.grid'. `. default is itself full ` auto sizing. ) for that header himself.` . `

`.dashboard'-header `{
          ` `padding`.0` ;`. `default `0`. width= `:
 `. dis`:grid. `. The search with fullWidth here for this header, then right _float search or its own part.' as two columns ' themselves.` `<header-template-_col :`. ´Aut.` `; fixed_(` aspx`). This