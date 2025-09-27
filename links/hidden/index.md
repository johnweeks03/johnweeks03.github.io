<html lang="en-US" dir="ltr" class="dark-mode"><head xmlns:og="http://ogp.me/ns#" xmlns:book="https://ogp.me/ns/book#">
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>A Taste of Number Theory</title>
<link xmlns:xlink="http://www.w3.org/1999/xlink" rel="preconnect" href="https://fonts.googleapis.com">
<link xmlns:xlink="http://www.w3.org/1999/xlink" rel="preconnect" href="https://fonts.gstatic.com" crossorigin="">
<link xmlns:xlink="http://www.w3.org/1999/xlink" rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@24,400,0,0">
<link href="_static/pretext/css/theme.css" rel="stylesheet" type="text/css">
<link xmlns:xlink="http://www.w3.org/1999/xlink" href="_static/pretext/css/ol-markers.css" rel="stylesheet" type="text/css">
<link rel="stylesheet" type="text/css" href="external/custom-styles.css">
<script>
var runestoneMathReady = new Promise((resolve) => window.rsMathReady = resolve);
window.MathJax = {
  "tex": {
    "inlineMath": [
      [
        "\\(",
        "\\)"
      ]
    ],
    "tags": "none",
    "tagSide": "right",
    "tagIndent": ".8em",
    "packages": {
      "[+]": [
        "base",
        "extpfeil",
        "ams",
        "amscd",
        "color",
        "newcommand",
        "knowl"
      ]
    }
  },
  "options": {
    "ignoreHtmlClass": "tex2jax_ignore|ignore-math",
    "processHtmlClass": "process-math"
  },
  "chtml": {
    "scale": 0.98,
    "mtextInheritFont": true
  },
  "loader": {
    "load": [
      "input/asciimath",
      "[tex]/extpfeil",
      "[tex]/amscd",
      "[tex]/color",
      "[tex]/newcommand",
      "[pretext]/mathjaxknowl3.js"
    ],
    "paths": {
      "pretext": "_static/pretext/js/lib"
    }
  },
  "startup": {
    pageReady() {
      return MathJax.startup.defaultPageReady().then(function () {
      console.log("in ready function");
      rsMathReady();
      }
    )}
  }
};
</script><script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"></script><script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/input/asciimath.js" charset="UTF-8"></script><script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/input/tex/extensions/extpfeil.js" charset="UTF-8"></script><script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/input/tex/extensions/amscd.js" charset="UTF-8"></script><script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/input/tex/extensions/color.js" charset="UTF-8"></script><script src="_static/pretext/js/lib/mathjaxknowl3.js" charset="UTF-8"></script><meta xmlns:xlink="http://www.w3.org/1999/xlink" name="Keywords" content="Authored in PreTeXt">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta xmlns:xlink="http://www.w3.org/1999/xlink" property="og:type" content="book">
<meta xmlns:xlink="http://www.w3.org/1999/xlink" property="book:title" content="An Introduction to Proof via Inquiry-Based Learning">
<meta xmlns:xlink="http://www.w3.org/1999/xlink" property="book:author" content="Dana C. Ernst, PhD">
<script src="_static/pretext/js/lib/jquery.min.js"></script><script src="_static/pretext/js/lib/jquery.sticky.js"></script><script src="_static/pretext/js/lib/jquery.espy.min.js"></script><script src="_static/pretext/js/pretext.js"></script><script src="_static/pretext/js/pretext_add_on.js?x=1"></script><script src="_static/pretext/js/user_preferences.js"></script><!--** eBookCongig is necessary to configure interactive       **-->
<!--** Runestone components to run locally in reader's browser **-->
<!--** No external communication:                              **-->
<!--**     log level is 0, Runestone Services are disabled     **-->
<script type="text/javascript">
eBookConfig = {};
eBookConfig.useRunestoneServices = false;
eBookConfig.host = 'http://127.0.0.1:8000';
eBookConfig.course = 'PTX_Course_Title_Here';
eBookConfig.basecourse = 'PTX_Base_Course';
eBookConfig.isLoggedIn = false;
eBookConfig.email = '';
eBookConfig.isInstructor = false;
eBookConfig.logLevel = 0;
eBookConfig.username = '';
eBookConfig.readings = null;
eBookConfig.activities = null;
eBookConfig.downloadsEnabled = false;
eBookConfig.allow_pairs = false;
eBookConfig.enableScratchAC = false;
eBookConfig.build_info = "";
eBookConfig.python3 = null;
eBookConfig.runestone_version = '7.6.1';
eBookConfig.jobehost = '';
eBookConfig.proxyuri_runs = '';
eBookConfig.proxyuri_files = '';
eBookConfig.enable_chatcodes =  false;
</script>
<!--*** Runestone Services ***-->
<script src="_static/prefix-runtime.c7804631fa963734.bundle.js"></script><script src="_static/prefix-723.3e6434f80549315a.bundle.js"></script><script src="_static/prefix-runestone.f7a03b209751032d.bundle.js"></script><link rel="stylesheet" type="text/css" href="_static/prefix-723.3bccd435914aa0ff.css">
<link rel="stylesheet" type="text/css" href="_static/prefix-runestone.541c9106f2c605b9.css">
<script xmlns:xlink="http://www.w3.org/1999/xlink" src="_static/pretext/js/lti_iframe_resizer.js"></script><script src="https://cdnjs.cloudflare.com/ajax/libs/lunr.js/2.3.9/lunr.min.js" integrity="sha512-4xUl/d6D6THrAnXAwGajXkoWaeMNwEKK4iNfq5DotEbLPAfk6FSxSP3ydNxqDgCw1c/0Z1Jg6L8h2j+++9BZmg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script><script src="lunr-pretext-search-index.js" async=""></script><script src="_static/pretext/js/pretext_search.js"></script><script src="_static/pretext/js/lib/knowl.js"></script><!--knowl.js code controls Sage Cells within knowls--><script>sagecellEvalName='Evaluate (Sage)';
</script>
<style type="text/css">.CtxtMenu_InfoClose {  top:.2em; right:.2em;}
.CtxtMenu_InfoContent {  overflow:auto; text-align:left; font-size:80%;  padding:.4em .6em; border:1px inset; margin:1em 0px;  max-height:20em; max-width:30em; background-color:#EEEEEE;  white-space:normal;}
.CtxtMenu_Info.CtxtMenu_MousePost {outline:none;}
.CtxtMenu_Info {  position:fixed; left:50%; width:auto; text-align:center;  border:3px outset; padding:1em 2em; background-color:#DDDDDD;  color:black;  cursor:default; font-family:message-box; font-size:120%;  font-style:normal; text-indent:0; text-transform:none;  line-height:normal; letter-spacing:normal; word-spacing:normal;  word-wrap:normal; white-space:nowrap; float:none; z-index:201;  border-radius: 15px;                     /* Opera 10.5 and IE9 */  -webkit-border-radius:15px;               /* Safari and Chrome */  -moz-border-radius:15px;                  /* Firefox */  -khtml-border-radius:15px;                /* Konqueror */  box-shadow:0px 10px 20px #808080;         /* Opera 10.5 and IE9 */  -webkit-box-shadow:0px 10px 20px #808080; /* Safari 3 & Chrome */  -moz-box-shadow:0px 10px 20px #808080;    /* Forefox 3.5 */  -khtml-box-shadow:0px 10px 20px #808080;  /* Konqueror */  filter:progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color="gray", Positive="true"); /* IE */}
</style><style type="text/css">.CtxtMenu_MenuClose {  position:absolute;  cursor:pointer;  display:inline-block;  border:2px solid #AAA;  border-radius:18px;  -webkit-border-radius: 18px;             /* Safari and Chrome */  -moz-border-radius: 18px;                /* Firefox */  -khtml-border-radius: 18px;              /* Konqueror */  font-family: "Courier New", Courier;  font-size:24px;  color:#F0F0F0}
.CtxtMenu_MenuClose span {  display:block; background-color:#AAA; border:1.5px solid;  border-radius:18px;  -webkit-border-radius: 18px;             /* Safari and Chrome */  -moz-border-radius: 18px;                /* Firefox */  -khtml-border-radius: 18px;              /* Konqueror */  line-height:0;  padding:8px 0 6px     /* may need to be browser-specific */}
.CtxtMenu_MenuClose:hover {  color:white!important;  border:2px solid #CCC!important}
.CtxtMenu_MenuClose:hover span {  background-color:#CCC!important}
.CtxtMenu_MenuClose:hover:focus {  outline:none}
</style><style type="text/css">.CtxtMenu_Menu {  position:absolute;  background-color:white;  color:black;  width:auto; padding:5px 0px;  border:1px solid #CCCCCC; margin:0; cursor:default;  font: menu; text-align:left; text-indent:0; text-transform:none;  line-height:normal; letter-spacing:normal; word-spacing:normal;  word-wrap:normal; white-space:nowrap; float:none; z-index:201;  border-radius: 5px;                     /* Opera 10.5 and IE9 */  -webkit-border-radius: 5px;             /* Safari and Chrome */  -moz-border-radius: 5px;                /* Firefox */  -khtml-border-radius: 5px;              /* Konqueror */  box-shadow:0px 10px 20px #808080;         /* Opera 10.5 and IE9 */  -webkit-box-shadow:0px 10px 20px #808080; /* Safari 3 & Chrome */  -moz-box-shadow:0px 10px 20px #808080;    /* Forefox 3.5 */  -khtml-box-shadow:0px 10px 20px #808080;  /* Konqueror */}
.CtxtMenu_MenuItem {  padding: 1px 2em;  background:transparent;}
.CtxtMenu_MenuArrow {  position:absolute; right:.5em; padding-top:.25em; color:#666666;  font-family: null; font-size: .75em}
.CtxtMenu_MenuActive .CtxtMenu_MenuArrow {color:white}
.CtxtMenu_MenuArrow.CtxtMenu_RTL {left:.5em; right:auto}
.CtxtMenu_MenuCheck {  position:absolute; left:.7em;  font-family: null}
.CtxtMenu_MenuCheck.CtxtMenu_RTL { right:.7em; left:auto }
.CtxtMenu_MenuRadioCheck {  position:absolute; left: .7em;}
.CtxtMenu_MenuRadioCheck.CtxtMenu_RTL {  right: .7em; left:auto}
.CtxtMenu_MenuInputBox {  padding-left: 1em; right:.5em; color:#666666;  font-family: null;}
.CtxtMenu_MenuInputBox.CtxtMenu_RTL {  left: .1em;}
.CtxtMenu_MenuComboBox {  left:.1em; padding-bottom:.5em;}
.CtxtMenu_MenuSlider {  left: .1em;}
.CtxtMenu_SliderValue {  position:absolute; right:.1em; padding-top:.25em; color:#333333;  font-size: .75em}
.CtxtMenu_SliderBar {  outline: none; background: #d3d3d3}
.CtxtMenu_MenuLabel {  padding: 1px 2em 3px 1.33em;  font-style:italic}
.CtxtMenu_MenuRule {  border-top: 1px solid #DDDDDD;  margin: 4px 3px;}
.CtxtMenu_MenuDisabled {  color:GrayText}
.CtxtMenu_MenuActive {  background-color: #606872;  color: white;}
.CtxtMenu_MenuDisabled:focus {  background-color: #E8E8E8}
.CtxtMenu_MenuLabel:focus {  background-color: #E8E8E8}
.CtxtMenu_ContextMenu:focus {  outline:none}
.CtxtMenu_ContextMenu .CtxtMenu_MenuItem:focus {  outline:none}
.CtxtMenu_SelectionMenu {  position:relative; float:left;  border-bottom: none; -webkit-box-shadow:none; -webkit-border-radius:0px; }
.CtxtMenu_SelectionItem {  padding-right: 1em;}
.CtxtMenu_Selection {  right: 40%; width:50%; }
.CtxtMenu_SelectionBox {  padding: 0em; max-height:20em; max-width: none;  background-color:#FFFFFF;}
.CtxtMenu_SelectionDivider {  clear: both; border-top: 2px solid #000000;}
.CtxtMenu_Menu .CtxtMenu_MenuClose {  top:-10px; left:-10px}
</style><style id="MJX-CHTML-styles">
mjx-container[jax="CHTML"] {
  line-height: 0;
}

mjx-container [space="1"] {
  margin-left: .111em;
}

mjx-container [space="2"] {
  margin-left: .167em;
}

mjx-container [space="3"] {
  margin-left: .222em;
}

mjx-container [space="4"] {
  margin-left: .278em;
}

mjx-container [space="5"] {
  margin-left: .333em;
}

mjx-container [rspace="1"] {
  margin-right: .111em;
}

mjx-container [rspace="2"] {
  margin-right: .167em;
}

mjx-container [rspace="3"] {
  margin-right: .222em;
}

mjx-container [rspace="4"] {
  margin-right: .278em;
}

mjx-container [rspace="5"] {
  margin-right: .333em;
}

mjx-container [size="s"] {
  font-size: 70.7%;
}

mjx-container [size="ss"] {
  font-size: 50%;
}

mjx-container [size="Tn"] {
  font-size: 60%;
}

mjx-container [size="sm"] {
  font-size: 85%;
}

mjx-container [size="lg"] {
  font-size: 120%;
}

mjx-container [size="Lg"] {
  font-size: 144%;
}

mjx-container [size="LG"] {
  font-size: 173%;
}

mjx-container [size="hg"] {
  font-size: 207%;
}

mjx-container [size="HG"] {
  font-size: 249%;
}

mjx-container [width="full"] {
  width: 100%;
}

mjx-box {
  display: inline-block;
}

mjx-block {
  display: block;
}

mjx-itable {
  display: inline-table;
}

mjx-row {
  display: table-row;
}

mjx-row > * {
  display: table-cell;
}

mjx-mtext {
  display: inline-block;
  text-align: left;
}

mjx-mstyle {
  display: inline-block;
}

mjx-merror {
  display: inline-block;
  color: red;
  background-color: yellow;
}

mjx-mphantom {
  visibility: hidden;
}

_::-webkit-full-page-media, _:future, :root mjx-container {
  will-change: opacity;
}

mjx-assistive-mml {
  position: absolute !important;
  top: 0px;
  left: 0px;
  clip: rect(1px, 1px, 1px, 1px);
  padding: 1px 0px 0px 0px !important;
  border: 0px !important;
  display: block !important;
  width: auto !important;
  overflow: hidden !important;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

mjx-assistive-mml[display="block"] {
  width: 100% !important;
}

mjx-math {
  display: inline-block;
  text-align: left;
  line-height: 0;
  text-indent: 0;
  font-style: normal;
  font-weight: normal;
  font-size: 100%;
  font-size-adjust: none;
  letter-spacing: normal;
  border-collapse: collapse;
  word-wrap: normal;
  word-spacing: normal;
  white-space: nowrap;
  direction: ltr;
  padding: 1px 0;
}

mjx-container[jax="CHTML"][display="true"] {
  display: block;
  text-align: center;
  margin: 1em 0;
}

mjx-container[jax="CHTML"][display="true"][width="full"] {
  display: flex;
}

mjx-container[jax="CHTML"][display="true"] mjx-math {
  padding: 0;
}

mjx-container[jax="CHTML"][justify="left"] {
  text-align: left;
}

mjx-container[jax="CHTML"][justify="right"] {
  text-align: right;
}

mjx-msqrt {
  display: inline-block;
  text-align: left;
}

mjx-root {
  display: inline-block;
  white-space: nowrap;
}

mjx-surd {
  display: inline-block;
  vertical-align: top;
}

mjx-sqrt {
  display: inline-block;
  padding-top: .07em;
}

mjx-sqrt > mjx-box {
  border-top: .07em solid;
}

mjx-sqrt.mjx-tall > mjx-box {
  padding-left: .3em;
  margin-left: -.3em;
}

mjx-mo {
  display: inline-block;
  text-align: left;
}

mjx-stretchy-h {
  display: inline-table;
  width: 100%;
}

mjx-stretchy-h > * {
  display: table-cell;
  width: 0;
}

mjx-stretchy-h > * > mjx-c {
  display: inline-block;
  transform: scalex(1.0000001);
}

mjx-stretchy-h > * > mjx-c::before {
  display: inline-block;
  width: initial;
}

mjx-stretchy-h > mjx-ext {
  /* IE */ overflow: hidden;
  /* others */ overflow: clip visible;
  width: 100%;
}

mjx-stretchy-h > mjx-ext > mjx-c::before {
  transform: scalex(500);
}

mjx-stretchy-h > mjx-ext > mjx-c {
  width: 0;
}

mjx-stretchy-h > mjx-beg > mjx-c {
  margin-right: -.1em;
}

mjx-stretchy-h > mjx-end > mjx-c {
  margin-left: -.1em;
}

mjx-stretchy-v {
  display: inline-block;
}

mjx-stretchy-v > * {
  display: block;
}

mjx-stretchy-v > mjx-beg {
  height: 0;
}

mjx-stretchy-v > mjx-end > mjx-c {
  display: block;
}

mjx-stretchy-v > * > mjx-c {
  transform: scaley(1.0000001);
  transform-origin: left center;
  overflow: hidden;
}

mjx-stretchy-v > mjx-ext {
  display: block;
  height: 100%;
  box-sizing: border-box;
  border: 0px solid transparent;
  /* IE */ overflow: hidden;
  /* others */ overflow: visible clip;
}

mjx-stretchy-v > mjx-ext > mjx-c::before {
  width: initial;
  box-sizing: border-box;
}

mjx-stretchy-v > mjx-ext > mjx-c {
  transform: scaleY(500) translateY(.075em);
  overflow: visible;
}

mjx-mark {
  display: inline-block;
  height: 0px;
}

mjx-c {
  display: inline-block;
}

mjx-utext {
  display: inline-block;
  padding: .75em 0 .2em 0;
}

mjx-mn {
  display: inline-block;
  text-align: left;
}

mjx-TeXAtom {
  display: inline-block;
  text-align: left;
}

mjx-mi {
  display: inline-block;
  text-align: left;
}

mjx-msup {
  display: inline-block;
  text-align: left;
}

mjx-mfrac {
  display: inline-block;
  text-align: left;
}

mjx-frac {
  display: inline-block;
  vertical-align: 0.17em;
  padding: 0 .22em;
}

mjx-frac[type="d"] {
  vertical-align: .04em;
}

mjx-frac[delims] {
  padding: 0 .1em;
}

mjx-frac[atop] {
  padding: 0 .12em;
}

mjx-frac[atop][delims] {
  padding: 0;
}

mjx-dtable {
  display: inline-table;
  width: 100%;
}

mjx-dtable > * {
  font-size: 2000%;
}

mjx-dbox {
  display: block;
  font-size: 5%;
}

mjx-num {
  display: block;
  text-align: center;
}

mjx-den {
  display: block;
  text-align: center;
}

mjx-mfrac[bevelled] > mjx-num {
  display: inline-block;
}

mjx-mfrac[bevelled] > mjx-den {
  display: inline-block;
}

mjx-den[align="right"], mjx-num[align="right"] {
  text-align: right;
}

mjx-den[align="left"], mjx-num[align="left"] {
  text-align: left;
}

mjx-nstrut {
  display: inline-block;
  height: .054em;
  width: 0;
  vertical-align: -.054em;
}

mjx-nstrut[type="d"] {
  height: .217em;
  vertical-align: -.217em;
}

mjx-dstrut {
  display: inline-block;
  height: .505em;
  width: 0;
}

mjx-dstrut[type="d"] {
  height: .726em;
}

mjx-line {
  display: block;
  box-sizing: border-box;
  min-height: 1px;
  height: .06em;
  border-top: .06em solid;
  margin: .06em -.1em;
  overflow: hidden;
}

mjx-line[type="d"] {
  margin: .18em -.1em;
}

mjx-c::before {
  display: block;
  width: 0;
}

.MJX-TEX {
  font-family: MJXZERO, MJXTEX;
}

.TEX-B {
  font-family: MJXZERO, MJXTEX-B;
}

.TEX-I {
  font-family: MJXZERO, MJXTEX-I;
}

.TEX-MI {
  font-family: MJXZERO, MJXTEX-MI;
}

.TEX-BI {
  font-family: MJXZERO, MJXTEX-BI;
}

.TEX-S1 {
  font-family: MJXZERO, MJXTEX-S1;
}

.TEX-S2 {
  font-family: MJXZERO, MJXTEX-S2;
}

.TEX-S3 {
  font-family: MJXZERO, MJXTEX-S3;
}

.TEX-S4 {
  font-family: MJXZERO, MJXTEX-S4;
}

.TEX-A {
  font-family: MJXZERO, MJXTEX-A;
}

.TEX-C {
  font-family: MJXZERO, MJXTEX-C;
}

.TEX-CB {
  font-family: MJXZERO, MJXTEX-CB;
}

.TEX-FR {
  font-family: MJXZERO, MJXTEX-FR;
}

.TEX-FRB {
  font-family: MJXZERO, MJXTEX-FRB;
}

.TEX-SS {
  font-family: MJXZERO, MJXTEX-SS;
}

.TEX-SSB {
  font-family: MJXZERO, MJXTEX-SSB;
}

.TEX-SSI {
  font-family: MJXZERO, MJXTEX-SSI;
}

.TEX-SC {
  font-family: MJXZERO, MJXTEX-SC;
}

.TEX-T {
  font-family: MJXZERO, MJXTEX-T;
}

.TEX-V {
  font-family: MJXZERO, MJXTEX-V;
}

.TEX-VB {
  font-family: MJXZERO, MJXTEX-VB;
}

mjx-stretchy-v mjx-c, mjx-stretchy-h mjx-c {
  font-family: MJXZERO, MJXTEX-S1, MJXTEX-S4, MJXTEX, MJXTEX-A ! important;
}

@font-face /* 0 */ {
  font-family: MJXZERO;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Zero.woff") format("woff");
}

@font-face /* 1 */ {
  font-family: MJXTEX;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Main-Regular.woff") format("woff");
}

@font-face /* 2 */ {
  font-family: MJXTEX-B;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Main-Bold.woff") format("woff");
}

@font-face /* 3 */ {
  font-family: MJXTEX-I;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Math-Italic.woff") format("woff");
}

@font-face /* 4 */ {
  font-family: MJXTEX-MI;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Main-Italic.woff") format("woff");
}

@font-face /* 5 */ {
  font-family: MJXTEX-BI;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Math-BoldItalic.woff") format("woff");
}

@font-face /* 6 */ {
  font-family: MJXTEX-S1;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size1-Regular.woff") format("woff");
}

@font-face /* 7 */ {
  font-family: MJXTEX-S2;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size2-Regular.woff") format("woff");
}

@font-face /* 8 */ {
  font-family: MJXTEX-S3;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size3-Regular.woff") format("woff");
}

@font-face /* 9 */ {
  font-family: MJXTEX-S4;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Size4-Regular.woff") format("woff");
}

@font-face /* 10 */ {
  font-family: MJXTEX-A;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_AMS-Regular.woff") format("woff");
}

@font-face /* 11 */ {
  font-family: MJXTEX-C;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Calligraphic-Regular.woff") format("woff");
}

@font-face /* 12 */ {
  font-family: MJXTEX-CB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Calligraphic-Bold.woff") format("woff");
}

@font-face /* 13 */ {
  font-family: MJXTEX-FR;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Fraktur-Regular.woff") format("woff");
}

@font-face /* 14 */ {
  font-family: MJXTEX-FRB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Fraktur-Bold.woff") format("woff");
}

@font-face /* 15 */ {
  font-family: MJXTEX-SS;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_SansSerif-Regular.woff") format("woff");
}

@font-face /* 16 */ {
  font-family: MJXTEX-SSB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_SansSerif-Bold.woff") format("woff");
}

@font-face /* 17 */ {
  font-family: MJXTEX-SSI;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_SansSerif-Italic.woff") format("woff");
}

@font-face /* 18 */ {
  font-family: MJXTEX-SC;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Script-Regular.woff") format("woff");
}

@font-face /* 19 */ {
  font-family: MJXTEX-T;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Typewriter-Regular.woff") format("woff");
}

@font-face /* 20 */ {
  font-family: MJXTEX-V;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Vector-Regular.woff") format("woff");
}

@font-face /* 21 */ {
  font-family: MJXTEX-VB;
  src: url("https://cdn.jsdelivr.net/npm/mathjax@3/es5/output/chtml/fonts/woff-v2/MathJax_Vector-Bold.woff") format("woff");
}

mjx-c.mjx-c221A::before {
  padding: 0.8em 0.853em 0.2em 0;
  content: "\221A";
}

mjx-c.mjx-c32::before {
  padding: 0.666em 0.5em 0 0;
  content: "2";
}

mjx-c.mjx-c2124.TEX-A::before {
  padding: 0.683em 0.667em 0 0;
  content: "Z";
}

mjx-c.mjx-c3A::before {
  padding: 0.43em 0.278em 0 0;
  content: ":";
}

mjx-c.mjx-c3D::before {
  padding: 0.583em 0.778em 0.082em 0;
  content: "=";
}

mjx-c.mjx-c7B::before {
  padding: 0.75em 0.5em 0.25em 0;
  content: "{";
}

mjx-c.mjx-c2026::before {
  padding: 0.12em 1.172em 0 0;
  content: "\2026";
}

mjx-c.mjx-c2C::before {
  padding: 0.121em 0.278em 0.194em 0;
  content: ",";
}

mjx-c.mjx-c2212::before {
  padding: 0.583em 0.778em 0.082em 0;
  content: "\2212";
}

mjx-c.mjx-c33::before {
  padding: 0.665em 0.5em 0.022em 0;
  content: "3";
}

mjx-c.mjx-c31::before {
  padding: 0.666em 0.5em 0 0;
  content: "1";
}

mjx-c.mjx-c30::before {
  padding: 0.666em 0.5em 0.022em 0;
  content: "0";
}

mjx-c.mjx-c7D::before {
  padding: 0.75em 0.5em 0.25em 0;
  content: "}";
}

mjx-c.mjx-c2115.TEX-A::before {
  padding: 0.683em 0.722em 0.02em 0;
  content: "N";
}

mjx-c.mjx-c211D.TEX-A::before {
  padding: 0.683em 0.722em 0 0;
  content: "R";
}

mjx-c.mjx-c2208::before {
  padding: 0.54em 0.667em 0.04em 0;
  content: "\2208";
}

mjx-c.mjx-c1D45B.TEX-I::before {
  padding: 0.442em 0.6em 0.011em 0;
  content: "n";
}

mjx-c.mjx-c1D44E.TEX-I::before {
  padding: 0.441em 0.529em 0.01em 0;
  content: "a";
}

mjx-c.mjx-c1D434.TEX-I::before {
  padding: 0.716em 0.75em 0 0;
  content: "A";
}

mjx-c.mjx-c1D44F.TEX-I::before {
  padding: 0.694em 0.429em 0.011em 0;
  content: "b";
}

mjx-c.mjx-c1D458.TEX-I::before {
  padding: 0.694em 0.521em 0.011em 0;
  content: "k";
}

mjx-c.mjx-c2B::before {
  padding: 0.583em 0.778em 0.082em 0;
  content: "+";
}

mjx-c.mjx-c22C5::before {
  padding: 0.31em 0.278em 0 0;
  content: "\22C5";
}

mjx-c.mjx-c28::before {
  padding: 0.75em 0.389em 0.25em 0;
  content: "(";
}

mjx-c.mjx-c29::before {
  padding: 0.75em 0.389em 0.25em 0;
  content: ")";
}

mjx-c.mjx-c2F::before {
  padding: 0.75em 0.5em 0.25em 0;
  content: "/";
}

mjx-c.mjx-c1D45A.TEX-I::before {
  padding: 0.442em 0.878em 0.011em 0;
  content: "m";
}

mjx-c.mjx-c7C::before {
  padding: 0.75em 0.278em 0.249em 0;
  content: "|";
}

mjx-c.mjx-c1D450.TEX-I::before {
  padding: 0.442em 0.433em 0.011em 0;
  content: "c";
}
</style></head>
<body class="pretext book ignore-math">
<a class="assistive" href="#ptx-content">Skip to main content</a><header id="ptx-masthead" class="ptx-masthead"><div class="ptx-banner"><div class="title-container">
<h1 class="heading"><a href="root-1-2.html"><span class="title">An Introduction to Proof via Inquiry-Based Learning</span></a></h1>
<p class="byline">Dana C. Ernst, PhD</p>
</div></div></header><nav xmlns:xlink="http://www.w3.org/1999/xlink" id="ptx-navbar" class="ptx-navbar navbar"><div class="ptx-navbar-contents">
<button class="toc-toggle button" title="Contents"><span class="icon material-symbols-outlined" aria-hidden="true"></span><span class="name">Contents</span></button><div class="searchbox">
<div class="searchwidget"><button id="searchbutton" class="searchbutton button" type="button" title="Search book"><span class="icon material-symbols-outlined" aria-hidden="true"></span><span class="name">Search Book</span></button></div>
<div id="searchresultsplaceholder" class="searchresultsplaceholder" style="display: none">
<div class="search-results-controls">
<input aria-label="Search term" id="ptxsearch" class="ptxsearch" type="text" name="terms" placeholder="Search term"><button title="Close search" id="closesearchresults" class="closesearchresults"><span class="material-symbols-outlined">close</span></button>
</div>
<h2 class="search-results-heading">Search Results: </h2>
<div id="searchempty" class="searchempty"><span>No results.</span></div>
<ol id="searchresults" class="searchresults"></ol>
</div>
<div class="searchresultsbackground" style="display: none;"></div></div>
<span class="nav-other-controls"><button id="light-dark-button" class="light-dark-button button" title="Dark Mode"><span class="icon material-symbols-outlined" aria-hidden="true">light_mode</span><span class="name">Light Mode</span></button></span><span class="treebuttons"><a class="previous-button button" href="chap_IntroToMath.html" title="Previous"><span class="icon material-symbols-outlined" aria-hidden="true"></span><span class="name">Prev</span></a><a class="up-button button" href="chap_IntroToMath.html" title="Up"><span class="icon material-symbols-outlined" aria-hidden="true"></span><span class="name">Up</span></a><a class="next-button button" href="sec_Intro_to_Logic.html" title="Next"><span class="name">Next</span><span class="icon material-symbols-outlined" aria-hidden="true"></span></a></span>
</div></nav><div xmlns:xlink="http://www.w3.org/1999/xlink" id="latex-macros" class="hidden-content process-math" style="display:none"><span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="0" style="font-size: 110.9%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"></math></mjx-assistive-mml></mjx-container></span></div>
<div class="ptx-page">

<main class="ptx-main"><div id="ptx-content" class="ptx-content"><section xmlns:xlink="http://www.w3.org/1999/xlink" class="section" id="sec_baby_number_theory"><h2 class="heading hide-type">
<span class="type">Section</span><span class="space"> </span><span class="codenumber">2.1</span><span class="space"> </span><span class="title">A Taste of Number Theory</span>
</h2>
<div class="para" id="sec_baby_number_theory-2">It is important to point out that we are diving in head first here. As we get started, we are going to rely on your intuition and previous experience with proofs. This is intentional. What you will likely encounter is a general sense of what a proof entails, but you may not be able to articulate the finer details that you do and do not comprehend. There are going to be some subtle issues that you will be confronted with and one of our goals will be to elucidate as many of them as possible. We need to calibrate and develop an intellectual need for structure. You are encouraged to just try your hand at writing proofs for the problems in this section without too much concern for whether you are “doing it the right way.” In <a href="sec_Intro_to_Logic.html" class="internal" title="Section 2.2: Introduction to Logic">Section&nbsp;2.2</a>, we will start over and begin to develop a formal foundation for the material in the remainder of the book. Once you have gained more experience and a better understanding of what a proof entails, you should consider returning to this section and reviewing your first attempts at writing proofs. In the meantime, see what you can do!<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-2" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para logical" id="sec_baby_number_theory-3">
<div class="para">In this section, we will introduce the basics of a branch of mathematics called <dfn class="terminology">number theory</dfn>, which is devoted to studying the properties of the integers. The integers is the set of numbers given by</div>
<div class="displaymath process-math">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" style="font-size: 118.7%; position: relative;" display="true" tabindex="0" ctxtmenu_counter="2"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-texatom texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3A"></mjx-c><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c7B"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2026"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="2"><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="2"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="2"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="2"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2026"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c7D"></mjx-c></mjx-mo></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow><mo>:=</mo><mo fence="false" stretchy="false">{</mo><mo>…</mo><mo>,</mo><mo>−</mo><mn>3</mn><mo>,</mo><mo>−</mo><mn>2</mn><mo>,</mo><mo>−</mo><mn>1</mn><mo>,</mo><mn>0</mn><mo>,</mo><mn>1</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mo>…</mo><mo fence="false" stretchy="false">}</mo></mrow><mtext>.</mtext></math></mjx-assistive-mml></mjx-container>
</div>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-3" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para logical" id="sec_baby_number_theory-4">
<div class="para">The collection of positive integers also have a special name. The set of <dfn class="terminology">natural numbers</dfn> is given by</div>
<div class="displaymath process-math">
<mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" display="true" tabindex="0" ctxtmenu_counter="3" style="font-size: 118.7%; position: relative;"><mjx-math display="true" class="MJX-TEX" aria-hidden="true" style="margin-left: 0px; margin-right: 0px;"><mjx-texatom texclass="ORD"><mjx-texatom texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2115 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3A"></mjx-c><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c7B"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="2"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="2"><mjx-c class="mjx-c33"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="2"><mjx-c class="mjx-c2026"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c7D"></mjx-c></mjx-mo></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="block"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow data-mjx-texclass="ORD"><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">N</mi></mrow><mo>:=</mo><mo fence="false" stretchy="false">{</mo><mn>1</mn><mo>,</mo><mn>2</mn><mo>,</mo><mn>3</mn><mo>,</mo><mo>…</mo><mo fence="false" stretchy="false">}</mo></mrow><mtext>.</mtext></math></mjx-assistive-mml></mjx-container>
</div>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-4" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para" id="sec_baby_number_theory-5">Some mathematicians (set theorists, in particular) include <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="4" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn></math></mjx-assistive-mml></mjx-container></span> in <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" style="font-size: 118.7%; position: relative;" tabindex="0" ctxtmenu_counter="5"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2115 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">N</mi></mrow><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> but this will not be our convention. If you look closely at the two sets we defined above, you will notice that we wrote <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="6" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c3A"></mjx-c><mjx-c class="mjx-c3D"></mjx-c></mjx-mo></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>:=</mo></mrow></math></mjx-assistive-mml></mjx-container></span> instead of <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="7" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;" space="4"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>=</mo><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> We use <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="8" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c3A"></mjx-c><mjx-c class="mjx-c3D"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>:=</mo></math></mjx-assistive-mml></mjx-container></span> to mean that the symbol or expression on the left is defined to be equal to the expression on the right. The symbol <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="9" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-texatom texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c211D TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">R</mi></mrow></mrow></math></mjx-assistive-mml></mjx-container></span> is used to denote the set of all <dfn class="terminology">real numbers</dfn>. We will not formally define the real numbers, but instead rely on your prior intuition and understanding.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-5" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para" id="sec_baby_number_theory-6">Because you are so familiar with many of the properties of the integers and real numbers, one of the issues that we will bump into is knowing which facts we can take for granted. As a general rule of thumb, you should attempt to use the definitions provided without relying too much on your prior knowledge. The order in which we develop things is important.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-6" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para" id="sec_baby_number_theory-7">It is common practice in mathematics to use the symbol <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="10" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mo>∈</mo></mrow></math></mjx-assistive-mml></mjx-container></span> as an abbreviation for the phrase “is an element of” or sometimes simply “in.” For example, the mathematical expression “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="11" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span>” means “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="12" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is an element of the integers.” However, some care should be taken in how this symbol is used. We will only use the symbol “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="13" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>∈</mo></math></mjx-assistive-mml></mjx-container></span>” in expressions of the form <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="14" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mi>a</mi><mo>∈</mo><mi>A</mi></mrow><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> where <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="15" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>A</mi></math></mjx-assistive-mml></mjx-container></span> is a set and <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="16" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> is an element of <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="17" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>A</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> We will write expressions like <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="18" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mi>a</mi><mo>,</mo><mi>b</mi><mo>∈</mo><mi>A</mi></mrow></math></mjx-assistive-mml></mjx-container></span> as shorthand for “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="19" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>∈</mo><mi>A</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="20" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi><mo>∈</mo><mi>A</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>” We should avoid writing phrases such as “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="21" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> is a number <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="22" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D434 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>∈</mo><mi>A</mi></math></mjx-assistive-mml></mjx-container></span>” and “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="23" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>∈</mo></math></mjx-assistive-mml></mjx-container></span> integers”.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-7" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para" id="sec_baby_number_theory-8">We will now encounter our very first definition. In mathematics, a <dfn class="terminology">definition</dfn> is a precise and unambiguous description of the meaning of a mathematical term. It characterizes the meaning of a word by giving all the properties and only those properties that must be true. Check out <a href="appendix_fancy_math_terms.html" class="internal" title="Appendix B: Fancy Mathematical Terms">Appendix&nbsp;B</a> for a list of other mathematical terms that we should be familiar with.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-8" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="definition definition-like" id="sec_baby_number_theory-9"><h3 class="heading">
<span class="type">Definition</span><span class="space"> </span><span class="codenumber">2.1</span><span class="period">.</span>
</h3>
<div class="para" id="sec_baby_number_theory-9-1-1">An integer <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="24" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is <dfn class="terminology">even</dfn> if <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="25" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>=</mo><mn>2</mn><mi>k</mi></math></mjx-assistive-mml></mjx-container></span> for some <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="26" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> An integer <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="27" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is <dfn class="terminology">odd</dfn> if <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="28" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>=</mo><mn>2</mn><mi>k</mi><mo>+</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> for some <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="29" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-9-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Definition 2.1"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-9" title="Copy permalink for Definition 2.1">🔗</a></div></article><div class="para" id="sec_baby_number_theory-10">Notice that we framed the definition of “even” in terms of multiplication as opposed to division. When tackling theorems and problems involving even or odd, be sure to make use of our formal definitions and not some of the well-known divisibility properties. For now, you should avoid arguments that involve statements like, “even numbers have no remainder when divided by two” or “the last digit of an even number is 0, 2, 4, 6, or 8.” Also notice that the notions of even and odd apply to zero and negative numbers. In particular, zero is even since <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="30" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c22C5"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c30"></mjx-c></mjx-mn><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn><mo>=</mo><mn>2</mn><mo>⋅</mo><mn>0</mn><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> where it is worth emphasizing that the occurrence of <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="31" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mn class="mjx-n"><mjx-c class="mjx-c30"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn></math></mjx-assistive-mml></mjx-container></span> on the righthand side of the equation is an integer. As another example, we see that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="32" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> is odd since <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="33" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1</mn><mo>=</mo><mn>2</mn><mo stretchy="false">(</mo><mo>−</mo><mn>1</mn><mo stretchy="false">)</mo><mo>+</mo><mn>1</mn><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> Despite the fact that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="34" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="4"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c28"></mjx-c></mjx-mo><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn><mjx-mo class="mjx-n"><mjx-c class="mjx-c29"></mjx-c></mjx-mo><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1</mn><mo>=</mo><mn>2</mn><mo stretchy="false">(</mo><mo>−</mo><mn>1</mn><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn><mo stretchy="false">)</mo><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> this does not imply that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="35" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1</mn></math></mjx-assistive-mml></mjx-container></span> is also even since <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="36" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mn>1</mn><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mn>2</mn></math></mjx-assistive-mml></mjx-container></span> is not an integer. For the remainder of this section, you may assume that every integer is either even or odd but never both.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-10" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para" id="sec_baby_number_theory-11">Our first theorem concerning the integers is stated below. A <dfn class="terminology">theorem</dfn> is a mathematical statement that is proved using rigorous mathematical reasoning. A synonym for theorem is <dfn class="terminology">proposition</dfn>. However, in formal mathematics research papers, the term “theorem” is typically reserved for the most important results while “proposition” is used for other interesting but generally less important results. To complicate matters, the term “proposition” has a second yet related meaning, which we will encounter in <a href="sec_Intro_to_Logic.html#def_proposition" class="xref knowl__link" data-knowl="./knowl/xref/def_proposition.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Definition 2.16" data-knowl-uid="0" role="button" data-base-title="Definition 2.16" aria-label="Reveal Definition 2.16">Definition&nbsp;2.16</a>. In this book, we will utilize the theorem designation for true mathematical statements. In contrast, as in <a href="sec_Intro_to_Logic.html#def_proposition" class="xref knowl__link" data-knowl="./knowl/xref/def_proposition.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Definition 2.16" data-knowl-uid="1" role="button" data-base-title="Definition 2.16" aria-label="Reveal Definition 2.16">Definition&nbsp;2.16</a>, we will use proposition to describe a sentence that is either true or false (but never both). See <a href="appendix_fancy_math_terms.html" class="internal" title="Appendix B: Fancy Mathematical Terms">Appendix&nbsp;B</a> for a list of fancy mathematical terms that includes theorem and proposition. As with most theorems in this book, your task is to try your hand at proving the following theorem. Give it a try.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-11" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="theorem theorem-like" id="thm_n_even_implies_n_2_even"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.2</span><span class="period">.</span>
</h3>
<div class="para" id="thm_n_even_implies_n_2_even-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="37" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is an even integer, then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="38" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>n</mi><mn>2</mn></msup></math></mjx-assistive-mml></mjx-container></span> is an even integer.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_n_even_implies_n_2_even-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.2"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_n_even_implies_n_2_even" title="Copy permalink for Theorem 2.2">🔗</a></div></article><div class="para" id="sec_baby_number_theory-13">One crux in proving the next theorem involves figuring out how to describe an arbitrary pair of consecutive integers.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-13" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="theorem theorem-like" id="thm_two_consecutive_ints"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.3</span><span class="period">.</span>
</h3>
<div class="para" id="thm_two_consecutive_ints-1-1">The sum of two consecutive integers is odd.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_two_consecutive_ints-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.3"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_two_consecutive_ints" title="Copy permalink for Theorem 2.3">🔗</a></div></article><div class="para" id="sec_baby_number_theory-15">One skill we will want to develop is determining whether a given mathematical statement is true or false. In order to verify that a mathematical statement is false, we should provide a specific example where the statement fails. Such an example is called a <dfn class="terminology">counterexample</dfn>. Notice that it is sufficient to provide a single example to verify that a general statement is not true. On the other hand, if we want to prove that a general mathematical statement is true, it is usually not sufficient to provide just a single example, or even a hundred examples. Such examples are just evidence that the statement is true.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-15" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="problem example-like" id="sec_baby_number_theory-16"><h3 class="heading">
<span class="type">Problem</span><span class="space"> </span><span class="codenumber">2.4</span><span class="period">.</span>
</h3>
<div class="para logical" id="sec_baby_number_theory-16-1-1">
<div class="para">Determine whether each of the following statements is true or false. If a statement is true, prove it. If a statement is false, provide a counterexample.</div>
<ol class="lower-alpha ol-marker-1" id="sec_baby_number_theory-16-1-1-1">
<li id="sec_baby_number_theory-16-1-1-1-1"><div class="para" id="sec_baby_number_theory-16-1-1-1-1-1">The product of an odd integer and an even integer is odd.</div></li>
<li id="sec_baby_number_theory-16-1-1-1-2"><div class="para" id="sec_baby_number_theory-16-1-1-1-2-1">The product of an odd integer and an odd integer is odd.</div></li>
<li id="sec_baby_number_theory-16-1-1-1-3"><div class="para" id="sec_baby_number_theory-16-1-1-1-3-1">The product of an even integer and an even integer is even.</div></li>
<li id="sec_baby_number_theory-16-1-1-1-4"><div class="para" id="sec_baby_number_theory-16-1-1-1-4-1">The sum of an even integer and an odd integer is odd.</div></li>
</ol>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-16-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Problem 2.4"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-16" title="Copy permalink for Problem 2.4">🔗</a></div></article><div class="para" id="sec_baby_number_theory-17">For the statements that were true in the previous problem, you may cite them later in a future proof as if they are theorems.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-17" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="definition definition-like" id="def_divides"><h3 class="heading">
<span class="type">Definition</span><span class="space"> </span><span class="codenumber">2.5</span><span class="period">.</span>
</h3>
<div class="para" id="def_divides-1-1">Given <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="39" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>,</mo><mi>m</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> we say that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="40" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> <dfn class="terminology">divides</dfn> <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="41" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> written <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="42" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-texatom texclass="ORD"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow data-mjx-texclass="ORD"><mi>n</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>m</mi></mrow><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> if there exists <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="43" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>k</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span> such that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="44" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c3D"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="4"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D458 TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi><mo>=</mo><mi>n</mi><mi>k</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="45" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>m</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> we may also say that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="46" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></mjx-assistive-mml></mjx-container></span> is <dfn class="terminology">divisible</dfn> by <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="47" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> or that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="48" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is a <dfn class="terminology">factor</dfn> of <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="49" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#def_divides-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Definition 2.5"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#def_divides" title="Copy permalink for Definition 2.5">🔗</a></div></article><article class="problem example-like" id="sec_baby_number_theory-19"><h3 class="heading">
<span class="type">Problem</span><span class="space"> </span><span class="codenumber">2.6</span><span class="period">.</span>
</h3>
<div class="para logical" id="sec_baby_number_theory-19-1-1">
<div class="para">For <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="50" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>,</mo><mi>m</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> how are the following mathematical expressions similar and how are they different? In particular, is each one a sentence or simply a noun?</div>
<ol class="lower-alpha ol-marker-1" id="sec_baby_number_theory-19-1-1-2">
<li id="sec_baby_number_theory-19-1-1-2-1"><div class="para" id="sec_baby_number_theory-19-1-1-2-1-1"><span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="51" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mstyle><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-mstyle></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mstyle displaystyle="true" scriptlevel="0"><mi>n</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>m</mi></mstyle></math></mjx-assistive-mml></mjx-container></span></div></li>
<li id="sec_baby_number_theory-19-1-1-2-2"><div class="para" id="sec_baby_number_theory-19-1-1-2-2-1"><span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="52" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mstyle><mjx-mstyle><mjx-mfrac><mjx-frac type="d"><mjx-num><mjx-nstrut type="d"></mjx-nstrut><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-num><mjx-dbox><mjx-dtable><mjx-line type="d"></mjx-line><mjx-row><mjx-den><mjx-dstrut type="d"></mjx-dstrut><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-den></mjx-row></mjx-dtable></mjx-dbox></mjx-frac></mjx-mfrac></mjx-mstyle></mjx-mstyle></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mstyle displaystyle="true" scriptlevel="0"><mstyle displaystyle="true" scriptlevel="0"><mfrac><mi>m</mi><mi>n</mi></mfrac></mstyle></mstyle></math></mjx-assistive-mml></mjx-container></span></div></li>
<li id="sec_baby_number_theory-19-1-1-2-3"><div class="para" id="sec_baby_number_theory-19-1-1-2-3-1"><span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="53" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mstyle><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2F"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-mstyle></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mstyle displaystyle="true" scriptlevel="0"><mi>m</mi><mrow data-mjx-texclass="ORD"><mo>/</mo></mrow><mi>n</mi></mstyle></math></mjx-assistive-mml></mjx-container></span></div></li>
</ol>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-19-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Problem 2.6"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-19" title="Copy permalink for Problem 2.6">🔗</a></div></article><div class="para" id="sec_baby_number_theory-20">In this section on number theory, we allow addition, subtraction, and multiplication of integers. In general, we avoid division since an integer divided by an integer may result in a number that is not an integer. The upshot is that we will avoid writing <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="54" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mfrac><mjx-frac><mjx-num><mjx-nstrut></mjx-nstrut><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-num><mjx-dbox><mjx-dtable><mjx-line></mjx-line><mjx-row><mjx-den><mjx-dstrut></mjx-dstrut><mjx-mi class="mjx-i" size="s"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-den></mjx-row></mjx-dtable></mjx-dbox></mjx-frac></mjx-mfrac><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mfrac><mi>m</mi><mi>n</mi></mfrac><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> When you feel the urge to divide, switch to an equivalent formulation using multiplication. This will make your life much easier when proving statements involving divisibility.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-20" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="theorem theorem-like" id="thm_sum_of_three_consecutive_integers"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.7</span><span class="period">.</span>
</h3>
<div class="para" id="thm_sum_of_three_consecutive_integers-1-1">The sum of any three consecutive integers is always divisible by three.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_sum_of_three_consecutive_integers-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.7"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_sum_of_three_consecutive_integers" title="Copy permalink for Theorem 2.7">🔗</a></div></article><article class="problem example-like" id="prob_divisibility_examples"><h3 class="heading">
<span class="type">Problem</span><span class="space"> </span><span class="codenumber">2.8</span><span class="period">.</span>
</h3>
<div class="para logical" id="prob_divisibility_examples-1-1">
<div class="para">Let <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="55" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>b</mi><mo>,</mo><mi>n</mi><mo>,</mo><mi>m</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> Determine whether each of the following statements is true or false. If a statement is true, prove it. If a statement is false, provide a counterexample.</div>
<ol class="lower-alpha ol-marker-1" id="prob_divisibility_examples-1-1-2">
<li id="prob_first_divisibility_example"><div class="para" id="prob_first_divisibility_example-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="56" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="57" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>m</mi><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
</div></li>
<li id="prob_divisibility_examples-1-1-2-2"><div class="para" id="prob_divisibility_examples-1-1-2-2-1">If 6 divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="58" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then 2 divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="59" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> and 3 divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="60" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
</div></li>
<li id="prob_divisibility_examples-1-1-2-3"><div class="para" id="prob_divisibility_examples-1-1-2-3-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="61" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mi>b</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="62" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="63" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="64" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="65" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="66" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
</div></li>
</ol>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#prob_divisibility_examples-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Problem 2.8"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#prob_divisibility_examples" title="Copy permalink for Problem 2.8">🔗</a></div></article><div class="para" id="sec_baby_number_theory-23">A theorem that follows almost immediately from another theorem is called a <dfn class="terminology">corollary</dfn>. See if you can prove the next result quickly using a previous result. Be sure to cite the result in your proof.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-23" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="corollary theorem-like" id="cor_a_divs_n_implies_a_divs_n_2"><h3 class="heading">
<span class="type">Corollary</span><span class="space"> </span><span class="codenumber">2.9</span><span class="period">.</span>
</h3>
<div class="para" id="cor_a_divs_n_implies_a_divs_n_2-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="67" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span> such that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="68" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="69" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="70" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="71" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>n</mi><mn>2</mn></msup><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#cor_a_divs_n_implies_a_divs_n_2-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Corollary 2.9"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#cor_a_divs_n_implies_a_divs_n_2" title="Copy permalink for Corollary 2.9">🔗</a></div></article><div class="para" id="sec_baby_number_theory-25">The next two theorems are likely familiar to you.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-25" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="theorem theorem-like" id="thm_divides_negative"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.10</span><span class="period">.</span>
</h3>
<div class="para" id="thm_divides_negative-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="72" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span> such that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="73" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="74" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="75" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="76" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_divides_negative-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.10"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_divides_negative" title="Copy permalink for Theorem 2.10">🔗</a></div></article><article class="theorem theorem-like" id="thm_divides_sum"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.11</span><span class="period">.</span>
</h3>
<div class="para" id="thm_divides_sum-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="77" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>n</mi><mo>,</mo><mi>m</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span> such that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="78" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="79" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="80" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="81" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="82" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="83" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi><mo>+</mo><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_divides_sum-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.11"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_divides_sum" title="Copy permalink for Theorem 2.11">🔗</a></div></article><div class="para" id="sec_baby_number_theory-28">Notice that we have been tinkering with statements of the form “If…, then…”. Statements of this form are called <dfn class="terminology">conditional propositions</dfn>, which we revisit in the next section. The phrase that occurs after “If” but before “then” is called the <dfn class="terminology">hypothesis</dfn> while the phrase that occurs after “then” is called the <dfn class="terminology">conclusion</dfn>. For example, in <a href="sec_baby_number_theory.html#prob_divisibility_examples" class="xref knowl__link" data-knowl="./knowl/xref/prob_divisibility_examples.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Problem 2.8" data-knowl-uid="2" role="button" data-base-title="Problem 2.8" aria-label="Reveal Problem 2.8">Problem&nbsp;2.8</a> <a href="sec_baby_number_theory.html#prob_first_divisibility_example" class="xref knowl__link" data-knowl="./knowl/xref/prob_first_divisibility_example.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Item a" data-knowl-uid="3" role="button" data-base-title="Item a" aria-label="Reveal Item a">Item&nbsp;a</a>, “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="84" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>n</mi></math></mjx-assistive-mml></mjx-container></span>” is the hypothesis while “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="85" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>m</mi><mi>n</mi></math></mjx-assistive-mml></mjx-container></span>” is the conclusion. Note that conditional propositions can also be written in the form “… if …”, where the conclusion is written before “if” and the hypothesis after. For example, we can rewrite <a href="sec_baby_number_theory.html#prob_divisibility_examples" class="xref knowl__link" data-knowl="./knowl/xref/prob_divisibility_examples.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Problem 2.8" data-knowl-uid="4" role="button" data-base-title="Problem 2.8" aria-label="Reveal Problem 2.8">Problem&nbsp;2.8</a> <a href="sec_baby_number_theory.html#prob_first_divisibility_example" class="xref knowl__link" data-knowl="./knowl/xref/prob_first_divisibility_example.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Item a" data-knowl-uid="5" role="button" data-base-title="Item a" aria-label="Reveal Item a">Item&nbsp;a</a> as “<span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="86" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>m</mi><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> if <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="87" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>n</mi></math></mjx-assistive-mml></mjx-container></span>”. While the order of the hypothesis and conclusion have been reversed in the sentence, their roles have not.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-28" title="Copy permalink for Paragraph">🔗</a></div></div>
<div class="para" id="sec_baby_number_theory-29">Whenever we encounter a conditional statement in mathematics, we want to get in the habit of asking ourselves what happens when we swap the roles of the hypothesis and the conclusion. The statement that results from reversing the roles of the hypothesis and conclusion in a conditional statement is called the <dfn class="terminology">converse</dfn> of the original statement. For example, the converse of <a href="sec_baby_number_theory.html#prob_divisibility_examples" class="xref knowl__link" data-knowl="./knowl/xref/prob_divisibility_examples.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Problem 2.8" data-knowl-uid="6" role="button" data-base-title="Problem 2.8" aria-label="Reveal Problem 2.8">Problem&nbsp;2.8</a> <a href="sec_baby_number_theory.html#prob_first_divisibility_example" class="xref knowl__link" data-knowl="./knowl/xref/prob_first_divisibility_example.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Item a" data-knowl-uid="7" role="button" data-base-title="Item a" aria-label="Reveal Item a">Item&nbsp;a</a> is “If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="88" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>m</mi><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="89" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-texatom texclass="ORD"><mjx-mo class="mjx-n"><mjx-c class="mjx-c7C"></mjx-c></mjx-mo></mjx-texatom><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mrow data-mjx-texclass="ORD"><mo stretchy="false">|</mo></mrow><mi>n</mi></math></mjx-assistive-mml></mjx-container></span>”, which happens to be false. The converse of <a href="sec_baby_number_theory.html#thm_n_even_implies_n_2_even" class="xref knowl__link" data-knowl="./knowl/xref/thm_n_even_implies_n_2_even.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Theorem 2.2" data-knowl-uid="8" role="button" data-base-title="Theorem 2.2" aria-label="Reveal Theorem 2.2">Theorem&nbsp;2.2</a> is “If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="90" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>n</mi><mn>2</mn></msup></math></mjx-assistive-mml></mjx-container></span> is an even integer, then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="91" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is an even integer”. While this statement is true it does <em class="emphasis">not</em> have the same meaning as <a href="sec_baby_number_theory.html#thm_n_even_implies_n_2_even" class="xref knowl__link" data-knowl="./knowl/xref/thm_n_even_implies_n_2_even.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Theorem 2.2" data-knowl-uid="9" role="button" data-base-title="Theorem 2.2" aria-label="Reveal Theorem 2.2">Theorem&nbsp;2.2</a>.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-29" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="problem example-like" id="sec_baby_number_theory-30"><h3 class="heading">
<span class="type">Problem</span><span class="space"> </span><span class="codenumber">2.12</span><span class="period">.</span>
</h3>
<div class="para logical" id="sec_baby_number_theory-30-1-1">
<div class="para">Determine whether the converse of each of <a href="sec_baby_number_theory.html#cor_a_divs_n_implies_a_divs_n_2" class="xref knowl__link" data-knowl="./knowl/xref/cor_a_divs_n_implies_a_divs_n_2.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Corollary 2.9" data-knowl-uid="10" role="button" data-base-title="Corollary 2.9" aria-label="Reveal Corollary 2.9">Corollary&nbsp;2.9</a>, <a href="sec_baby_number_theory.html#thm_divides_negative" class="xref knowl__link" data-knowl="./knowl/xref/thm_divides_negative.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Theorem 2.10" data-knowl-uid="11" role="button" data-base-title="Theorem 2.10" aria-label="Reveal Theorem 2.10">Theorem&nbsp;2.10</a>, and <a href="sec_baby_number_theory.html#thm_divides_sum" class="xref knowl__link" data-knowl="./knowl/xref/thm_divides_sum.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Theorem 2.11" data-knowl-uid="12" role="button" data-base-title="Theorem 2.11" aria-label="Reveal Theorem 2.11">Theorem&nbsp;2.11</a> is true. That is, for <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="92" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>n</mi><mo>,</mo><mi>m</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> determine whether each of the following statements is true or false. If a statement is true, prove it. If a statement is false, provide a counterexample.</div>
<ol class="lower-alpha ol-marker-1" id="sec_baby_number_theory-30-1-1-5">
<li id="sec_baby_number_theory-30-1-1-5-1"><div class="para" id="sec_baby_number_theory-30-1-1-5-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="93" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="94" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-mn class="mjx-n" size="s"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-script></mjx-msup><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>n</mi><mn>2</mn></msup><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="95" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="96" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> (Converse of <a href="sec_baby_number_theory.html#cor_a_divs_n_implies_a_divs_n_2" class="xref knowl__link" data-knowl="./knowl/xref/cor_a_divs_n_implies_a_divs_n_2.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Corollary 2.9" data-knowl-uid="13" role="button" data-base-title="Corollary 2.9" aria-label="Reveal Corollary 2.9">Corollary&nbsp;2.9</a>)</div></li>
<li id="sec_baby_number_theory-30-1-1-5-2"><div class="para" id="sec_baby_number_theory-30-1-1-5-2-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="97" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="98" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mo class="mjx-n"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mo>−</mo><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="99" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="100" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> (Converse of <a href="sec_baby_number_theory.html#thm_divides_negative" class="xref knowl__link" data-knowl="./knowl/xref/thm_divides_negative.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Theorem 2.10" data-knowl-uid="14" role="button" data-base-title="Theorem 2.10" aria-label="Reveal Theorem 2.10">Theorem&nbsp;2.10</a>)</div></li>
<li id="sec_baby_number_theory-30-1-1-5-3"><div class="para" id="sec_baby_number_theory-30-1-1-5-3-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="101" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="102" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2B"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi><mo>+</mo><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="103" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="104" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="105" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="106" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span> (Converse of <a href="sec_baby_number_theory.html#thm_divides_sum" class="xref knowl__link" data-knowl="./knowl/xref/thm_divides_sum.html" data-reveal-label="Reveal" data-close-label="Close" title="Reveal Theorem 2.11" data-knowl-uid="15" role="button" data-base-title="Theorem 2.11" aria-label="Reveal Theorem 2.11">Theorem&nbsp;2.11</a>)</div></li>
</ol>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-30-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Problem 2.12"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-30" title="Copy permalink for Problem 2.12">🔗</a></div></article><div class="para" id="sec_baby_number_theory-31">The next theorem is often referred to as the <dfn class="terminology">transitivity of division of integers</dfn>.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-31" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="theorem theorem-like" id="thm_transitivity_of_divides"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.13</span><span class="period">.</span>
</h3>
<div class="para" id="thm_transitivity_of_divides-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="107" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D450 TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>b</mi><mo>,</mo><mi>c</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span> such that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="108" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="109" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="110" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44F TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>b</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="111" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D450 TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>c</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="112" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="113" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D450 TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>c</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_transitivity_of_divides-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.13"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#thm_transitivity_of_divides" title="Copy permalink for Theorem 2.13">🔗</a></div></article><div class="para" id="sec_baby_number_theory-33">Once we have proved a few theorems, we should be on the look out to see if we can utilize any of our current results to prove new results. There is no point in reinventing the wheel if we do not have to.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-33" title="Copy permalink for Paragraph">🔗</a></div></div>
<article class="theorem theorem-like" id="sec_baby_number_theory-34"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.14</span><span class="period">.</span>
</h3>
<div class="para" id="sec_baby_number_theory-34-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="114" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n"><mjx-c class="mjx-c2C"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="2"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>,</mo><mi>n</mi><mo>,</mo><mi>m</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span> such that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="115" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="116" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi></math></mjx-assistive-mml></mjx-container></span> and <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="117" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="118" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">,</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mtext>,</mtext></math></mjx-assistive-mml></mjx-container></span> then <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="119" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D44E TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></mjx-assistive-mml></mjx-container></span> divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="120" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45A TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mi class="mjx-i" space="3"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>m</mi><mo>−</mo><mi>n</mi><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-34-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.14"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-34" title="Copy permalink for Theorem 2.14">🔗</a></div></article><article class="theorem theorem-like" id="sec_baby_number_theory-35"><h3 class="heading">
<span class="type">Theorem</span><span class="space"> </span><span class="codenumber">2.15</span><span class="period">.</span>
</h3>
<div class="para" id="sec_baby_number_theory-35-1-1">If <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="121" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-mo class="mjx-n" space="4"><mjx-c class="mjx-c2208"></mjx-c></mjx-mo><mjx-texatom space="4" texclass="ORD"><mjx-mi class="mjx-ds mjx-b"><mjx-c class="mjx-c2124 TEX-A"></mjx-c></mjx-mi></mjx-texatom></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi><mo>∈</mo><mrow data-mjx-texclass="ORD"><mi mathvariant="double-struck">Z</mi></mrow></math></mjx-assistive-mml></mjx-container></span> such that <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="122" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>n</mi></math></mjx-assistive-mml></mjx-container></span> is odd, then 8 divides <span class="process-math"><mjx-container class="MathJax CtxtMenu_Attached_0" jax="CHTML" tabindex="0" ctxtmenu_counter="123" style="font-size: 118.7%; position: relative;"><mjx-math class="MJX-TEX" aria-hidden="true"><mjx-msup><mjx-mi class="mjx-i"><mjx-c class="mjx-c1D45B TEX-I"></mjx-c></mjx-mi><mjx-script style="vertical-align: 0.363em;"><mjx-texatom size="s" texclass="ORD"><mjx-mn class="mjx-n"><mjx-c class="mjx-c32"></mjx-c></mjx-mn></mjx-texatom></mjx-script></mjx-msup><mjx-mo class="mjx-n" space="3"><mjx-c class="mjx-c2212"></mjx-c></mjx-mo><mjx-mn class="mjx-n" space="3"><mjx-c class="mjx-c31"></mjx-c></mjx-mn><mjx-mtext style="font-family: MJXZERO, &quot;Open Sans&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;"><mjx-utext variant="-explicitFont" style="font-size: 82.6%; padding: 0.909em 0px 0.242em; width: 4px;">.</mjx-utext></mjx-mtext></mjx-math><mjx-assistive-mml unselectable="on" display="inline"><math xmlns="http://www.w3.org/1998/Math/MathML"><msup><mi>n</mi><mrow data-mjx-texclass="ORD"><mn>2</mn></mrow></msup><mo>−</mo><mn>1</mn><mtext>.</mtext></math></mjx-assistive-mml></mjx-container></span>
<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-35-1-1" title="Copy permalink for Paragraph">🔗</a></div></div><div class="autopermalink" onclick="copyPermalink(this)" data-description="Theorem 2.15"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-35" title="Copy permalink for Theorem 2.15">🔗</a></div></article><blockquote class="blockquote" id="sec_baby_number_theory-36">
<div class="para" id="sec_baby_number_theory-36-1">Time spent thinking about a problem is always time well spent. Even if you seem to make no progress at all.<div class="autopermalink" onclick="copyPermalink(this)" data-description="Paragraph"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html#sec_baby_number_theory-36-1" title="Copy permalink for Paragraph">🔗</a></div></div>
<cite class="attribution">―Paul Zeitz, mathematician</cite>
</blockquote><div class="autopermalink" onclick="copyPermalink(this)" data-description="Section 2.1: A Taste of Number Theory"><a href="https://danaernst.com/IntroToProofViaIBL/sec_baby_number_theory.html" title="Copy permalink for Section 2.1: A Taste of Number Theory">🔗</a></div></section></div>
<div class="ptx-content-footer">
<a class="previous-button button" href="chap_IntroToMath.html" title="Previous"><span xmlns:xlink="http://www.w3.org/1999/xlink" class="icon material-symbols-outlined" aria-hidden="true"></span><span class="name">Prev</span></a><a class="top-button button" href="#" title="Top"><span xmlns:xlink="http://www.w3.org/1999/xlink" class="icon material-symbols-outlined" aria-hidden="true"></span><span class="name">Top</span></a><a class="next-button button" href="sec_Intro_to_Logic.html" title="Next"><span class="name">Next</span><span xmlns:xlink="http://www.w3.org/1999/xlink" class="icon material-symbols-outlined" aria-hidden="true"></span></a>
</div></main>
</div>
<div id="ptx-page-footer" class="ptx-page-footer">
<a xmlns:xlink="http://www.w3.org/1999/xlink" class="pretext-link" href="https://pretextbook.org" title="PreTeXt"><div class="logo"><svg xmlns="http://www.w3.org/2000/svg" height="100%" viewBox="338 3000 8772 6866" role="img"><title>PreTeXt logo</title><g style="stroke-width:.025in; stroke:currentColor; fill:none"><polyline points="472,3590 472,9732 " style="stroke-width:174; stroke-linejoin:miter; stroke-linecap:round; "></polyline><path style="stroke-width:126;stroke-linecap:butt;" d="M 4724,9448 A 4660 4660  0  0  1  8598  9259"></path><path style="stroke-width:174;stroke-linecap:butt;" d="M 4488,9685 A 4228 4228  0  0  0   472  9732"></path><path style="stroke-width:126;stroke-linecap:butt;" d="M 4724,3590 A 4241 4241  0  0  1  8598  3496"></path><path style="stroke-width:126;stroke-linecap:round;" d="M 850,3496  A 4241 4241  0  0  1  4724  3590"></path><path style="stroke-width:126;stroke-linecap:round;" d="M 850,9259  A 4507 4507  0  0  1  4724  9448"></path><polyline points="5385,4299 4062,8125" style="stroke-width:300; stroke-linejoin:miter; stroke-linecap:round;"></polyline><polyline points="8598,3496 8598,9259" style="stroke-width:126; stroke-linejoin:miter; stroke-linecap:round;"></polyline><polyline points="850,3496 850,9259" style="stroke-width:126; stroke-linejoin:miter; stroke-linecap:round;"></polyline><polyline points="4960,9685 4488,9685" style="stroke-width:174; stroke-linejoin:miter; stroke-linecap:round;"></polyline><polyline points="3070,4582 1889,6141 3070,7700" style="stroke-width:300; stroke-linejoin:miter; stroke-linecap:round;"></polyline><polyline points="6418,4582 7600,6141 6418,7700" style="stroke-width:300; stroke-linejoin:miter; stroke-linecap:round;"></polyline><polyline points="8976,3590 8976,9732" style="stroke-width:174; stroke-linejoin:miter; stroke-linecap:round;"></polyline><path style="stroke-width:174;stroke-linecap:butt;" d="M 4960,9685 A 4228 4228  0  0  1  8976  9732"></path></g></svg></div></a><a xmlns:xlink="http://www.w3.org/1999/xlink" class="runestone-link" href="https://runestone.academy" title="Runestone Academy"><img class="logo" src="https://runestone.academy/runestone/static/images/RAIcon_cropped.png" alt="Runstone Academy logo"></a><a xmlns:xlink="http://www.w3.org/1999/xlink" class="mathjax-link" href="https://www.mathjax.org" title="MathJax"><img class="logo" src="https://www.mathjax.org/badge/badge-square-2.png" alt="MathJax logo"></a>
</div>


</body></html>
