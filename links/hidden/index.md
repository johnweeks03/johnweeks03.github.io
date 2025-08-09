<html lang="en">
<head><meta charset="utf-8"><title>A Change In The Air - Ximera</title><meta name="viewport" content="width=device-width, initial-scale=1.0, shrink-to-fit=no"><meta name="description" content="Ximera provides the backend technology for online courses"><meta name="author" content="The Ximera Project"><meta name="keywords" content="mathematics, math, maths, courses, course, education, calculus, complex analysis, algebra, geometry, graphs, plots, MOOC"><link href="/public/v1.8.1/stylesheets/base.css" rel="stylesheet"><meta property="og:title" content="A Change In The Air"><meta property="og:url" content="https://ximera.osu.edu/johnweeks03-test/aFirstXourse/aFirstFolder/aFirstActivity"><meta property="og:description" content="
A simple Ximera activity. 
"><style>/* BASICS */

.CodeMirror {
  /* Set height, width, borders, and global font properties here */
  font-family: monospace;
  height: 300px;
  color: black;
  direction: ltr;
}

/* PADDING */

.CodeMirror-lines {
  padding: 4px 0; /* Vertical padding around content */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  padding: 0 4px; /* Horizontal padding of content */
}

.CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  background-color: white; /* The little square between H and V scrollbars */
}

/* GUTTER */

.CodeMirror-gutters {
  border-right: 1px solid #ddd;
  background-color: #f7f7f7;
  white-space: nowrap;
}
.CodeMirror-linenumbers {}
.CodeMirror-linenumber {
  padding: 0 3px 0 5px;
  min-width: 20px;
  text-align: right;
  color: #999;
  white-space: nowrap;
}

.CodeMirror-guttermarker { color: black; }
.CodeMirror-guttermarker-subtle { color: #999; }

/* CURSOR */

.CodeMirror-cursor {
  border-left: 1px solid black;
  border-right: none;
  width: 0;
}
/* Shown when moving in bi-directional text */
.CodeMirror div.CodeMirror-secondarycursor {
  border-left: 1px solid silver;
}
.cm-fat-cursor .CodeMirror-cursor {
  width: auto;
  border: 0 !important;
  background: #7e7;
}
.cm-fat-cursor div.CodeMirror-cursors {
  z-index: 1;
}
.cm-fat-cursor .CodeMirror-line::selection,
.cm-fat-cursor .CodeMirror-line > span::selection, 
.cm-fat-cursor .CodeMirror-line > span > span::selection { background: transparent; }
.cm-fat-cursor .CodeMirror-line::-moz-selection,
.cm-fat-cursor .CodeMirror-line > span::-moz-selection,
.cm-fat-cursor .CodeMirror-line > span > span::-moz-selection { background: transparent; }
.cm-fat-cursor { caret-color: transparent; }
@-moz-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@-webkit-keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}
@keyframes blink {
  0% {}
  50% { background-color: transparent; }
  100% {}
}

/* Can style cursor different in overwrite (non-insert) mode */
.CodeMirror-overwrite .CodeMirror-cursor {}

.cm-tab { display: inline-block; text-decoration: inherit; }

.CodeMirror-rulers {
  position: absolute;
  left: 0; right: 0; top: -50px; bottom: 0;
  overflow: hidden;
}
.CodeMirror-ruler {
  border-left: 1px solid #ccc;
  top: 0; bottom: 0;
  position: absolute;
}

/* DEFAULT THEME */

.cm-s-default .cm-header {color: blue;}
.cm-s-default .cm-quote {color: #090;}
.cm-negative {color: #d44;}
.cm-positive {color: #292;}
.cm-header, .cm-strong {font-weight: bold;}
.cm-em {font-style: italic;}
.cm-link {text-decoration: underline;}
.cm-strikethrough {text-decoration: line-through;}

.cm-s-default .cm-keyword {color: #708;}
.cm-s-default .cm-atom {color: #219;}
.cm-s-default .cm-number {color: #164;}
.cm-s-default .cm-def {color: #00f;}
.cm-s-default .cm-variable,
.cm-s-default .cm-punctuation,
.cm-s-default .cm-property,
.cm-s-default .cm-operator {}
.cm-s-default .cm-variable-2 {color: #05a;}
.cm-s-default .cm-variable-3, .cm-s-default .cm-type {color: #085;}
.cm-s-default .cm-comment {color: #a50;}
.cm-s-default .cm-string {color: #a11;}
.cm-s-default .cm-string-2 {color: #f50;}
.cm-s-default .cm-meta {color: #555;}
.cm-s-default .cm-qualifier {color: #555;}
.cm-s-default .cm-builtin {color: #30a;}
.cm-s-default .cm-bracket {color: #997;}
.cm-s-default .cm-tag {color: #170;}
.cm-s-default .cm-attribute {color: #00c;}
.cm-s-default .cm-hr {color: #999;}
.cm-s-default .cm-link {color: #00c;}

.cm-s-default .cm-error {color: #f00;}
.cm-invalidchar {color: #f00;}

.CodeMirror-composing { border-bottom: 2px solid; }

/* Default styles for common addons */

div.CodeMirror span.CodeMirror-matchingbracket {color: #0b0;}
div.CodeMirror span.CodeMirror-nonmatchingbracket {color: #a22;}
.CodeMirror-matchingtag { background: rgba(255, 150, 0, .3); }
.CodeMirror-activeline-background {background: #e8f2ff;}

/* STOP */

/* The rest of this file contains styles related to the mechanics of
   the editor. You probably shouldn't touch them. */

.CodeMirror {
  position: relative;
  overflow: hidden;
  background: white;
}

.CodeMirror-scroll {
  overflow: scroll !important; /* Things will break if this is overridden */
  /* 50px is the magic margin used to hide the element's real scrollbars */
  /* See overflow: hidden in .CodeMirror */
  margin-bottom: -50px; margin-right: -50px;
  padding-bottom: 50px;
  height: 100%;
  outline: none; /* Prevent dragging from highlighting the element */
  position: relative;
  z-index: 0;
}
.CodeMirror-sizer {
  position: relative;
  border-right: 50px solid transparent;
}

/* The fake, visible scrollbars. Used to force redraw during scrolling
   before actual scrolling happens, thus preventing shaking and
   flickering artifacts. */
.CodeMirror-vscrollbar, .CodeMirror-hscrollbar, .CodeMirror-scrollbar-filler, .CodeMirror-gutter-filler {
  position: absolute;
  z-index: 6;
  display: none;
  outline: none;
}
.CodeMirror-vscrollbar {
  right: 0; top: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.CodeMirror-hscrollbar {
  bottom: 0; left: 0;
  overflow-y: hidden;
  overflow-x: scroll;
}
.CodeMirror-scrollbar-filler {
  right: 0; bottom: 0;
}
.CodeMirror-gutter-filler {
  left: 0; bottom: 0;
}

.CodeMirror-gutters {
  position: absolute; left: 0; top: 0;
  min-height: 100%;
  z-index: 3;
}
.CodeMirror-gutter {
  white-space: normal;
  height: 100%;
  display: inline-block;
  vertical-align: top;
  margin-bottom: -50px;
}
.CodeMirror-gutter-wrapper {
  position: absolute;
  z-index: 4;
  background: none !important;
  border: none !important;
}
.CodeMirror-gutter-background {
  position: absolute;
  top: 0; bottom: 0;
  z-index: 4;
}
.CodeMirror-gutter-elt {
  position: absolute;
  cursor: default;
  z-index: 4;
}
.CodeMirror-gutter-wrapper ::selection { background-color: transparent }
.CodeMirror-gutter-wrapper ::-moz-selection { background-color: transparent }

.CodeMirror-lines {
  cursor: text;
  min-height: 1px; /* prevents collapsing before first draw */
}
.CodeMirror pre.CodeMirror-line,
.CodeMirror pre.CodeMirror-line-like {
  /* Reset some styles that the rest of the page might have set */
  -moz-border-radius: 0; -webkit-border-radius: 0; border-radius: 0;
  border-width: 0;
  background: transparent;
  font-family: inherit;
  font-size: inherit;
  margin: 0;
  white-space: pre;
  word-wrap: normal;
  line-height: inherit;
  color: inherit;
  z-index: 2;
  position: relative;
  overflow: visible;
  -webkit-tap-highlight-color: transparent;
  -webkit-font-variant-ligatures: contextual;
  font-variant-ligatures: contextual;
}
.CodeMirror-wrap pre.CodeMirror-line,
.CodeMirror-wrap pre.CodeMirror-line-like {
  word-wrap: break-word;
  white-space: pre-wrap;
  word-break: normal;
}

.CodeMirror-linebackground {
  position: absolute;
  left: 0; right: 0; top: 0; bottom: 0;
  z-index: 0;
}

.CodeMirror-linewidget {
  position: relative;
  z-index: 2;
  padding: 0.1px; /* Force widget margins to stay inside of the container */
}

.CodeMirror-widget {}

.CodeMirror-rtl pre { direction: rtl; }

.CodeMirror-code {
  outline: none;
}

/* Force content-box sizing for the elements where we expect it */
.CodeMirror-scroll,
.CodeMirror-sizer,
.CodeMirror-gutter,
.CodeMirror-gutters,
.CodeMirror-linenumber {
  -moz-box-sizing: content-box;
  box-sizing: content-box;
}

.CodeMirror-measure {
  position: absolute;
  width: 100%;
  height: 0;
  overflow: hidden;
  visibility: hidden;
}

.CodeMirror-cursor {
  position: absolute;
  pointer-events: none;
}
.CodeMirror-measure pre { position: static; }

div.CodeMirror-cursors {
  visibility: hidden;
  position: relative;
  z-index: 3;
}
div.CodeMirror-dragcursors {
  visibility: visible;
}

.CodeMirror-focused div.CodeMirror-cursors {
  visibility: visible;
}

.CodeMirror-selected { background: #d9d9d9; }
.CodeMirror-focused .CodeMirror-selected { background: #d7d4f0; }
.CodeMirror-crosshair { cursor: crosshair; }
.CodeMirror-line::selection, .CodeMirror-line > span::selection, .CodeMirror-line > span > span::selection { background: #d7d4f0; }
.CodeMirror-line::-moz-selection, .CodeMirror-line > span::-moz-selection, .CodeMirror-line > span > span::-moz-selection { background: #d7d4f0; }

.cm-searching {
  background-color: #ffa;
  background-color: rgba(255, 255, 0, .4);
}

/* Used to force a border model for a node */
.cm-force-border { padding-right: .1px; }

@media print {
  /* Hide the cursor when printing */
  .CodeMirror div.CodeMirror-cursors {
    visibility: hidden;
  }
}

/* See issue #2901 */
.cm-tab-wrap-hack:after { content: ''; }

/* Help users use markselection to safely style text background */
span.CodeMirror-selectedtext { background: none; }


.CodeMirror-fullscreen {
  position: fixed;
  top: 0; left: 0; right: 0; bottom: 0;
  height: auto;
  z-index: 9;
}


.CodeMirror-foldmarker {
  color: blue;
  text-shadow: #b9f 1px 1px 2px, #b9f -1px -1px 2px, #b9f 1px -1px 2px, #b9f -1px 1px 2px;
  font-family: arial;
  line-height: .3;
  cursor: pointer;
}
.CodeMirror-foldgutter {
  width: .7em;
}
.CodeMirror-foldgutter-open,
.CodeMirror-foldgutter-folded {
  cursor: pointer;
}
.CodeMirror-foldgutter-open:after {
  content: "\25BE";
}
.CodeMirror-foldgutter-folded:after {
  content: "\25B8";
}


.CodeMirror-hints {
  position: absolute;
  z-index: 10;
  overflow: hidden;
  list-style: none;

  margin: 0;
  padding: 2px;

  -webkit-box-shadow: 2px 3px 5px rgba(0,0,0,.2);
  -moz-box-shadow: 2px 3px 5px rgba(0,0,0,.2);
  box-shadow: 2px 3px 5px rgba(0,0,0,.2);
  border-radius: 3px;
  border: 1px solid silver;

  background: white;
  font-size: 90%;
  font-family: monospace;

  max-height: 20em;
  overflow-y: auto;
}

.CodeMirror-hint {
  margin: 0;
  padding: 0 4px;
  border-radius: 2px;
  white-space: pre;
  color: black;
  cursor: pointer;
}

li.CodeMirror-hint-active {
  background: #08f;
  color: white;
}


/*! jQuery UI - v1.12.0 - 2016-07-08
* http://jqueryui.com
* Includes: core.css, accordion.css, autocomplete.css, menu.css, button.css, controlgroup.css, checkboxradio.css, datepicker.css, dialog.css, draggable.css, resizable.css, progressbar.css, selectable.css, selectmenu.css, slider.css, sortable.css, spinner.css, tabs.css, tooltip.css, theme.css
* To view and modify this theme, visit http://jqueryui.com/themeroller/?ffDefault=Verdana%2CArial%2Csans-serif&fwDefault=normal&fsDefault=1.1em&cornerRadius=4px&bgColorHeader=cccccc&bgTextureHeader=highlight_soft&bgImgOpacityHeader=75&borderColorHeader=aaaaaa&fcHeader=222222&iconColorHeader=222222&bgColorContent=ffffff&bgTextureContent=flat&bgImgOpacityContent=75&borderColorContent=aaaaaa&fcContent=222222&iconColorContent=222222&bgColorDefault=e6e6e6&bgTextureDefault=glass&bgImgOpacityDefault=75&borderColorDefault=d3d3d3&fcDefault=555555&iconColorDefault=888888&bgColorHover=dadada&bgTextureHover=glass&bgImgOpacityHover=75&borderColorHover=999999&fcHover=212121&iconColorHover=454545&bgColorActive=ffffff&bgTextureActive=glass&bgImgOpacityActive=65&borderColorActive=aaaaaa&fcActive=212121&iconColorActive=454545&bgColorHighlight=fbf9ee&bgTextureHighlight=glass&bgImgOpacityHighlight=55&borderColorHighlight=fcefa1&fcHighlight=363636&iconColorHighlight=2e83ff&bgColorError=fef1ec&bgTextureError=glass&bgImgOpacityError=95&borderColorError=cd0a0a&fcError=cd0a0a&iconColorError=cd0a0a&bgColorOverlay=aaaaaa&bgTextureOverlay=flat&bgImgOpacityOverlay=0&opacityOverlay=30&bgColorShadow=aaaaaa&bgTextureShadow=flat&bgImgOpacityShadow=0&opacityShadow=30&thicknessShadow=8px&offsetTopShadow=-8px&offsetLeftShadow=-8px&cornerRadiusShadow=8px
* Copyright jQuery Foundation and other contributors; Licensed MIT */

.ui-helper-hidden{display:none}.ui-helper-hidden-accessible{border:0;clip:rect(0 0 0 0);height:1px;margin:-1px;overflow:hidden;padding:0;position:absolute;width:1px}.ui-helper-reset{margin:0;padding:0;border:0;outline:0;line-height:1.3;text-decoration:none;font-size:100%;list-style:none}.ui-helper-clearfix:before,.ui-helper-clearfix:after{content:"";display:table;border-collapse:collapse}.ui-helper-clearfix:after{clear:both}.ui-helper-zfix{width:100%;height:100%;top:0;left:0;position:absolute;opacity:0;filter:Alpha(Opacity=0)}.ui-front{z-index:100}.ui-state-disabled{cursor:default!important;pointer-events:none}.ui-icon{display:inline-block;vertical-align:middle;margin-top:-.25em;position:relative;text-indent:-99999px;overflow:hidden;background-repeat:no-repeat}.ui-widget-icon-block{left:50%;margin-left:-8px;display:block}.ui-widget-overlay{position:fixed;top:0;left:0;width:100%;height:100%}.ui-accordion .ui-accordion-header{display:block;cursor:pointer;position:relative;margin:2px 0 0 0;padding:.5em .5em .5em .7em;font-size:100%}.ui-accordion .ui-accordion-content{padding:1em 2.2em;border-top:0;overflow:auto}.ui-autocomplete{position:absolute;top:0;left:0;cursor:default}.ui-menu{list-style:none;padding:0;margin:0;display:block;outline:0}.ui-menu .ui-menu{position:absolute}.ui-menu .ui-menu-item{margin:0;cursor:pointer;list-style-image:url("data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7")}.ui-menu .ui-menu-item-wrapper{position:relative;padding:3px 1em 3px .4em}.ui-menu .ui-menu-divider{margin:5px 0;height:0;font-size:0;line-height:0;border-width:1px 0 0 0}.ui-menu .ui-state-focus,.ui-menu .ui-state-active{margin:-1px}.ui-menu-icons{position:relative}.ui-menu-icons .ui-menu-item-wrapper{padding-left:2em}.ui-menu .ui-icon{position:absolute;top:0;bottom:0;left:.2em;margin:auto 0}.ui-menu .ui-menu-icon{left:auto;right:0}.ui-button{padding:.4em 1em;display:inline-block;position:relative;line-height:normal;margin-right:.1em;cursor:pointer;vertical-align:middle;text-align:center;-webkit-user-select:none;-moz-user-select:none;-ms-user-select:none;user-select:none;overflow:visible}.ui-button,.ui-button:link,.ui-button:visited,.ui-button:hover,.ui-button:active{text-decoration:none}.ui-button-icon-only{width:2em;box-sizing:border-box;text-indent:-9999px;white-space:nowrap}input.ui-button.ui-button-icon-only{text-indent:0}.ui-button-icon-only .ui-icon{position:absolute;top:50%;left:50%;margin-top:-8px;margin-left:-8px}.ui-button.ui-icon-notext .ui-icon{padding:0;width:2.1em;height:2.1em;text-indent:-9999px;white-space:nowrap}input.ui-button.ui-icon-notext .ui-icon{width:auto;height:auto;text-indent:0;white-space:normal;padding:.4em 1em}input.ui-button::-moz-focus-inner,button.ui-button::-moz-focus-inner{border:0;padding:0}.ui-controlgroup{vertical-align:middle;display:inline-block}.ui-controlgroup > .ui-controlgroup-item{float:left;margin-left:0;margin-right:0}.ui-controlgroup > .ui-controlgroup-item:focus,.ui-controlgroup > .ui-controlgroup-item.ui-visual-focus{z-index:9999}.ui-controlgroup-vertical > .ui-controlgroup-item{display:block;float:none;width:100%;margin-top:0;margin-bottom:0;text-align:left}.ui-controlgroup-vertical .ui-controlgroup-item{box-sizing:border-box}.ui-controlgroup .ui-controlgroup-label{padding:.4em 1em}.ui-controlgroup .ui-controlgroup-label span{font-size:80%}.ui-controlgroup-horizontal .ui-controlgroup-label + .ui-controlgroup-item{border-left:none}.ui-controlgroup-vertical .ui-controlgroup-label + .ui-controlgroup-item{border-top:none}.ui-controlgroup-horizontal .ui-controlgroup-label.ui-widget-content{border-right:none}.ui-controlgroup-vertical .ui-controlgroup-label.ui-widget-content{border-bottom:none}.ui-controlgroup-vertical .ui-spinner-input{width:75%;width:calc( 100% - 2.4em )}.ui-controlgroup-vertical .ui-spinner .ui-spinner-up{border-top-style:solid}.ui-checkboxradio-label .ui-icon-background{box-shadow:inset 1px 1px 1px #ccc;border-radius:.12em;border:none}.ui-checkboxradio-radio-label .ui-icon-background{width:16px;height:16px;border-radius:1em;overflow:visible;border:none}.ui-checkboxradio-radio-label.ui-checkboxradio-checked .ui-icon,.ui-checkboxradio-radio-label.ui-checkboxradio-checked:hover .ui-icon{background-image:none;width:8px;height:8px;border-width:4px;border-style:solid}.ui-checkboxradio-disabled{pointer-events:none}.ui-datepicker{width:17em;padding:.2em .2em 0;display:none}.ui-datepicker .ui-datepicker-header{position:relative;padding:.2em 0}.ui-datepicker .ui-datepicker-prev,.ui-datepicker .ui-datepicker-next{position:absolute;top:2px;width:1.8em;height:1.8em}.ui-datepicker .ui-datepicker-prev-hover,.ui-datepicker .ui-datepicker-next-hover{top:1px}.ui-datepicker .ui-datepicker-prev{left:2px}.ui-datepicker .ui-datepicker-next{right:2px}.ui-datepicker .ui-datepicker-prev-hover{left:1px}.ui-datepicker .ui-datepicker-next-hover{right:1px}.ui-datepicker .ui-datepicker-prev span,.ui-datepicker .ui-datepicker-next span{display:block;position:absolute;left:50%;margin-left:-8px;top:50%;margin-top:-8px}.ui-datepicker .ui-datepicker-title{margin:0 2.3em;line-height:1.8em;text-align:center}.ui-datepicker .ui-datepicker-title select{font-size:1em;margin:1px 0}.ui-datepicker select.ui-datepicker-month,.ui-datepicker select.ui-datepicker-year{width:45%}.ui-datepicker table{width:100%;font-size:.9em;border-collapse:collapse;margin:0 0 .4em}.ui-datepicker th{padding:.7em .3em;text-align:center;font-weight:bold;border:0}.ui-datepicker td{border:0;padding:1px}.ui-datepicker td span,.ui-datepicker td a{display:block;padding:.2em;text-align:right;text-decoration:none}.ui-datepicker .ui-datepicker-buttonpane{background-image:none;margin:.7em 0 0 0;padding:0 .2em;border-left:0;border-right:0;border-bottom:0}.ui-datepicker .ui-datepicker-buttonpane button{float:right;margin:.5em .2em .4em;cursor:pointer;padding:.2em .6em .3em .6em;width:auto;overflow:visible}.ui-datepicker .ui-datepicker-buttonpane button.ui-datepicker-current{float:left}.ui-datepicker.ui-datepicker-multi{width:auto}.ui-datepicker-multi .ui-datepicker-group{float:left}.ui-datepicker-multi .ui-datepicker-group table{width:95%;margin:0 auto .4em}.ui-datepicker-multi-2 .ui-datepicker-group{width:50%}.ui-datepicker-multi-3 .ui-datepicker-group{width:33.3%}.ui-datepicker-multi-4 .ui-datepicker-group{width:25%}.ui-datepicker-multi .ui-datepicker-group-last .ui-datepicker-header,.ui-datepicker-multi .ui-datepicker-group-middle .ui-datepicker-header{border-left-width:0}.ui-datepicker-multi .ui-datepicker-buttonpane{clear:left}.ui-datepicker-row-break{clear:both;width:100%;font-size:0}.ui-datepicker-rtl{direction:rtl}.ui-datepicker-rtl .ui-datepicker-prev{right:2px;left:auto}.ui-datepicker-rtl .ui-datepicker-next{left:2px;right:auto}.ui-datepicker-rtl .ui-datepicker-prev:hover{right:1px;left:auto}.ui-datepicker-rtl .ui-datepicker-next:hover{left:1px;right:auto}.ui-datepicker-rtl .ui-datepicker-buttonpane{clear:right}.ui-datepicker-rtl .ui-datepicker-buttonpane button{float:left}.ui-datepicker-rtl .ui-datepicker-buttonpane button.ui-datepicker-current,.ui-datepicker-rtl .ui-datepicker-group{float:right}.ui-datepicker-rtl .ui-datepicker-group-last .ui-datepicker-header,.ui-datepicker-rtl .ui-datepicker-group-middle .ui-datepicker-header{border-right-width:0;border-left-width:1px}.ui-datepicker .ui-icon{display:block;text-indent:-99999px;overflow:hidden;background-repeat:no-repeat;left:.5em;top:.3em}.ui-dialog{position:absolute;top:0;left:0;padding:.2em;outline:0}.ui-dialog .ui-dialog-titlebar{padding:.4em 1em;position:relative}.ui-dialog .ui-dialog-title{float:left;margin:.1em 0;white-space:nowrap;width:90%;overflow:hidden;text-overflow:ellipsis}.ui-dialog .ui-dialog-titlebar-close{position:absolute;right:.3em;top:50%;width:20px;margin:-10px 0 0 0;padding:1px;height:20px}.ui-dialog .ui-dialog-content{position:relative;border:0;padding:.5em 1em;background:none;overflow:auto}.ui-dialog .ui-dialog-buttonpane{text-align:left;border-width:1px 0 0 0;background-image:none;margin-top:.5em;padding:.3em 1em .5em .4em}.ui-dialog .ui-dialog-buttonpane .ui-dialog-buttonset{float:right}.ui-dialog .ui-dialog-buttonpane button{margin:.5em .4em .5em 0;cursor:pointer}.ui-dialog .ui-resizable-n{height:2px;top:0}.ui-dialog .ui-resizable-e{width:2px;right:0}.ui-dialog .ui-resizable-s{height:2px;bottom:0}.ui-dialog .ui-resizable-w{width:2px;left:0}.ui-dialog .ui-resizable-se,.ui-dialog .ui-resizable-sw,.ui-dialog .ui-resizable-ne,.ui-dialog .ui-resizable-nw{width:7px;height:7px}.ui-dialog .ui-resizable-se{right:0;bottom:0}.ui-dialog .ui-resizable-sw{left:0;bottom:0}.ui-dialog .ui-resizable-ne{right:0;top:0}.ui-dialog .ui-resizable-nw{left:0;top:0}.ui-draggable .ui-dialog-titlebar{cursor:move}.ui-draggable-handle{-ms-touch-action:none;touch-action:none}.ui-resizable{position:relative}.ui-resizable-handle{position:absolute;font-size:0.1px;display:block;-ms-touch-action:none;touch-action:none}.ui-resizable-disabled .ui-resizable-handle,.ui-resizable-autohide .ui-resizable-handle{display:none}.ui-resizable-n{cursor:n-resize;height:7px;width:100%;top:-5px;left:0}.ui-resizable-s{cursor:s-resize;height:7px;width:100%;bottom:-5px;left:0}.ui-resizable-e{cursor:e-resize;width:7px;right:-5px;top:0;height:100%}.ui-resizable-w{cursor:w-resize;width:7px;left:-5px;top:0;height:100%}.ui-resizable-se{cursor:se-resize;width:12px;height:12px;right:1px;bottom:1px}.ui-resizable-sw{cursor:sw-resize;width:9px;height:9px;left:-5px;bottom:-5px}.ui-resizable-nw{cursor:nw-resize;width:9px;height:9px;left:-5px;top:-5px}.ui-resizable-ne{cursor:ne-resize;width:9px;height:9px;right:-5px;top:-5px}.ui-progressbar{height:2em;text-align:left;overflow:hidden}.ui-progressbar .ui-progressbar-value{margin:-1px;height:100%}.ui-progressbar .ui-progressbar-overlay{background:url("data:image/gif;base64,R0lGODlhKAAoAIABAAAAAP///yH/C05FVFNDQVBFMi4wAwEAAAAh+QQJAQABACwAAAAAKAAoAAACkYwNqXrdC52DS06a7MFZI+4FHBCKoDeWKXqymPqGqxvJrXZbMx7Ttc+w9XgU2FB3lOyQRWET2IFGiU9m1frDVpxZZc6bfHwv4c1YXP6k1Vdy292Fb6UkuvFtXpvWSzA+HycXJHUXiGYIiMg2R6W459gnWGfHNdjIqDWVqemH2ekpObkpOlppWUqZiqr6edqqWQAAIfkECQEAAQAsAAAAACgAKAAAApSMgZnGfaqcg1E2uuzDmmHUBR8Qil95hiPKqWn3aqtLsS18y7G1SzNeowWBENtQd+T1JktP05nzPTdJZlR6vUxNWWjV+vUWhWNkWFwxl9VpZRedYcflIOLafaa28XdsH/ynlcc1uPVDZxQIR0K25+cICCmoqCe5mGhZOfeYSUh5yJcJyrkZWWpaR8doJ2o4NYq62lAAACH5BAkBAAEALAAAAAAoACgAAAKVDI4Yy22ZnINRNqosw0Bv7i1gyHUkFj7oSaWlu3ovC8GxNso5fluz3qLVhBVeT/Lz7ZTHyxL5dDalQWPVOsQWtRnuwXaFTj9jVVh8pma9JjZ4zYSj5ZOyma7uuolffh+IR5aW97cHuBUXKGKXlKjn+DiHWMcYJah4N0lYCMlJOXipGRr5qdgoSTrqWSq6WFl2ypoaUAAAIfkECQEAAQAsAAAAACgAKAAAApaEb6HLgd/iO7FNWtcFWe+ufODGjRfoiJ2akShbueb0wtI50zm02pbvwfWEMWBQ1zKGlLIhskiEPm9R6vRXxV4ZzWT2yHOGpWMyorblKlNp8HmHEb/lCXjcW7bmtXP8Xt229OVWR1fod2eWqNfHuMjXCPkIGNileOiImVmCOEmoSfn3yXlJWmoHGhqp6ilYuWYpmTqKUgAAIfkECQEAAQAsAAAAACgAKAAAApiEH6kb58biQ3FNWtMFWW3eNVcojuFGfqnZqSebuS06w5V80/X02pKe8zFwP6EFWOT1lDFk8rGERh1TTNOocQ61Hm4Xm2VexUHpzjymViHrFbiELsefVrn6XKfnt2Q9G/+Xdie499XHd2g4h7ioOGhXGJboGAnXSBnoBwKYyfioubZJ2Hn0RuRZaflZOil56Zp6iioKSXpUAAAh+QQJAQABACwAAAAAKAAoAAACkoQRqRvnxuI7kU1a1UU5bd5tnSeOZXhmn5lWK3qNTWvRdQxP8qvaC+/yaYQzXO7BMvaUEmJRd3TsiMAgswmNYrSgZdYrTX6tSHGZO73ezuAw2uxuQ+BbeZfMxsexY35+/Qe4J1inV0g4x3WHuMhIl2jXOKT2Q+VU5fgoSUI52VfZyfkJGkha6jmY+aaYdirq+lQAACH5BAkBAAEALAAAAAAoACgAAAKWBIKpYe0L3YNKToqswUlvznigd4wiR4KhZrKt9Upqip61i9E3vMvxRdHlbEFiEXfk9YARYxOZZD6VQ2pUunBmtRXo1Lf8hMVVcNl8JafV38aM2/Fu5V16Bn63r6xt97j09+MXSFi4BniGFae3hzbH9+hYBzkpuUh5aZmHuanZOZgIuvbGiNeomCnaxxap2upaCZsq+1kAACH5BAkBAAEALAAAAAAoACgAAAKXjI8By5zf4kOxTVrXNVlv1X0d8IGZGKLnNpYtm8Lr9cqVeuOSvfOW79D9aDHizNhDJidFZhNydEahOaDH6nomtJjp1tutKoNWkvA6JqfRVLHU/QUfau9l2x7G54d1fl995xcIGAdXqMfBNadoYrhH+Mg2KBlpVpbluCiXmMnZ2Sh4GBqJ+ckIOqqJ6LmKSllZmsoq6wpQAAAh+QQJAQABACwAAAAAKAAoAAAClYx/oLvoxuJDkU1a1YUZbJ59nSd2ZXhWqbRa2/gF8Gu2DY3iqs7yrq+xBYEkYvFSM8aSSObE+ZgRl1BHFZNr7pRCavZ5BW2142hY3AN/zWtsmf12p9XxxFl2lpLn1rseztfXZjdIWIf2s5dItwjYKBgo9yg5pHgzJXTEeGlZuenpyPmpGQoKOWkYmSpaSnqKileI2FAAACH5BAkBAAEALAAAAAAoACgAAAKVjB+gu+jG4kORTVrVhRlsnn2dJ3ZleFaptFrb+CXmO9OozeL5VfP99HvAWhpiUdcwkpBH3825AwYdU8xTqlLGhtCosArKMpvfa1mMRae9VvWZfeB2XfPkeLmm18lUcBj+p5dnN8jXZ3YIGEhYuOUn45aoCDkp16hl5IjYJvjWKcnoGQpqyPlpOhr3aElaqrq56Bq7VAAAOw==");height:100%;filter:alpha(opacity=25);opacity:0.25}.ui-progressbar-indeterminate .ui-progressbar-value{background-image:none}.ui-selectable{-ms-touch-action:none;touch-action:none}.ui-selectable-helper{position:absolute;z-index:100;border:1px dotted black}.ui-selectmenu-menu{padding:0;margin:0;position:absolute;top:0;left:0;display:none}.ui-selectmenu-menu .ui-menu{overflow:auto;overflow-x:hidden;padding-bottom:1px}.ui-selectmenu-menu .ui-menu .ui-selectmenu-optgroup{font-size:1em;font-weight:bold;line-height:1.5;padding:2px 0.4em;margin:0.5em 0 0 0;height:auto;border:0}.ui-selectmenu-open{display:block}.ui-selectmenu-text{display:block;margin-right:20px;overflow:hidden;text-overflow:ellipsis}.ui-selectmenu-button.ui-button{text-align:left;white-space:nowrap;width:14em}.ui-selectmenu-icon.ui-icon{float:right;margin-top:0}.ui-slider{position:relative;text-align:left}.ui-slider .ui-slider-handle{position:absolute;z-index:2;width:1.2em;height:1.2em;cursor:default;-ms-touch-action:none;touch-action:none}.ui-slider .ui-slider-range{position:absolute;z-index:1;font-size:.7em;display:block;border:0;background-position:0 0}.ui-slider.ui-state-disabled .ui-slider-handle,.ui-slider.ui-state-disabled .ui-slider-range{filter:inherit}.ui-slider-horizontal{height:.8em}.ui-slider-horizontal .ui-slider-handle{top:-.3em;margin-left:-.6em}.ui-slider-horizontal .ui-slider-range{top:0;height:100%}.ui-slider-horizontal .ui-slider-range-min{left:0}.ui-slider-horizontal .ui-slider-range-max{right:0}.ui-slider-vertical{width:.8em;height:100px}.ui-slider-vertical .ui-slider-handle{left:-.3em;margin-left:0;margin-bottom:-.6em}.ui-slider-vertical .ui-slider-range{left:0;width:100%}.ui-slider-vertical .ui-slider-range-min{bottom:0}.ui-slider-vertical .ui-slider-range-max{top:0}.ui-sortable-handle{-ms-touch-action:none;touch-action:none}.ui-spinner{position:relative;display:inline-block;overflow:hidden;padding:0;vertical-align:middle}.ui-spinner-input{border:none;background:none;color:inherit;padding:.222em 0;margin:.2em 0;vertical-align:middle;margin-left:.4em;margin-right:2em}.ui-spinner-button{width:1.6em;height:50%;font-size:.5em;padding:0;margin:0;text-align:center;position:absolute;cursor:default;display:block;overflow:hidden;right:0}.ui-spinner a.ui-spinner-button{border-top-style:none;border-bottom-style:none;border-right-style:none}.ui-spinner-up{top:0}.ui-spinner-down{bottom:0}.ui-tabs{position:relative;padding:.2em}.ui-tabs .ui-tabs-nav{margin:0;padding:.2em .2em 0}.ui-tabs .ui-tabs-nav li{list-style:none;float:left;position:relative;top:0;margin:1px .2em 0 0;border-bottom-width:0;padding:0;white-space:nowrap}.ui-tabs .ui-tabs-nav .ui-tabs-anchor{float:left;padding:.5em 1em;text-decoration:none}.ui-tabs .ui-tabs-nav li.ui-tabs-active{margin-bottom:-1px;padding-bottom:1px}.ui-tabs .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor,.ui-tabs .ui-tabs-nav li.ui-state-disabled .ui-tabs-anchor,.ui-tabs .ui-tabs-nav li.ui-tabs-loading .ui-tabs-anchor{cursor:text}.ui-tabs-collapsible .ui-tabs-nav li.ui-tabs-active .ui-tabs-anchor{cursor:pointer}.ui-tabs .ui-tabs-panel{display:block;border-width:0;padding:1em 1.4em;background:none}.ui-tooltip{padding:8px;position:absolute;z-index:9999;max-width:300px}body .ui-tooltip{border-width:2px}.ui-widget{font-family:Verdana,Arial,sans-serif;font-size:1.1em}.ui-widget .ui-widget{font-size:1em}.ui-widget input,.ui-widget select,.ui-widget textarea,.ui-widget button{font-family:Verdana,Arial,sans-serif;font-size:1em}.ui-widget.ui-widget-content{border:1px solid #d3d3d3}.ui-widget-content{border:1px solid #aaa;background:#fff;color:#222}.ui-widget-content a{color:#222}.ui-widget-header{border:1px solid #aaa;background:#ccc url("https://sagecell.sagemath.org/static/images/ui-bg_highlight-soft_75_cccccc_1x100.png") 50% 50% repeat-x;color:#222;font-weight:bold}.ui-widget-header a{color:#222}.ui-state-default,.ui-widget-content .ui-state-default,.ui-widget-header .ui-state-default,.ui-button,html .ui-button.ui-state-disabled:hover,html .ui-button.ui-state-disabled:active{border:1px solid #d3d3d3;background:#e6e6e6 url("https://sagecell.sagemath.org/static/images/ui-bg_glass_75_e6e6e6_1x400.png") 50% 50% repeat-x;font-weight:normal;color:#555}.ui-state-default a,.ui-state-default a:link,.ui-state-default a:visited,a.ui-button,a:link.ui-button,a:visited.ui-button,.ui-button{color:#555;text-decoration:none}.ui-state-hover,.ui-widget-content .ui-state-hover,.ui-widget-header .ui-state-hover,.ui-state-focus,.ui-widget-content .ui-state-focus,.ui-widget-header .ui-state-focus,.ui-button:hover,.ui-button:focus{border:1px solid #999;background:#dadada url("https://sagecell.sagemath.org/static/images/ui-bg_glass_75_dadada_1x400.png") 50% 50% repeat-x;font-weight:normal;color:#212121}.ui-state-hover a,.ui-state-hover a:hover,.ui-state-hover a:link,.ui-state-hover a:visited,.ui-state-focus a,.ui-state-focus a:hover,.ui-state-focus a:link,.ui-state-focus a:visited,a.ui-button:hover,a.ui-button:focus{color:#212121;text-decoration:none}.ui-visual-focus{box-shadow:0 0 3px 1px rgb(94,158,214)}.ui-state-active,.ui-widget-content .ui-state-active,.ui-widget-header .ui-state-active,a.ui-button:active,.ui-button:active,.ui-button.ui-state-active:hover{border:1px solid #aaa;background:#fff url("https://sagecell.sagemath.org/static/images/ui-bg_glass_65_ffffff_1x400.png") 50% 50% repeat-x;font-weight:normal;color:#212121}.ui-icon-background,.ui-state-active .ui-icon-background{border:#aaa;background-color:#212121}.ui-state-active a,.ui-state-active a:link,.ui-state-active a:visited{color:#212121;text-decoration:none}.ui-state-highlight,.ui-widget-content .ui-state-highlight,.ui-widget-header .ui-state-highlight{border:1px solid #fcefa1;background:#fbf9ee url("https://sagecell.sagemath.org/static/images/ui-bg_glass_55_fbf9ee_1x400.png") 50% 50% repeat-x;color:#363636}.ui-state-checked{border:1px solid #fcefa1;background:#fbf9ee}.ui-state-highlight a,.ui-widget-content .ui-state-highlight a,.ui-widget-header .ui-state-highlight a{color:#363636}.ui-state-error,.ui-widget-content .ui-state-error,.ui-widget-header .ui-state-error{border:1px solid #cd0a0a;background:#fef1ec url("https://sagecell.sagemath.org/static/images/ui-bg_glass_95_fef1ec_1x400.png") 50% 50% repeat-x;color:#cd0a0a}.ui-state-error a,.ui-widget-content .ui-state-error a,.ui-widget-header .ui-state-error a{color:#cd0a0a}.ui-state-error-text,.ui-widget-content .ui-state-error-text,.ui-widget-header .ui-state-error-text{color:#cd0a0a}.ui-priority-primary,.ui-widget-content .ui-priority-primary,.ui-widget-header .ui-priority-primary{font-weight:bold}.ui-priority-secondary,.ui-widget-content .ui-priority-secondary,.ui-widget-header .ui-priority-secondary{opacity:.7;filter:Alpha(Opacity=70);font-weight:normal}.ui-state-disabled,.ui-widget-content .ui-state-disabled,.ui-widget-header .ui-state-disabled{opacity:.35;filter:Alpha(Opacity=35);background-image:none}.ui-state-disabled .ui-icon{filter:Alpha(Opacity=35)}.ui-icon{width:16px;height:16px}.ui-icon,.ui-widget-content .ui-icon{background-image:url("https://sagecell.sagemath.org/static/images/ui-icons_222222_256x240.png")}.ui-widget-header .ui-icon{background-image:url("https://sagecell.sagemath.org/static/images/ui-icons_222222_256x240.png")}.ui-button .ui-icon{background-image:url("https://sagecell.sagemath.org/static/images/ui-icons_888888_256x240.png")}.ui-state-hover .ui-icon,.ui-state-focus .ui-icon,.ui-button:hover .ui-icon,.ui-button:focus .ui-icon,.ui-state-default .ui-icon{background-image:url("https://sagecell.sagemath.org/static/images/ui-icons_454545_256x240.png")}.ui-state-active .ui-icon,.ui-button:active .ui-icon{background-image:url("https://sagecell.sagemath.org/static/images/ui-icons_454545_256x240.png")}.ui-state-highlight .ui-icon,.ui-button .ui-state-highlight.ui-icon{background-image:url("https://sagecell.sagemath.org/static/images/ui-icons_2e83ff_256x240.png")}.ui-state-error .ui-icon,.ui-state-error-text .ui-icon{background-image:url("https://sagecell.sagemath.org/static/images/ui-icons_cd0a0a_256x240.png")}.ui-icon-blank{background-position:16px 16px}.ui-icon-caret-1-n{background-position:0 0}.ui-icon-caret-1-ne{background-position:-16px 0}.ui-icon-caret-1-e{background-position:-32px 0}.ui-icon-caret-1-se{background-position:-48px 0}.ui-icon-caret-1-s{background-position:-65px 0}.ui-icon-caret-1-sw{background-position:-80px 0}.ui-icon-caret-1-w{background-position:-96px 0}.ui-icon-caret-1-nw{background-position:-112px 0}.ui-icon-caret-2-n-s{background-position:-128px 0}.ui-icon-caret-2-e-w{background-position:-144px 0}.ui-icon-triangle-1-n{background-position:0 -16px}.ui-icon-triangle-1-ne{background-position:-16px -16px}.ui-icon-triangle-1-e{background-position:-32px -16px}.ui-icon-triangle-1-se{background-position:-48px -16px}.ui-icon-triangle-1-s{background-position:-65px -16px}.ui-icon-triangle-1-sw{background-position:-80px -16px}.ui-icon-triangle-1-w{background-position:-96px -16px}.ui-icon-triangle-1-nw{background-position:-112px -16px}.ui-icon-triangle-2-n-s{background-position:-128px -16px}.ui-icon-triangle-2-e-w{background-position:-144px -16px}.ui-icon-arrow-1-n{background-position:0 -32px}.ui-icon-arrow-1-ne{background-position:-16px -32px}.ui-icon-arrow-1-e{background-position:-32px -32px}.ui-icon-arrow-1-se{background-position:-48px -32px}.ui-icon-arrow-1-s{background-position:-65px -32px}.ui-icon-arrow-1-sw{background-position:-80px -32px}.ui-icon-arrow-1-w{background-position:-96px -32px}.ui-icon-arrow-1-nw{background-position:-112px -32px}.ui-icon-arrow-2-n-s{background-position:-128px -32px}.ui-icon-arrow-2-ne-sw{background-position:-144px -32px}.ui-icon-arrow-2-e-w{background-position:-160px -32px}.ui-icon-arrow-2-se-nw{background-position:-176px -32px}.ui-icon-arrowstop-1-n{background-position:-192px -32px}.ui-icon-arrowstop-1-e{background-position:-208px -32px}.ui-icon-arrowstop-1-s{background-position:-224px -32px}.ui-icon-arrowstop-1-w{background-position:-240px -32px}.ui-icon-arrowthick-1-n{background-position:1px -48px}.ui-icon-arrowthick-1-ne{background-position:-16px -48px}.ui-icon-arrowthick-1-e{background-position:-32px -48px}.ui-icon-arrowthick-1-se{background-position:-48px -48px}.ui-icon-arrowthick-1-s{background-position:-64px -48px}.ui-icon-arrowthick-1-sw{background-position:-80px -48px}.ui-icon-arrowthick-1-w{background-position:-96px -48px}.ui-icon-arrowthick-1-nw{background-position:-112px -48px}.ui-icon-arrowthick-2-n-s{background-position:-128px -48px}.ui-icon-arrowthick-2-ne-sw{background-position:-144px -48px}.ui-icon-arrowthick-2-e-w{background-position:-160px -48px}.ui-icon-arrowthick-2-se-nw{background-position:-176px -48px}.ui-icon-arrowthickstop-1-n{background-position:-192px -48px}.ui-icon-arrowthickstop-1-e{background-position:-208px -48px}.ui-icon-arrowthickstop-1-s{background-position:-224px -48px}.ui-icon-arrowthickstop-1-w{background-position:-240px -48px}.ui-icon-arrowreturnthick-1-w{background-position:0 -64px}.ui-icon-arrowreturnthick-1-n{background-position:-16px -64px}.ui-icon-arrowreturnthick-1-e{background-position:-32px -64px}.ui-icon-arrowreturnthick-1-s{background-position:-48px -64px}.ui-icon-arrowreturn-1-w{background-position:-64px -64px}.ui-icon-arrowreturn-1-n{background-position:-80px -64px}.ui-icon-arrowreturn-1-e{background-position:-96px -64px}.ui-icon-arrowreturn-1-s{background-position:-112px -64px}.ui-icon-arrowrefresh-1-w{background-position:-128px -64px}.ui-icon-arrowrefresh-1-n{background-position:-144px -64px}.ui-icon-arrowrefresh-1-e{background-position:-160px -64px}.ui-icon-arrowrefresh-1-s{background-position:-176px -64px}.ui-icon-arrow-4{background-position:0 -80px}.ui-icon-arrow-4-diag{background-position:-16px -80px}.ui-icon-extlink{background-position:-32px -80px}.ui-icon-newwin{background-position:-48px -80px}.ui-icon-refresh{background-position:-64px -80px}.ui-icon-shuffle{background-position:-80px -80px}.ui-icon-transfer-e-w{background-position:-96px -80px}.ui-icon-transferthick-e-w{background-position:-112px -80px}.ui-icon-folder-collapsed{background-position:0 -96px}.ui-icon-folder-open{background-position:-16px -96px}.ui-icon-document{background-position:-32px -96px}.ui-icon-document-b{background-position:-48px -96px}.ui-icon-note{background-position:-64px -96px}.ui-icon-mail-closed{background-position:-80px -96px}.ui-icon-mail-open{background-position:-96px -96px}.ui-icon-suitcase{background-position:-112px -96px}.ui-icon-comment{background-position:-128px -96px}.ui-icon-person{background-position:-144px -96px}.ui-icon-print{background-position:-160px -96px}.ui-icon-trash{background-position:-176px -96px}.ui-icon-locked{background-position:-192px -96px}.ui-icon-unlocked{background-position:-208px -96px}.ui-icon-bookmark{background-position:-224px -96px}.ui-icon-tag{background-position:-240px -96px}.ui-icon-home{background-position:0 -112px}.ui-icon-flag{background-position:-16px -112px}.ui-icon-calendar{background-position:-32px -112px}.ui-icon-cart{background-position:-48px -112px}.ui-icon-pencil{background-position:-64px -112px}.ui-icon-clock{background-position:-80px -112px}.ui-icon-disk{background-position:-96px -112px}.ui-icon-calculator{background-position:-112px -112px}.ui-icon-zoomin{background-position:-128px -112px}.ui-icon-zoomout{background-position:-144px -112px}.ui-icon-search{background-position:-160px -112px}.ui-icon-wrench{background-position:-176px -112px}.ui-icon-gear{background-position:-192px -112px}.ui-icon-heart{background-position:-208px -112px}.ui-icon-star{background-position:-224px -112px}.ui-icon-link{background-position:-240px -112px}.ui-icon-cancel{background-position:0 -128px}.ui-icon-plus{background-position:-16px -128px}.ui-icon-plusthick{background-position:-32px -128px}.ui-icon-minus{background-position:-48px -128px}.ui-icon-minusthick{background-position:-64px -128px}.ui-icon-close{background-position:-80px -128px}.ui-icon-closethick{background-position:-96px -128px}.ui-icon-key{background-position:-112px -128px}.ui-icon-lightbulb{background-position:-128px -128px}.ui-icon-scissors{background-position:-144px -128px}.ui-icon-clipboard{background-position:-160px -128px}.ui-icon-copy{background-position:-176px -128px}.ui-icon-contact{background-position:-192px -128px}.ui-icon-image{background-position:-208px -128px}.ui-icon-video{background-position:-224px -128px}.ui-icon-script{background-position:-240px -128px}.ui-icon-alert{background-position:0 -144px}.ui-icon-info{background-position:-16px -144px}.ui-icon-notice{background-position:-32px -144px}.ui-icon-help{background-position:-48px -144px}.ui-icon-check{background-position:-64px -144px}.ui-icon-bullet{background-position:-80px -144px}.ui-icon-radio-on{background-position:-96px -144px}.ui-icon-radio-off{background-position:-112px -144px}.ui-icon-pin-w{background-position:-128px -144px}.ui-icon-pin-s{background-position:-144px -144px}.ui-icon-play{background-position:0 -160px}.ui-icon-pause{background-position:-16px -160px}.ui-icon-seek-next{background-position:-32px -160px}.ui-icon-seek-prev{background-position:-48px -160px}.ui-icon-seek-end{background-position:-64px -160px}.ui-icon-seek-start{background-position:-80px -160px}.ui-icon-seek-first{background-position:-80px -160px}.ui-icon-stop{background-position:-96px -160px}.ui-icon-eject{background-position:-112px -160px}.ui-icon-volume-off{background-position:-128px -160px}.ui-icon-volume-on{background-position:-144px -160px}.ui-icon-power{background-position:0 -176px}.ui-icon-signal-diag{background-position:-16px -176px}.ui-icon-signal{background-position:-32px -176px}.ui-icon-battery-0{background-position:-48px -176px}.ui-icon-battery-1{background-position:-64px -176px}.ui-icon-battery-2{background-position:-80px -176px}.ui-icon-battery-3{background-position:-96px -176px}.ui-icon-circle-plus{background-position:0 -192px}.ui-icon-circle-minus{background-position:-16px -192px}.ui-icon-circle-close{background-position:-32px -192px}.ui-icon-circle-triangle-e{background-position:-48px -192px}.ui-icon-circle-triangle-s{background-position:-64px -192px}.ui-icon-circle-triangle-w{background-position:-80px -192px}.ui-icon-circle-triangle-n{background-position:-96px -192px}.ui-icon-circle-arrow-e{background-position:-112px -192px}.ui-icon-circle-arrow-s{background-position:-128px -192px}.ui-icon-circle-arrow-w{background-position:-144px -192px}.ui-icon-circle-arrow-n{background-position:-160px -192px}.ui-icon-circle-zoomin{background-position:-176px -192px}.ui-icon-circle-zoomout{background-position:-192px -192px}.ui-icon-circle-check{background-position:-208px -192px}.ui-icon-circlesmall-plus{background-position:0 -208px}.ui-icon-circlesmall-minus{background-position:-16px -208px}.ui-icon-circlesmall-close{background-position:-32px -208px}.ui-icon-squaresmall-plus{background-position:-48px -208px}.ui-icon-squaresmall-minus{background-position:-64px -208px}.ui-icon-squaresmall-close{background-position:-80px -208px}.ui-icon-grip-dotted-vertical{background-position:0 -224px}.ui-icon-grip-dotted-horizontal{background-position:-16px -224px}.ui-icon-grip-solid-vertical{background-position:-32px -224px}.ui-icon-grip-solid-horizontal{background-position:-48px -224px}.ui-icon-gripsmall-diagonal-se{background-position:-64px -224px}.ui-icon-grip-diagonal-se{background-position:-80px -224px}.ui-corner-all,.ui-corner-top,.ui-corner-left,.ui-corner-tl{border-top-left-radius:4px}.ui-corner-all,.ui-corner-top,.ui-corner-right,.ui-corner-tr{border-top-right-radius:4px}.ui-corner-all,.ui-corner-bottom,.ui-corner-left,.ui-corner-bl{border-bottom-left-radius:4px}.ui-corner-all,.ui-corner-bottom,.ui-corner-right,.ui-corner-br{border-bottom-right-radius:4px}.ui-widget-overlay{background:#aaa;opacity:.3;filter:Alpha(Opacity=30)}.ui-widget-shadow{-webkit-box-shadow:-8px -8px 8px #aaa;box-shadow:-8px -8px 8px #aaa}

.colorpicker {
	width: 356px;
	height: 176px;
	overflow: hidden;
	position: absolute;
	background: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_background.png);
	font-family: Arial, Helvetica, sans-serif;
	display: none;
}
.colorpicker_color {
	width: 150px;
	height: 150px;
	left: 14px;
	top: 13px;
	position: absolute;
	background: #f00;
	overflow: hidden;
	cursor: crosshair;
}
.colorpicker_color div {
	position: absolute;
	top: 0;
	left: 0;
	width: 150px;
	height: 150px;
	background: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_overlay.png);
}
.colorpicker_color div div {
	position: absolute;
	top: 0;
	left: 0;
	width: 11px;
	height: 11px;
	overflow: hidden;
	background: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_select.gif);
	margin: -5px 0 0 -5px;
}
.colorpicker_hue {
	position: absolute;
	top: 13px;
	left: 171px;
	width: 35px;
	height: 150px;
	cursor: n-resize;
}
.colorpicker_hue div {
	position: absolute;
	width: 35px;
	height: 9px;
	overflow: hidden;
	background: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_indic.gif) left top;
	margin: -4px 0 0 0;
	left: 0px;
}
.colorpicker_new_color {
	position: absolute;
	width: 60px;
	height: 30px;
	left: 213px;
	top: 13px;
	background: #f00;
}
.colorpicker_current_color {
	position: absolute;
	width: 60px;
	height: 30px;
	left: 283px;
	top: 13px;
	background: #f00;
}
.colorpicker input {
	background-color: transparent;
	border: 1px solid transparent;
	position: absolute;
	font-size: 10px;
	font-family: Arial, Helvetica, sans-serif;
	color: #898989;
	top: 4px;
	right: 11px;
	text-align: right;
	margin: 0;
	padding: 0;
	height: 11px;
}
.colorpicker_hex {
	position: absolute;
	width: 72px;
	height: 22px;
	background: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_hex.png) top;
	left: 212px;
	top: 142px;
}
.colorpicker_hex input {
	right: 6px;
}
.colorpicker_field {
	height: 22px;
	width: 62px;
	background-position: top;
	position: absolute;
}
.colorpicker_field span {
	position: absolute;
	width: 12px;
	height: 22px;
	overflow: hidden;
	top: 0;
	right: 0;
	cursor: n-resize;
}
.colorpicker_rgb_r {
	background-image: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_rgb_r.png);
	top: 52px;
	left: 212px;
}
.colorpicker_rgb_g {
	background-image: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_rgb_g.png);
	top: 82px;
	left: 212px;
}
.colorpicker_rgb_b {
	background-image: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_rgb_b.png);
	top: 112px;
	left: 212px;
}
.colorpicker_hsb_h {
	background-image: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_hsb_h.png);
	top: 52px;
	left: 282px;
}
.colorpicker_hsb_s {
	background-image: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_hsb_s.png);
	top: 82px;
	left: 282px;
}
.colorpicker_hsb_b {
	background-image: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_hsb_b.png);
	top: 112px;
	left: 282px;
}
.colorpicker_submit {
	position: absolute;
	width: 22px;
	height: 22px;
	background: url(https://sagecell.sagemath.org/static/colorpicker/images/colorpicker_submit.png) top;
	left: 322px;
	top: 142px;
	overflow: hidden;
}
.colorpicker_focus {
	background-position: center;
}
.colorpicker_hex.colorpicker_focus {
	background-position: bottom;
}
.colorpicker_submit.colorpicker_focus {
	background-position: bottom;
}
.colorpicker_slider {
	background-position: bottom;
}


/*!
 *  Font Awesome 3.0.2
 *  the iconic font designed for use with Twitter Bootstrap
 *  -------------------------------------------------------
 *  The full suite of pictographic icons, examples, and documentation
 *  can be found at: http://fortawesome.github.com/Font-Awesome/
 *
 *  License
 *  -------------------------------------------------------
 *  - The Font Awesome font is licensed under the SIL Open Font License - http://scripts.sil.org/OFL
 *  - Font Awesome CSS, LESS, and SASS files are licensed under the MIT License -
 *    http://opensource.org/licenses/mit-license.html
 *  - The Font Awesome pictograms are licensed under the CC BY 3.0 License - http://creativecommons.org/licenses/by/3.0/
 *  - Attribution is no longer required in Font Awesome 3.0, but much appreciated:
 *    "Font Awesome by Dave Gandy - http://fortawesome.github.com/Font-Awesome"

 *  Contact
 *  -------------------------------------------------------
 *  Email: dave@davegandy.com
 *  Twitter: http://twitter.com/fortaweso_me
 *  Work: Lead Product Designer @ http://kyruus.com
 */
@font-face {
  font-family: 'FontAwesomeSagecell';
  src: url('https://sagecell.sagemath.org/static/fontawesome-webfont.eot?v=3.0.1');
  src: url('https://sagecell.sagemath.org/static/fontawesome-webfont.eot?#iefix&v=3.0.1') format('embedded-opentype'),
    url('https://sagecell.sagemath.org/static/fontawesome-webfont.woff?v=3.0.1') format('woff'),
    url('https://sagecell.sagemath.org/static/fontawesome-webfont.ttf?v=3.0.1') format('truetype');
  font-weight: normal;
  font-style: normal;
}
/*  Font Awesome styles
    ------------------------------------------------------- */
.sagecell [class^="sagecell_icon-"],
.sagecell [class*=" sagecell_icon-"] {
  font-family: FontAwesomeSagecell;
  font-weight: normal;
  font-style: normal;
  text-decoration: inherit;
  -webkit-font-smoothing: antialiased;

  font-size: 125%;
  background: transparent;
  /* sprites.less reset */
  display: inline;
  width: auto;
  height: auto;
  line-height: normal;
  vertical-align: baseline;
  margin-top: 0;
}
.sagecell [class^="sagecell_icon-"]:before,
.sagecell [class*=" sagecell_icon-"]:before {
  text-decoration: inherit;
  display: inline-block;
  speak: none;
}
.sagecell .sagecell_icon-resize-full:before		{ content: "\f021"; }
.sagecell .sagecell_icon-resize-small:before		{ content: "\f022"; }


.sagecell_messages div {
    margin-bottom: 12pt;
}

.sagecell_sliderControl {
    max-width: 40em;
    margin-right: 1.0em;
    margin-left: 0.5em;
}

.sagecell_multiSliderContainer {
    margin-left: 1.0em;
    whitespace: nowrap;
}

.sagecell_multiSliderControl {
    display: inline-block;
    margin-right: 0.5em;
    margin-left: 0.5em;
    margin-top: 0.25em;
}

.sagecell_colorSelector {
    display: inline-block;
    width: 2em;
    height: 2em;
    border: 2px solid gray;
    border-radius: 3px;
    padding: 1px;
    cursor: pointer;
    vertical-align: middle;
}

.sagecell .error, .sagecell .stderr {
    color: red;
}

.sagecell .colorpicker {
    z-index: 10;
}

.sagecell .CodeMirror {
    border: 1px solid;
    height: auto;
}

.sagecell .CodeMirror-scroll {
    min-height: 3em;
    max-height: 14em;
}

.sagecell .CodeMirror-fullscreen .CodeMirror-scroll {
    max-height: none;
}

.sagecell .CodeMirror-hints {
    padding-right: 10px;
}

.sagecell .ui-dialog-content {
    font-size: 80%;
}

.sagecell_input {
    overflow: hidden;
    padding-right: 2px;
}

.sagecell button.sagecell_evalButton {
    cursor: default;
}

.sagecell_output {
    padding-right: 2px;
}

.sagecell_output_elements {
    margin-top: 0.5em;
}

.sagecell_permalink {
    padding-right: 5px;
    text-align: right;
    position: relative;
}

.sagecell_permalink_result {
    position: absolute;
    padding-right: 5px;
    text-align: right;
    right: 3px;
    z-index: 100;
    background-color: white;
    border: 1px solid black;
    border-radius: 3px;
    padding: 5px;
}

.sagecell_permalink_result a:not([href]) {
    color: gray;
    text-decoration: none;
    cursor: default;
}

.sagecell_permalink_result img {
    display: inline-block;
    background-color: lightgray;
    width: 200px;
    height: 200px;
}

.sagecell_sessionContainer {
    position: relative;
}

.sagecell_sessionContainer:after {
    display: table;
    content: " ";
    clear: both;
}

.sagecell_sessionOutput {
    position: relative;
    border: 2px solid;
    padding: 5px;
    margin-top: 2px;
    min-height: 16px;
    overflow-x: auto;
}

.sagecell_sessionOutput pre {
    margin: 0px;
}

.sagecell_sessionOutput.sagecell_active {
    border-color: #080;
}

.sagecell_poweredBy {
    float: right;
    padding: 3px 5px 5px 0px;
    text-align: right;
    overflow: visible;
    font-size: 80%;
}

.sagecell_poweredBy img {
    vertical-align: -5px;
    border-style: none;
    text-decoration: none;
}

.sagecell_spinner {
    position: absolute;
    right: 5px;
    top: 5px;
}

.sagecell_sessionFiles {
    width: 80%;
    padding-bottom: 1.0em;
}

.sagecell_interactContainer {
    position: relative;
    padding: 15px 5px 5px 5px;
    border: 2px solid lightgray;
    margin-bottom: 2px;
}

.sagecell_bookmarks {
    cursor: default;
}

.sagecell_interactContainer .sagecell_bookmarks {
    position: absolute;
    right: 3px;
    top: 3px;
}

.sagecell_bookmarks div {
    display: inline-block;
    height: 1.5em;
    vertical-align: bottom;
    overflow-y: hidden;
    font-size: 1.3em;
    font-family: Arial;
    color: #8c8c8c;
    transition: color 0.25s ease-out;
}

.sagecell_bookmarks div:first-child {
    color: transparent;
    visibility: hidden;
}

.sagecell_bookmarks div:last-child {
    margin-left: 10px;
    width: 1.5em;
}

.sagecell_bookmarks div:last-child:before {
    display: inline-block;
    content: "\2605";
}

.sagecell_bookmarks div.sagecell_export {
    visibility: visible;
    transition: color 0.5s 0.5s;
    color: inherit;
    cursor: pointer;
}

.sagecell_export:before {
    content: "\22ef";
}

.sagecell_bookmarks input {
    border: 1px solid black;
    border-radius: 3px;
    vertical-align: 50%;
    background-color: rgba(0, 0, 0, 0.1);
    font-family: monospace;
}

.sagecell_sessionOutput.sagecell_active .sagecell_bookmarks div:last-child:hover {
    color: #ffa500;
    cursor: pointer;
}

.sagecell_bookmarks_list.ui-menu {
    display: inline-block;
    min-width: 15em;
    cursor: default;
    z-index: 99;
}

.sagecell_bookmarks_list.ui-menu li.ui-state-disabled {
    opacity: 1;
    margin: 0px;
}

.sagecell_bookmarks_list > li > a > input,
.sagecell_bookmarks_list > li > a > div:first-child {
    display: inline-block;
    width: 85%;
    border: none;
    border-radius: 3px;
}

.sagecell_bookmarks_list > li > a > div:last-child {
    float: right;
    width: 1.5em;
    text-align: center;
    font-weight: bold;
    color: #777;
    cursor: pointer;
    transition: 0.25s color;
}

.sagecell_bookmarks_list > li:not(:last-child):not(:hover) > a > div:last-child {
     display: none;
}

.sagecell_bookmarks_list > li > a > div:last-child:hover {
    color: darkred;
}

.sagecell_bookmarks_list > li > a > div:last-child:before {
    content: "\2716";
}

.sagecell_bookmarks_list > li:last-child > a > div:hover {
    color: darkblue;
}

.sagecell_bookmarks_list > li:last-child > a > div:before {
    content: "+";
}

.sagecell_interactOutput {
    padding: 10px;
    padding-right: 2em;
    padding-left: 2em;
    overflow-x: auto;
    vertical-align: top;
}

.sagecell_interactValueBox {
    border: 1px solid transparent;
    background-color: transparent;
    vertical-align: baseline;
    font-family: monospace;  /* Required since dynamic input box size is determined by monospaced fonts */
    max-width: 10ex;
}

.sagecell_interactValueBox:hover {
    border-color: lightgray;
}

.sagecell_interactValueBox:focus {
    border-color: gray;
}

.sagecell_interactControlCell {
    display: inline-table;
    vertical-align: top;
    min-width: 200px;
}

.sagecell_interactControlLabel {
    display: table-cell;
    text-align: right !important;
    vertical-align: middle !important;
    padding-right: 0.5ex !important;
    padding-top: 0.6ex !important;
    padding-bottom: 0.6ex !important;
    min-width: 10ex;
    overflow-wrap: break-word;
}

.sagecell_interactControl {
    display: table-cell;
    width: 100%;
    height: 100%;
    vertical-align: middle;
}

.sagecell_interactContainer .sagecell_interactControl {
    /* only pad if we are setting up the layout.  If we have an inline control
       don't pad, but leave it up to the user */
    padding: 1ex;
}

.sagecell_sliderContainer {
    display: table;
    width: 100%;
    height: 100%;
    max-width: 700px;
    min-width: 200px;
}

.sagecell_sliderContainer > div:first-child {
    display: table-cell;
    width: 100%;
    vertical-align: middle;
}

.sagecell_sliderContainer > div:first-child + div {
    display: table-cell;
    min-width: 11ex;
}

.sagecell_interactTextbox[size="0"] {
    width: 100%;
    max-width: 40em;
}

.sagecell_dirtyControl {
    box-shadow: 0px 0px 2px 1px #c00;
    transition: box-shadow 1s;
    border-radius: 2px;
}

.sagecell_commands, .sagecell .ui-widget .sagecell_commands {
    width: 100%;
    height: 200px;
    border: 1px solid;
    font-family: monospace;
    font-size: 10pt;
}

.sagecell_editor {
    margin-bottom: 8px;
}

.sagecell_options {
    display: inline-block;
    margin-right: 2px;
    float: right;
    text-align: right;
    font-size: 80%;
}

.sagecell_fullScreen {
    position: absolute;
    right: 1.5em;
    top: 0.5em;
    z-index: 10;
    padding: 2px;
    color: rgb(128,128,128);
}

.sagecell_editor div.ui-accordion-content.ui-helper-reset {
    padding: 1em 0.5em;
    font-size: 90.9%;
}

.sagecell_advancedFrame {
    border-radius: 5px;
    background-color: #ddf;
    border: 1px solid;
    padding: 0.2em;
    display: inline-block;
    width: 300px;
    overflow: hidden;
    margin-left: 3em;
    margin-bottom: 1em;
    vertical-align: top;
}

.sagecell_advancedTitle {
    cursor: default;
}

.sagecell_advancedFields {
    border: 1px solid gray;
    background-color: white;
    padding: 5px;
}

.sagecell_fileList li {
    list-style: none;
    position: relative;
}

.sagecell_fileName {
    position: relative;
    display: inline-block;
    white-space: nowrap;
    width: 230px;
    overflow: hidden;
    text-overflow: ellipsis;
}

.sagecell_deleteButton {
    position: absolute;
    left: -1.2em;
    cursor: pointer;
    margin-right: 5px;
}

.sagecell_deleteButton:hover {
    color: red;
}

.sagecell_deleteButton:active {
    color: darkred;
}

.sagecell_deleteButton:before {
    content: "\2716";
}

.sagecell table.table_form tr.row-a {
    background-color: #f8f8f8;
}

.sagecell table.table_form tr.row-b {
    background-color: #efefef;
}

.sagecell table.table_form td {
    padding: 5px 15px;
    color: #00a;
}

.sagecell .sagecell-templates .hide {
 display: none;   
}

.sagecell .sagecell-templates .pull-right {
    float: right;
}

.sagecell .sagecell-templates .lighten {
    color: gray;
}

/* These colors are constructed in
 * notebook/static/notebook/less/ansicolors.less
 * but were copied from
 * notebook/static/style/ipython.min.css
 * and processed in Python via
 * replace("{\n  ", "{").replace("\n}", "}").replace("\n.","\n.sagecell .")
 */
.sagecell .ansi-black-fg {color: #3E424D;}
.sagecell .ansi-black-bg {background-color: #3E424D;}
.sagecell .ansi-black-intense-fg {color: #282C36;}
.sagecell .ansi-black-intense-bg {background-color: #282C36;}
.sagecell .ansi-red-fg {color: #E75C58;}
.sagecell .ansi-red-bg {background-color: #E75C58;}
.sagecell .ansi-red-intense-fg {color: #B22B31;}
.sagecell .ansi-red-intense-bg {background-color: #B22B31;}
.sagecell .ansi-green-fg {color: #00A250;}
.sagecell .ansi-green-bg {background-color: #00A250;}
.sagecell .ansi-green-intense-fg {color: #007427;}
.sagecell .ansi-green-intense-bg {background-color: #007427;}
.sagecell .ansi-yellow-fg {color: #DDB62B;}
.sagecell .ansi-yellow-bg {background-color: #DDB62B;}
.sagecell .ansi-yellow-intense-fg {color: #B27D12;}
.sagecell .ansi-yellow-intense-bg {background-color: #B27D12;}
.sagecell .ansi-blue-fg {color: #208FFB;}
.sagecell .ansi-blue-bg {background-color: #208FFB;}
.sagecell .ansi-blue-intense-fg {color: #0065CA;}
.sagecell .ansi-blue-intense-bg {background-color: #0065CA;}
.sagecell .ansi-magenta-fg {color: #D160C4;}
.sagecell .ansi-magenta-bg {background-color: #D160C4;}
.sagecell .ansi-magenta-intense-fg {color: #A03196;}
.sagecell .ansi-magenta-intense-bg {background-color: #A03196;}
.sagecell .ansi-cyan-fg {color: #60C6C8;}
.sagecell .ansi-cyan-bg {background-color: #60C6C8;}
.sagecell .ansi-cyan-intense-fg {color: #258F8F;}
.sagecell .ansi-cyan-intense-bg {background-color: #258F8F;}
.sagecell .ansi-white-fg {color: #C5C1B4;}
.sagecell .ansi-white-bg {background-color: #C5C1B4;}
.sagecell .ansi-white-intense-fg {color: #A1A6B2;}
.sagecell .ansi-white-intense-bg {background-color: #A1A6B2;}
.sagecell .ansi-default-inverse-fg {color: #FFFFFF;}
.sagecell .ansi-default-inverse-bg {background-color: #000000;}
.sagecell .ansi-bold {font-weight: bold;}
.sagecell .ansi-underline {text-decoration: underline;}
</style><script type="text/javascript" async="" src="https://www.googletagmanager.com/gtag/js?id=G-JMYC2V6077&amp;cx=c&amp;_slc=1"></script><script src="https://connect.facebook.net/en_US/sdk.js?hash=3a4295d1065f4cc5aeb3244546f17b95" async="" crossorigin="anonymous"></script><script id="facebook-jssdk" src="//connect.facebook.net/en_US/sdk.js#xfbml=1&amp;version=v2.10&amp;appId=1581769695449208"></script><script async="" src="//www.google-analytics.com/analytics.js"></script><script type="text/javascript" async="" src="https://ssl.google-analytics.com/ga.js"></script><script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/0.6.0/p5.js"></script><style type="text/css" id="operaUserStyle"></style><link rel="stylesheet" type="text/css" href="https://sagecell.sagemath.org/static/sagecell_embed.css"><script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/seedrandom/2.4.3/seedrandom.min.js"></script><script type="text/javascript" src="https://sagecell.sagemath.org/static/embedded_sagecell.js"></script><script type="text/javascript" src="/public/v1.8.1/javascripts/main.min.js"></script><style type="text/css">.MathJax_Preview {color: #888}
#MathJax_Message {position: fixed; left: 1em; bottom: 1.5em; background-color: #E6E6E6; border: 1px solid #959595; margin: 0px; padding: 2px 8px; z-index: 102; color: black; font-size: 80%; width: auto; white-space: nowrap}
#MathJax_MSIE_Frame {position: absolute; top: 0; left: 0; width: 0px; z-index: 101; border: 0px; margin: 0px; padding: 0px}
.MathJax_Error {color: #CC0000; font-style: italic}
</style><link rel="apple-touch-icon" sizes="114x114" href="/public/v1.8.1/images/icons/favicon-114x114.png"><link rel="apple-touch-icon" sizes="72x72" href="/public/v1.8.1/images/icons/favicon-72x72.png"><link rel="apple-touch-icon" sizes="57x57" href="/public/v1.8.1/images/icons/favicon-57x57.png"><link rel="shortcut icon" type="image/x-icon" href="/favicon.ico"><script type="text/javascript">window.define = function(dependencies,callback) {
  var currentScript = document.currentScript || (function() {
    var scripts = document.getElementsByTagName('script');
    return scripts[scripts.length - 1];
  })();
  var targetId = currentScript.getAttribute('data-target');
  var parameters = currentScript.getAttribute('data-argument');

  (window.interactives = window.interactives || []).push({dependencies: dependencies, callback: callback, targetId: targetId, parameters: parameters});
};
</script><script type="text/javascript">(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','//www.google-analytics.com/analytics.js','ga');

ga('create', 'UA-47676415-1', 'osu.edu');
ga('send', 'pageview');
</script><script type="text/javascript">// The versions to warn about
var $buoop = {vs:{i:13,f:-4,o:-4,s:8,c:-4},unsecure:true,api:4}; 
function $buo_f(){ 
  var e = document.createElement("script"); 
  e.src = "//browser-update.org/update.min.js"; 
  document.body.appendChild(e);
};
try {document.addEventListener("DOMContentLoaded", $buo_f,false)}
catch(e){window.attachEvent("onload", $buo_f)}
</script><style type="text/css">.affix-top { top: 0px; }</style><style type="text/css">:root img[width="728"][height="90"], :root [href="https://adstub.net/cina777/"], :root [href="https://adstub.net/arab777/"], :root [href="https://adstub.net/ratu89/"], :root [href="https://adstub.net/judi89/"], :root [href^="//mage98rquewz.com/"], :root [href^="//x4pollyxxpush.com/"], :root div.content-showcase-itru-sufficient-2d:not(.q7d5z1l):not(.x9a7b3k), :root span[id^="ezoic-pub-ad-placeholder-"], :root ins.adsbygoogle[data-ad-slot], :root ins.adsbygoogle[data-ad-client], :root img[src^="https://s-img.adskeeper.com/"], :root guj-ad, :root gpt-ad, :root div[id^="zergnet-widget"], :root div[id^="vuukle-ad-"], :root div[id^="taboola-stream-"], :root div[id^="sticky_ad_"], :root div[id^="st"][style^="z-index: 999999999;"], :root div[id^="gpt_ad_"], :root div[id^="ezoic-pub-ad-"], :root div[id^="dfp-ad-"], :root div[id^="crt-"][style], :root div[id^="adspot-"], :root div[id^="adrotate_widgets-"], :root ps-connatix-module, :root div[id^="ad_position_"], :root div[id^="ad-div-"], :root div[id*="ScriptRoot"], :root div[id*="MarketGid"], :root [href="https://adstub.net/rusia777/"], :root div[data-id-advertdfpconf], :root div[data-dfp-id], :root hl-adsense, :root div[data-contentexchange-widget], :root div[data-alias="300x250 Ad 2"], :root div[data-adzone], :root div[data-adunit-path], :root div[data-adname], :root div[data-ad-targeting], :root div[data-ad-region], :root div[data-ad-placeholder], :root div[aria-label="Ads"], :root display-ads, :root display-ad-component, :root atf-ad-slot, :root aside[id^="adrotate_widgets-"], :root amp-fx-flying-carpet, :root amp-embed[type="taboola"], :root amp-connatix-player, :root amp-ad-custom, :root amp-ad, :root div[id^="google_dfp_"], :root ad-slot, :root ad-shield-ads, :root a[style="width:100%;height:100%;z-index:10000000000000000;position:absolute;top:0;left:0;"], :root a[onmousedown^="this.href='https://paid.outbrain.com/network/redir?"] + .ob_source, :root a[href^="https://xbet-4.com/"], :root div[id^="ad-position-"], :root a[href^="https://www.toprevenuegate.com/"], :root a[href^="https://www.purevpn.com/"][href*="&utm_source=aff-"], :root a[href^="https://www.privateinternetaccess.com/"] > img, :root a[href^="https://www.onlineusershielder.com/"], :root a[href^="https://financeads.net/tc.php?"], :root a[href^="https://www.mrskin.com/tour"], :root a[href^="https://www.infowarsstore.com/"] > img, :root a[href^="https://www.highperformancecpmgate.com/"], :root a[href^="https://www.highcpmrevenuenetwork.com/"], :root a[href^="https://www.get-express-vpn.com/offer/"], :root a[href^="https://lnkxt.bannerator.com/"], :root a[href^="https://www.geekbuying.com/dynamic-ads/"], :root a[href^="https://www.financeads.net/tc.php?"], :root a[href^="https://www.effectiveratecpm.com/"], :root [href^="https://www.herbanomic.com/"] > img, :root a[href^="https://maymooth-stopic.com/"], :root a[href^="https://www.dql2clk.com/"], :root a[href^="https://www.nutaku.net/signup/landing/"], :root a[href^="https://www.dating-finder.com/signup/?ai_d="], :root a[href^="https://explore-site.com/"], :root a[href^="https://www.brazzersnetwork.com/landing/"], :root a[href^="https://www.adxsrve.com/"], :root [data-template-type="nativead"], :root a[href^="https://www.endorico.com/Smartlink/"], :root a[href^="https://www.adultempire.com/"][href*="?partner_id="], :root a[href^="https://voluum.prom-xcams.com/"], :root a[href^="https://twinrdsyte.com/"], :root div[data-type="_mgwidget"]:not(.eyeo), :root a[href^="https://twinrdsrv.com/"], :root a[href^="https://trk.nfl-online-streams.club/"], :root a[href^="https://tracking.avapartner.com/"], :root a[href^="https://track.wg-aff.com"], :root a[href^="https://track.ultravpn.com/"], :root a[href^="https://track.afcpatrk.com/"], :root a[href^="https://torguard.net/aff.php"] > img, :root [data-identity="adhesive-ad"], :root a[href^="https://tc.tradetracker.net/"] > img, :root a[href^="https://tatrck.com/"], :root a[href^="https://click.candyoffers.com/"], :root [href^="https://zstacklife.com/"] img, :root a[href^="https://t.aslnk.link/"], :root a[href^="https://t.adating.link/"], :root a[href^="https://go.trackitalltheway.com/"], :root [href^="https://track.fiverr.com/visit/"] > img, :root a[href^="https://syndication.exoclick.com/"], :root a[href^="https://syndication.dynsrvtbg.com/"], :root div[data-alias="300x250 Ad 1"], :root a[href^="https://syndicate.contentsserved.com/"], :root a[href^="https://svb-analytics.trackerrr.com/"], :root [href="https://adstub.net/gaza88/"], :root a[href^="https://ad.doubleclick.net/"], :root a[href^="https://static.fleshlight.com/images/banners/"], :root a[href^="https://slkmis.com/"], :root bottomadblock, :root a[href^="https://s.zlinkd.com/"], :root a[href^="https://s.zlink3.com/"], :root a[href^="https://www.mrskin.com/account/"], :root a[href^="https://s.optzsrv.com/"], :root a[href^="https://s.ma3ion.com/"], :root a[href^="https://s.eunow4u.com/"], :root #kt_player > div[style$="display: block;"][style*="inset: 0px;"], :root [href$="/sexdating.php"], :root a[href^="https://quotationfirearmrevision.com/"], :root a[href^="https://pubads.g.doubleclick.net/"], :root a[href^="https://prf.hn/click/"][href*="/camref:"] > img, :root a[href^="https://www.dating-finder.com/?ai_d="], :root a[href^="https://serve.awmdelivery.com/"], :root a[href^="https://prf.hn/click/"][href*="/adref:"] > img, :root app-ad, :root [href^="https://ap.octopuspop.com/click/"] > img, :root a[href^="https://postback1win.com/"], :root a[href^="https://mmwebhandler.aff-online.com/"], :root a[href^="https://www.bet365.com/"][href*="affiliate="], :root a[href^="https://pb-track.com/"], :root a[href^="https://pb-front.com/"], :root a[href^="https://paid.outbrain.com/network/redir?"], :root a[href^="https://streamate.com/landing/click/"], :root div[class^="Adstyled__AdWrapper-"], :root a[href^="https://osfultrbriolenai.info/"], :root a[href^="https://upsups.click/"], :root a[href^="https://ndt5.net/"], :root a[href^="https://natour.naughtyamerica.com/track/"], :root a[href^="https://mediaserver.entainpartners.com/renderBanner.do?"], :root a[href^="https://m.do.co/c/"] > img, :root a[href^="https://lead1.pl/"], :root a[href^="https://landing.brazzersnetwork.com/"], :root a[href^="https://join.virtuallust3d.com/"], :root a[href^="https://kiksajex.com/"], :root a[href^="https://juicyads.in/"], :root a[href^="https://snowdayonline.xyz/"], :root a[href^="https://mediaserver.gvcaffiliates.com/renderBanner.do?"], :root a[href^="https://join.dreamsexworld.com/"], :root a[href^="https://jaxofuna.com/"], :root a[href^="https://italarizege.xyz/"], :root a[href^="https://iqbroker.com/"][href*="?aff="], :root a[href^="https://identicaldrench.com/"], :root a[href^="https://hot-growngames.life/"], :root a[href^="https://helmethomicidal.com/"], :root a[href^="https://golinks.work/"], :root ark-top-ad, :root a[href^="https://s.zlinkn.com/"], :root a[href^="https://go.xxxvjmp.com/"], :root [class^="tile-picker__CitrusBannerContainer-sc-"], :root a[href^="https://go.xxxiijmp.com"], :root a[href^="https://go.xtbaffiliates.com/"], :root [data-role="tile-ads-module"], :root a[href^="https://go.xlviirdr.com"], :root div[class$="-adlabel"], :root a[href^="https://go.xlviiirdr.com"], :root a[href^="https://ismlks.com/"], :root [href^="https://www.mypillow.com/"] > img, :root a[href^="https://go.xlirdr.com"], :root [data-css-class="dfp-inarticle"], :root a[href^="https://l.hyenadata.com/"], :root a[href^="https://go.tmrjmp.com"], :root a[href^="https://zirdough.net/"], :root a[href^="https://s.deltraff.com/"], :root a[href^="https://go.markets.com/visit/?bta="], :root a[href^="https://billing.purevpn.com/aff.php"] > img, :root a[href^="https://go.hpyrdr.com/"], :root a[href^="https://lijavaxa.com/"], :root a[href^="https://go.goaserv.com/"], :root a[href^="https://t.hrtye.com/"], :root a[href^="https://go.etoro.com/"] > img, :root a[href^="https://go.dmzjmp.com"], :root a[href^="https://www.bang.com/?aff="], :root #mgb-container > #mgb, :root a[href^="https://go.admjmp.com"], :root a[href^="https://ak.stikroltiltoowi.net/"], :root a[href^="https://get.surfshark.net/aff_c?"][href*="&aff_id="] > img, :root a[href^="https://www.adskeeper.com"], :root a[data-redirect^="https://paid.outbrain.com/network/redir?"], :root [href^="https://clicks.affstrack.com/"] > img, :root a[href^="https://ak.hauchiwu.com/"], :root a[href^="https://engine.phn.doublepimp.com/"], :root a[href^="https://engine.blueistheneworanges.com/"], :root a[href^="https://drumskilxoa.click/"], :root a[href^="https://dl-protect.net/"], :root a[href*=".foxqck.com/"], :root a[href^="https://ctosrd.com/"], :root div[id*="ScriptRoot"]:not(.eyeo), :root a[href^="https://clixtrac.com/"], :root [href^="https://noqreport.com/"] > img, :root a[href^="https://clicks.pipaffiliates.com/"], :root app-advertisement, :root a[href^="https://getmatchedlocally.com/"], :root a[href^="https://clickins.slixa.com/"], :root a[href^="https://datewhisper.life/"], :root a[href^="https://get-link.xyz/"], :root a[href^="https://click.linksynergy.com/fs-bin/"] > img, :root a[href^="https://combodef.com/"], :root a[href^="https://click.hoolig.app/"], :root a[href^="https://click.ggpickaff.com/"], :root a[href^="https://track.totalav.com/"], :root a[href^="https://ctrdwm.com/"], :root img[src^="https://images.purevpnaffiliates.com"], :root a[href^="https://porntubemate.com/"], :root a[href^="https://clickadilla.com/"], :root a[href^="https://click.dtiserv2.com/"], :root a[href^="https://go.xlvirdr.com"], :root a[href^="http://www.iyalc.com/"], :root a[href^="https://claring-loccelkin.com/"], :root a[href^="https://bongacams2.com/track?"], :root a[href^="https://t.ajrkm1.com/"], :root a[href^="https://bongacams10.com/track?"], :root a[href^="https://www.sheetmusicplus.com/"][href*="?aff_id="], :root a[href^="https://bngpt.com/"], :root a[href^="https://black77854.com/"], :root a[href^="https://rixofa.com/"], :root #ads[style^="position: absolute; z-index: 30; width: 100%; height"], :root a[href^="https://disobediencecalculatormaiden.com/"], :root a[href^="https://best-experience-cool.com/"], :root a[href^="https://banners.livepartners.com/"], :root a[href^="https://myclick-2.com/"], :root a[href^="https://sexynearme.com/"], :root a[href^="https://baipahanoop.net/"], :root a[href^="http://revolvemockerycopper.com/"], :root a[href^="https://awptjmp.com/"], :root a[href^="https://join.sexworld3d.com/track/"], :root a[href^="https://aweptjmp.com/"], :root a[href^="https://ausoafab.net/"], :root a[href^="https://adclick.g.doubleclick.net/"], :root a[href^="https://aj1070.online/"], :root a[href^="https://bc.game/"], :root a[href^="https://ak.oalsauwy.net/"], :root a[href^="https://a.bestcontentoperation.top/"], :root a[href^="https://adultfriendfinder.com/go/"], :root a[href^="https://ads.planetwin365affiliate.com/"], :root a[href^="https://ads.leovegas.com/"], :root .nya-slot[style], :root a[href^="https://a.bestcontentweb.top/"], :root a[href^="https://a2.adform.net/"], :root a[href^="https://a.candyai.love/"], :root a[href^="https://playnano.online/offerwalls/?ref="], :root a[href^="https://a.adtng.com/"], :root .banner-img > .pbl, :root [data-m-ad-id], :root a[href^="https://a-ads.com/"], :root [id^="ad_slider"], :root a[href^="https://click.ggpickyaff.com/"], :root broadstreet-zone-container, :root a[href^="https://ak.psaltauw.net/"], :root a[href^="https://1winpb.com/"], :root div[id^="rc-widget-"], :root a[href^="http://eslp34af.click/"], :root a[href^="https://turnstileunavailablesite.com/"], :root a[href^="https://chaturbate.com/in/?"], :root a[href^="https://prf.hn/click/"][href*="/creativeref:"] > img, :root a[href*="&maxads="], :root a[href^="http://www.adultempire.com/unlimited/promo?"][href*="&partner_id="], :root a[href^="https://1betandgonow.com/"], :root a[href^="https://eergortu.net/"], :root div[id^="optidigital-adslot"], :root a[href^="https://123-stream.org/"], :root a[href^="https://in.rabbtrk.com/"], :root a[href^="http://www.h4trck.com/"], :root a[href^="http://www.friendlyduck.com/AF_"], :root a[href^="https://go.rmhfrtnd.com"], :root a[href^="https://allhost.shop/aff.php?"], :root [data-dynamic-ads], :root a[href^="http://vnte9urn.click/"], :root a[href^="http://troopsassistedstupidity.com/"], :root a[href^="http://trk.globwo.online/"], :root a[href^="https://random-affiliate.atimaze.com/"], :root a-ad, :root a[href^="https://offhandpump.com/"], :root a[href^="http://stickingrepute.com/"], :root #slashboxes > .deals-rail, :root a[href^="http://roadcontagion.com/"], :root a[href^="http://premonitioninventdisagree.com/"], :root a[href^="http://cam4com.go2cloud.org/aff_c?"], :root a[href^="https://ads.betfair.com/redirect.aspx?"], :root [href^="https://www.mypatriotsupply.com/"] > img, :root a[href^="https://trk.softonixs.xyz/"], :root [data-advadstrackid], :root a[href^="http://muzzlematrix.com/"], :root a[href^="https://track.adform.net/"], :root a[href^="http://avthelkp.net/"], :root a[href^="https://a.medfoodhome.com/"], :root a[href^="https://engine.flixtrial.com/"], :root [data-type="ad-vertical"], :root [data-taboola-options], :root a[href^="http://annulmentequitycereals.com/"], :root a[href^="//startgaming.net/tienda/" i], :root a[href^="https://join.virtualtaboo.com/track/"], :root [id^="ad_sky"], :root a[href^="http://coefficienttolerategravel.com/"], :root a[href^="https://a.medfoodsafety.com/"], :root a[href^="//go.eabids.com/"], :root a[href^="//ejitsirdosha.net/"], :root a[href^=" https://www.friendlyduck.com/AF_"], :root [data-cl-spot-id], :root a[href*="/jump/next.php?r="], :root a[href^="https://go.rmishe.com/"], :root [href^="https://ilovemyfreedoms.com/landing-"], :root a[href^="https://syndication.optimizesrv.com/"], :root a[href*="//daichoho.com/"], :root a[href^="https://go.nordvpn.net/aff"] > img, :root .\[\&_\.gdprAdTransparencyCogWheelButton\]\:\!pjra-z-\[5\], :root [href^="http://clicks.totemcash.com/"], :root a[href^="https://ad.zanox.com/ppc/"] > img, :root a[href^="https://lone-pack.com/"], :root [data-d-ad-id], :root a[href*=".engine.adglare.net/"], :root a[href^="https://t.ajrkm3.com/"], :root [href^="https://aads.com/campaigns/"], :root a[href^="//stighoazon.com/"], :root [href^="https://www.profitablegatecpm.com/"], :root div[id^="lazyad-"], :root a[href^="http://com-1.pro/"], :root a[href*=".cfm?domain="][href*="&fp="], :root [data-ad-name], :root a[href^="https://loboclick.com/"], :root a[data-url^="https://vulpix.bet/?ref="], :root a[href^="https://ab.advertiserurl.com/aff/"], :root a[data-oburl^="https://paid.outbrain.com/network/redir?"], :root a[href^="https://go.xlivrdr.com"], :root [onclick^="location.href='https://1337x.vpnonly.site/"], :root [name^="google_ads_iframe"], :root [id^="section-ad-banner"], :root a[href^="https://www.goldenfrog.com/vyprvpn?offer_id="][href*="&aff_id="], :root a[href*="//jjgirls.com/sex/Chaturbate"], :root [id^="ad-wrap-"], :root [href^="https://zone.gotrackier.com/"], :root a[href^="http://sarcasmadvisor.com/"], :root [href^="https://www.restoro.com/"], :root [href^="https://www.targetingpartner.com/"], :root .section-subheader > .section-hotel-prices-header, :root [href^="https://www.hostg.xyz/"] > img, :root a[href^="http://adultfriendfinder.com/go/"], :root a[href^="https://fastestvpn.com/lifetime-special-deal?a_aid="], :root a[href^="https://tour.mrskin.com/"], :root [href^="https://www.brighteonstore.com/products/"] img, :root citrus-ad-wrapper, :root a[href^="https://go.grinsbest.com/"], :root a[href^="https://vo2.qrlsx.com/"], :root [href^="https://www.avantlink.com/click.php"] img, :root a[href^="https://t.acam.link/"], :root a[href^="https://go.strpjmp.com/"], :root [href^="https://url.totaladblock.com/"], :root div[id^="div-ads-"], :root [href^="https://rapidgator.net/article/premium/ref/"], :root [href^="https://join.girlsoutwest.com/"], :root a[href^="https://activate-game.com/"], :root .scroll-fixable.rail-right > .deals-rail, :root [data-wpas-zoneid], :root a[href^="https://track.aftrk3.com/"], :root [href^="https://join3.bannedsextapes.com"], :root a[href^="https://bodelen.com/"], :root a[href*=".g2afse.com/"], :root div[id^="adngin-"], :root [data-rc-widget], :root span[data-ez-ph-id], :root [href^="https://track.aftrk1.com/"], :root [href^="https://join.playboyplus.com/track/"], :root a[href^="https://go.xxxijmp.com"], :root [href^="https://istlnkcl.com/"], :root a[href^="https://tm-offers.gamingadult.com/"], :root [href^="https://charmingdatings.life/"], :root [href="https://adstub.net/indo666/"], :root [href^="https://glersakr.com/"], :root a[href^="https://a.bestcontentfood.top/"], :root [href^="https://cpa.10kfreesilver.com/"], :root [data-id^="div-gpt-ad"], :root a[href^="https://tracker.loropartners.com/"], :root [href^="https://awbbjmp.com/"], :root div[ow-ad-unit-wrapper], :root a[data-href^="http://ads.trafficjunky.net/"], :root a[href^="http://partners.etoro.com/"], :root a[href^="https://www.friendlyduck.com/AF_"], :root [href^="https://ad1.adfarm1.adition.com/"], :root a[href^="https://bngprm.com/"], :root [href^="https://shiftnetwork.infusionsoft.com/go/"] > img, :root a[href^="https://go.bushheel.com/"], :root a[href^="https://ctjdwm.com/"], :root a[href^="https://camfapr.com/landing/click/"], :root div[data-ad-wrapper], :root .gnt_em_vp_c[data-g-s="vp_dk"], :root [href="//sexcams.plus/"], :root [href^="http://www.mypillow.com/"] > img, :root a[href^="https://promerycergerful.com/"], :root #kt_player > a[target="_blank"], :root a[href^="http://bongacams.com/track?"], :root [href^="http://mypillow.com/"] > img, :root [href="https://ourgoldguy.com/contact/"] img, :root .ob_container .item-container-obpd, :root [id^="div-gpt-ad"], :root a[href^="https://go.rmhfrtnd.com/"], :root [href="https://jdrucker.com/gold"] > img, :root a[href^="https://www.liquidfire.mobi/"], :root .grid > .container > #aside-promotion, :root DFP-AD, :root [href^="https://go.xlrdr.com"], :root a[href^="https://s.cant3am.com/"], :root [data-testid^="taboola-"], :root a[href^="https://track.1234sd123.com/"], :root zeus-ad, :root [data-testid="prism-ad-wrapper"], :root [href^="https://ad.admitad.com/"], :root [href^="https://mypillow.com/"] > img, :root [data-testid="ad_testID"], :root [href^="https://antiagingbed.com/discount/"] > img, :root a[href*=".adsrv.eacdn.com/"], :root [href^="https://optimizedelite.com/"] > img, :root [data-name="adaptiveConstructorAd"], :root a[href^="https://go.cmtaffiliates.com/"], :root [data-testid="adBanner-wrapper"], :root [href^="https://mylead.global/stl/"] > img, :root [href^="https://mypatriotsupply.com/"] > img, :root a[href^="https://go.hpyjmp.com"], :root iframe[scrolling="no"][sandbox*="allow-popups allow-modals"][style^="width: 100%; height: 100%; border: none;"], :root [href^="https://mystore.com/"] > img, :root a[href^="https://81ac.xyz/"], :root [href^="https://wct.link/click?"], :root div[data-adunit], :root app-large-ad, :root [href^="https://turtlebids.irauctions.com/"] img, :root a[href^="https://believessway.com/"], :root div[class*="publift-widget-"]:has(.fuse-slot-sticky), :root a[href^="https://witnessjacket.com/"], :root [data-mobile-ad-id], :root [class^="amp-ad-"], :root a[href^="http://handgripvegetationhols.com/"], :root a[href^="https://go.bbrdbr.com"], :root a[href^="https://fc.lc/ref/"], :root [data-adshim], :root topadblock, :root a[href^="//s.zlinkd.com/"], :root #teaser1[style^="width:autopx;"], :root [href^="https://www.cloudways.com/en/?id"], :root [data-asg-ins], :root a[href^="https://gamingadlt.com/?offer="], :root [data-desktop-ad-id], :root [data-adbridg-ad-class], :root #teaser3[style^="width:autopx;"], :root [data-adblockkey], :root [data-block-type="ad"], :root [data-ad-width], :root [onclick*="content.ad/"], :root [data-ad-manager-id], :root AMP-AD, :root [data-ad-cls], :root [data-ez-name], :root a[href^="https://go.mnaspm.com/"], :root a[href^="https://service.bv-aff-trx.com/"], :root a[href^="https://6-partner.com/"], :root [class^="s2nPlayer"], :root a[href^="https://traffdaq.com/"], :root [data-testid="commercial-label-taboola"], :root [class^="div-gpt-ad"], :root a[href^="http://tc.tradetracker.net/"] > img, :root a[href^="https://www8.smartadserver.com/"], :root a[href^="https://pb-imc.com/"], :root [href^="https://affiliate.fastcomet.com/"] > img, :root [class^="adDisplay-module"], :root [data-freestar-ad][id], :root AD-SLOT, :root a[href^="https://www.googleadservices.com/pagead/aclk?"] > img, :root [data-ad-module], :root a[href^="https://go.skinstrip.net"][href*="?campaignId="], :root #teaser2[style^="width:autopx;"], :root [data-revive-zoneid], :root a[href^="https://losingoldfry.com/"], :root div[id^="div-gpt-"], :root a[href^="https://gml-grp.com/"], :root .ob_dual_right > .ob_ads_header ~ .odb_div, :root a[href^="https://cam4com.go2cloud.org/"], :root a[href^="http://li.blogtrottr.com/click?"], :root a[onmousedown^="this.href='https://paid.outbrain.com/network/redir?"], :root a[href^="https://t.ajump1.com/"], :root a[href^="https://go.xxxjmp.com"], :root #leader-companion > a[href], :root a[href^="https://wittered-mainging.com/"], :root #teaser3[style="width: 100%;text-align: center;display: scroll;position:fixed;bottom: 0;margin: 0 auto;z-index: 103;"], :root [href^="https://wwp.hoqodd.com/redirect-zone/"] { display: none !important; }</style><style type="text/css">#MathJax_About {position: fixed; left: 50%; width: auto; text-align: center; border: 3px outset; padding: 1em 2em; background-color: #DDDDDD; color: black; cursor: default; font-family: message-box; font-size: 120%; font-style: normal; text-indent: 0; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal; word-wrap: normal; white-space: nowrap; float: none; z-index: 201; border-radius: 15px; -webkit-border-radius: 15px; -moz-border-radius: 15px; -khtml-border-radius: 15px; box-shadow: 0px 10px 20px #808080; -webkit-box-shadow: 0px 10px 20px #808080; -moz-box-shadow: 0px 10px 20px #808080; -khtml-box-shadow: 0px 10px 20px #808080; filter: progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color='gray', Positive='true')}
#MathJax_About.MathJax_MousePost {outline: none}
.MathJax_Menu {position: absolute; background-color: white; color: black; width: auto; padding: 2px; border: 1px solid #CCCCCC; margin: 0; cursor: default; font: menu; text-align: left; text-indent: 0; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal; word-wrap: normal; white-space: nowrap; float: none; z-index: 201; box-shadow: 0px 10px 20px #808080; -webkit-box-shadow: 0px 10px 20px #808080; -moz-box-shadow: 0px 10px 20px #808080; -khtml-box-shadow: 0px 10px 20px #808080; filter: progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color='gray', Positive='true')}
.MathJax_MenuItem {padding: 2px 2em; background: transparent}
.MathJax_MenuArrow {position: absolute; right: .5em; padding-top: .25em; color: #666666; font-size: .75em}
.MathJax_MenuActive .MathJax_MenuArrow {color: white}
.MathJax_MenuArrow.RTL {left: .5em; right: auto}
.MathJax_MenuCheck {position: absolute; left: .7em}
.MathJax_MenuCheck.RTL {right: .7em; left: auto}
.MathJax_MenuRadioCheck {position: absolute; left: 1em}
.MathJax_MenuRadioCheck.RTL {right: 1em; left: auto}
.MathJax_MenuLabel {padding: 2px 2em 4px 1.33em; font-style: italic}
.MathJax_MenuRule {border-top: 1px solid #CCCCCC; margin: 4px 1px 0px}
.MathJax_MenuDisabled {color: GrayText}
.MathJax_MenuActive {background-color: Highlight; color: HighlightText}
.MathJax_MenuDisabled:focus, .MathJax_MenuLabel:focus {background-color: #E8E8E8}
.MathJax_ContextMenu:focus {outline: none}
.MathJax_ContextMenu .MathJax_MenuItem:focus {outline: none}
#MathJax_AboutClose {top: .2em; right: .2em}
.MathJax_Menu .MathJax_MenuClose {top: -10px; left: -10px}
.MathJax_MenuClose {position: absolute; cursor: pointer; display: inline-block; border: 2px solid #AAA; border-radius: 18px; -webkit-border-radius: 18px; -moz-border-radius: 18px; -khtml-border-radius: 18px; font-family: 'Courier New',Courier; font-size: 24px; color: #F0F0F0}
.MathJax_MenuClose span {display: block; background-color: #AAA; border: 1.5px solid; border-radius: 18px; -webkit-border-radius: 18px; -moz-border-radius: 18px; -khtml-border-radius: 18px; line-height: 0; padding: 8px 0 6px}
.MathJax_MenuClose:hover {color: white!important; border: 2px solid #CCC!important}
.MathJax_MenuClose:hover span {background-color: #CCC!important}
.MathJax_MenuClose:hover:focus {outline: none}
</style><style type="text/css">#MathJax_Zoom {position: absolute; background-color: #F0F0F0; overflow: auto; display: block; z-index: 301; padding: .5em; border: 1px solid black; margin: 0; font-weight: normal; font-style: normal; text-align: left; text-indent: 0; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal; word-wrap: normal; white-space: nowrap; float: none; -webkit-box-sizing: content-box; -moz-box-sizing: content-box; box-sizing: content-box; box-shadow: 5px 5px 15px #AAAAAA; -webkit-box-shadow: 5px 5px 15px #AAAAAA; -moz-box-shadow: 5px 5px 15px #AAAAAA; -khtml-box-shadow: 5px 5px 15px #AAAAAA; filter: progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color='gray', Positive='true')}
#MathJax_ZoomOverlay {position: absolute; left: 0; top: 0; z-index: 300; display: inline-block; width: 100%; height: 100%; border: 0; padding: 0; margin: 0; background-color: white; opacity: 0; filter: alpha(opacity=0)}
#MathJax_ZoomFrame {position: relative; display: inline-block; height: 0; width: 0}
#MathJax_ZoomEventTrap {position: absolute; left: 0; top: 0; z-index: 302; display: inline-block; border: 0; padding: 0; margin: 0; background-color: white; opacity: 0; filter: alpha(opacity=0)}
</style><style type="text/css">.MJX_Assistive_MathML {position: absolute!important; top: 0; left: 0; clip: rect(1px, 1px, 1px, 1px); padding: 1px 0 0 0!important; border: 0!important; height: 1px!important; width: 1px!important; overflow: hidden!important; display: block!important; -webkit-touch-callout: none; -webkit-user-select: none; -khtml-user-select: none; -moz-user-select: none; -ms-user-select: none; user-select: none}
.MJX_Assistive_MathML.MJX_Assistive_MathML_Block {width: 100%!important}
</style><style type="text/css">.MathJax_Hover_Frame {border-radius: .25em; -webkit-border-radius: .25em; -moz-border-radius: .25em; -khtml-border-radius: .25em; box-shadow: 0px 0px 15px #83A; -webkit-box-shadow: 0px 0px 15px #83A; -moz-box-shadow: 0px 0px 15px #83A; -khtml-box-shadow: 0px 0px 15px #83A; border: 1px solid #A6D ! important; display: inline-block; position: absolute}
.MathJax_Menu_Button .MathJax_Hover_Arrow {position: absolute; cursor: pointer; display: inline-block; border: 2px solid #AAA; border-radius: 4px; -webkit-border-radius: 4px; -moz-border-radius: 4px; -khtml-border-radius: 4px; font-family: 'Courier New',Courier; font-size: 9px; color: #F0F0F0}
.MathJax_Menu_Button .MathJax_Hover_Arrow span {display: block; background-color: #AAA; border: 1px solid; border-radius: 3px; line-height: 0; padding: 4px}
.MathJax_Hover_Arrow:hover {color: white!important; border: 2px solid #CCC!important}
.MathJax_Hover_Arrow:hover span {background-color: #CCC!important}
</style><style type="text/css" data-fbcssmodules="css:fb.css.base css:fb.css.dialog css:fb.css.iframewidget">.fb_hidden{position:absolute;top:-10000px;z-index:10001}.fb_reposition{overflow:hidden;position:relative}.fb_invisible{display:none}.fb_reset{background:none;border:0px;border-spacing:0;color:#000;cursor:auto;direction:ltr;font-family:lucida grande,tahoma,verdana,arial,sans-serif;font-size:11px;font-style:normal;font-variant:normal;font-weight:400;letter-spacing:normal;line-height:1;margin:0;overflow:visible;padding:0;text-align:left;text-decoration:none;text-indent:0;text-shadow:none;text-transform:none;visibility:visible;white-space:normal;word-spacing:normal}.fb_reset>div{overflow:hidden}@keyframes fb_transform{0%{opacity:0;transform:scale(.95)}to{opacity:1;transform:scale(1)}}.fb_animate{animation:fb_transform .3s forwards}

.fb_hidden{position:absolute;top:-10000px;z-index:10001}.fb_reposition{overflow:hidden;position:relative}.fb_invisible{display:none}.fb_reset{background:none;border:0px;border-spacing:0;color:#000;cursor:auto;direction:ltr;font-family:lucida grande,tahoma,verdana,arial,sans-serif;font-size:11px;font-style:normal;font-variant:normal;font-weight:400;letter-spacing:normal;line-height:1;margin:0;overflow:visible;padding:0;text-align:left;text-decoration:none;text-indent:0;text-shadow:none;text-transform:none;visibility:visible;white-space:normal;word-spacing:normal}.fb_reset>div{overflow:hidden}@keyframes fb_transform{0%{opacity:0;transform:scale(.95)}to{opacity:1;transform:scale(1)}}.fb_animate{animation:fb_transform .3s forwards}

.fb_dialog{background:#525252b3;position:absolute;top:-10000px;z-index:10001}.fb_dialog_advanced{border-radius:8px;padding:10px}.fb_dialog_content{background:#fff;color:#373737}.fb_dialog_close_icon{background:url(https://connect.facebook.net/rsrc.php/v4/yq/r/IE9JII6Z1Ys.png) no-repeat scroll 0 0 transparent;cursor:pointer;display:block;height:15px;position:absolute;right:18px;top:17px;width:15px}.fb_dialog_mobile .fb_dialog_close_icon{left:5px;right:auto;top:5px}.fb_dialog_padding{background-color:transparent;position:absolute;width:1px;z-index:-1}.fb_dialog_close_icon:hover{background:url(https://connect.facebook.net/rsrc.php/v4/yq/r/IE9JII6Z1Ys.png) no-repeat scroll 0 -15px transparent}.fb_dialog_close_icon:active{background:url(https://connect.facebook.net/rsrc.php/v4/yq/r/IE9JII6Z1Ys.png) no-repeat scroll 0 -30px transparent}.fb_dialog_iframe{line-height:0}.fb_dialog_content .dialog_title{background:#6d84b4;border:1px solid #365899;color:#fff;font-size:14px;font-weight:700;margin:0}.fb_dialog_content .dialog_title>span{background:url(https://connect.facebook.net/rsrc.php/v4/yd/r/Cou7n-nqK52.gif) no-repeat 5px 50%;float:left;padding:5px 0 7px 26px}body.fb_hidden{height:100%;left:0;margin:0;overflow:visible;position:absolute;top:-10000px;transform:none;width:100%}.fb_dialog.fb_dialog_mobile.loading{background:url(https://connect.facebook.net/rsrc.php/v4/ya/r/3rhSv5V8j3o.gif) #fff no-repeat 50% 50%;min-height:100%;min-width:100%;overflow:hidden;position:absolute;top:0;z-index:10001}.fb_dialog.fb_dialog_mobile.loading.centered{background:none;height:auto;min-height:initial;min-width:initial;width:auto}.fb_dialog.fb_dialog_mobile.loading.centered #fb_dialog_loader_spinner{width:100%}.fb_dialog.fb_dialog_mobile.loading.centered .fb_dialog_content{background:none}.loading.centered #fb_dialog_loader_close{clear:both;color:#fff;display:block;font-size:18px;padding-top:20px}#fb-root #fb_dialog_ipad_overlay{background:#0006;inset:0;min-height:100%;position:absolute;width:100%;z-index:10000}#fb-root #fb_dialog_ipad_overlay.hidden{display:none}.fb_dialog.fb_dialog_mobile.loading iframe{visibility:hidden}.fb_dialog_mobile .fb_dialog_iframe{position:sticky;top:0}.fb_dialog_content .dialog_header{background:linear-gradient(from(#738aba),to(#2c4987));border-bottom:1px solid;border-color:#043b87;box-shadow:#fff 0 1px 1px -1px inset;color:#fff;font:700 14px Helvetica,sans-serif;text-overflow:ellipsis;text-shadow:rgba(0,30,84,.296875) 0px -1px 0px;vertical-align:middle;white-space:nowrap}.fb_dialog_content .dialog_header table{height:43px;width:100%}.fb_dialog_content .dialog_header td.header_left{font-size:12px;padding-left:5px;vertical-align:middle;width:60px}.fb_dialog_content .dialog_header td.header_right{font-size:12px;padding-right:5px;vertical-align:middle;width:60px}.fb_dialog_content .touchable_button{background:linear-gradient(from(#4267B2),to(#2a4887));background-clip:padding-box;border:1px solid #29487d;border-radius:3px;display:inline-block;line-height:18px;margin-top:3px;max-width:85px;padding:4px 12px;position:relative}.fb_dialog_content .dialog_header .touchable_button input{background:none;border:none;color:#fff;font:700 12px Helvetica,sans-serif;margin:2px -12px;padding:2px 6px 3px;text-shadow:rgba(0,30,84,.296875) 0px -1px 0px}.fb_dialog_content .dialog_header .header_center{color:#fff;font-size:16px;font-weight:700;line-height:18px;text-align:center;vertical-align:middle}.fb_dialog_content .dialog_content{background:url(https://connect.facebook.net/rsrc.php/v4/y9/r/jKEcVPZFk-2.gif) no-repeat 50% 50%;border:1px solid #4A4A4A;border-bottom:0;border-top:0;height:150px}.fb_dialog_content .dialog_footer{background:#f5f6f7;border:1px solid #4A4A4A;border-top-color:#ccc;height:40px}#fb_dialog_loader_close{float:left}.fb_dialog.fb_dialog_mobile .fb_dialog_close_icon{visibility:hidden}#fb_dialog_loader_spinner{animation:rotateSpinner 1.2s linear infinite;background-color:transparent;background-image:url(https://connect.facebook.net/rsrc.php/v4/yD/r/t-wz8gw1xG1.png);background-position:50% 50%;background-repeat:no-repeat;height:24px;width:24px}@keyframes rotateSpinner{0%{transform:rotate(0)}to{transform:rotate(360deg)}}

.fb_iframe_widget{display:inline-block;position:relative}.fb_iframe_widget span{display:inline-block;position:relative;text-align:justify}.fb_iframe_widget iframe{position:absolute}.fb_iframe_widget_fluid_desktop,.fb_iframe_widget_fluid_desktop span,.fb_iframe_widget_fluid_desktop iframe{max-width:100%}.fb_iframe_widget_fluid_desktop iframe{min-width:220px;position:relative}.fb_iframe_widget_lift{z-index:1}.fb_iframe_widget_fluid{display:inline}.fb_iframe_widget_fluid span{width:100%}
</style><style type="text/css">.MathJax_Display {text-align: center; margin: 1em 0em; position: relative; display: block!important; text-indent: 0; max-width: none; max-height: none; min-width: 0; min-height: 0; width: 100%}
.MathJax .merror {background-color: #FFFF88; color: #CC0000; border: 1px solid #CC0000; padding: 1px 3px; font-style: normal; font-size: 90%}
.MathJax .MJX-monospace {font-family: monospace}
.MathJax .MJX-sans-serif {font-family: sans-serif}
#MathJax_Tooltip {background-color: InfoBackground; color: InfoText; border: 1px solid black; box-shadow: 2px 2px 5px #AAAAAA; -webkit-box-shadow: 2px 2px 5px #AAAAAA; -moz-box-shadow: 2px 2px 5px #AAAAAA; -khtml-box-shadow: 2px 2px 5px #AAAAAA; filter: progid:DXImageTransform.Microsoft.dropshadow(OffX=2, OffY=2, Color='gray', Positive='true'); padding: 3px 4px; z-index: 401; position: absolute; left: 0; top: 0; width: auto; height: auto; display: none}
.MathJax {display: inline; font-style: normal; font-weight: normal; line-height: normal; font-size: 100%; font-size-adjust: none; text-indent: 0; text-align: left; text-transform: none; letter-spacing: normal; word-spacing: normal; word-wrap: normal; white-space: nowrap; float: none; direction: ltr; max-width: none; max-height: none; min-width: 0; min-height: 0; border: 0; padding: 0; margin: 0}
.MathJax:focus, body :focus .MathJax {display: inline-table}
.MathJax.MathJax_FullWidth {text-align: center; display: table-cell!important; width: 10000em!important}
.MathJax img, .MathJax nobr, .MathJax a {border: 0; padding: 0; margin: 0; max-width: none; max-height: none; min-width: 0; min-height: 0; vertical-align: 0; line-height: normal; text-decoration: none}
img.MathJax_strut {border: 0!important; padding: 0!important; margin: 0!important; vertical-align: 0!important}
.MathJax span {display: inline; position: static; border: 0; padding: 0; margin: 0; vertical-align: 0; line-height: normal; text-decoration: none; box-sizing: content-box}
.MathJax nobr {white-space: nowrap!important}
.MathJax img {display: inline!important; float: none!important}
.MathJax * {transition: none; -webkit-transition: none; -moz-transition: none; -ms-transition: none; -o-transition: none}
.MathJax_Processing {visibility: hidden; position: fixed; width: 0; height: 0; overflow: hidden}
.MathJax_Processed {display: none!important}
.MathJax_ExBox {display: block!important; overflow: hidden; width: 1px; height: 60ex; min-height: 0; max-height: none}
.MathJax .MathJax_EmBox {display: block!important; overflow: hidden; width: 1px; height: 60em; min-height: 0; max-height: none}
.MathJax_LineBox {display: table!important}
.MathJax_LineBox span {display: table-cell!important; width: 10000em!important; min-width: 0; max-width: none; padding: 0; border: 0; margin: 0}
.MathJax .MathJax_HitBox {cursor: text; background: white; opacity: 0; filter: alpha(opacity=0)}
.MathJax .MathJax_HitBox * {filter: none; opacity: 1; background: transparent}
#MathJax_Tooltip * {filter: none; opacity: 1; background: transparent}
@font-face {font-family: MathJax_Main; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Main-Regular.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Main-Regular.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Main-bold; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Main-Bold.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Main-Bold.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Main-italic; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Main-Italic.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Main-Italic.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Math-italic; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Math-Italic.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Math-Italic.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Caligraphic; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Caligraphic-Regular.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Caligraphic-Regular.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Size1; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Size1-Regular.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Size1-Regular.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Size2; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Size2-Regular.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Size2-Regular.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Size3; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Size3-Regular.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Size3-Regular.otf?V=2.7.4') format('opentype')}
@font-face {font-family: MathJax_Size4; src: url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/woff/MathJax_Size4-Regular.woff?V=2.7.4') format('woff'), url('/node_modules/mathjax//../fonts/HTML-CSS/TeX/otf/MathJax_Size4-Regular.otf?V=2.7.4') format('opentype')}
.MathJax .noError {vertical-align: ; font-size: 90%; text-align: left; color: black; padding: 1px 3px; border: 1px solid}
</style></head>
<body><div style="visibility: hidden; overflow: hidden; position: absolute; top: 0px; height: 1px; width: auto; padding: 0px; border: 0px; margin: 0px; text-align: left; text-indent: 0px; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal;"><div id="MathJax_Hidden"><br><br></div></div><div id="MathJax_Message" style="display: none;"></div><div id="fb-root" class=" fb_reset"><div style="position: absolute; top: -10000px; width: 0px; height: 0px;"><div></div></div></div><script type="text/javascript">(function(d, s, id) {
var js, fjs = d.getElementsByTagName(s)[0];
if (d.getElementById(id)) return;
js = d.createElement(s); js.id = id;
js.src = "//connect.facebook.net/en_US/sdk.js#xfbml=1&version=v2.10&appId=1581769695449208";
fjs.parentNode.insertBefore(js, fjs);
}(document, 'script', 'facebook-jssdk'));</script><!--div#scroller-anchor--><!--if (atOhioState)--><!--include includes/osu--><!-- BADBAD: shouldn't this be removed now that htlatex is working--><!-- fine? No! Apparently htlatex still doesn't support two optional--><!-- arguments like this.--><div style="display: none;"><span class="MathJax" id="MathJax-Element-1-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; />" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-1" style="width: 0em; display: inline-block;"><span style="display: inline-block; position: relative; width: 0em; height: 0px; font-size: 116%;"><span style="position: absolute; clip: rect(3.828em, 1000em, 4.151em, -999.997em); top: -3.984em; left: 0em;"><span class="mrow" id="MathJax-Span-2"></span><span style="display: inline-block; width: 0px; height: 3.99em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.059em; border-left: 0px solid; width: 0px; height: 0.128em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"></math></span></span><script type="math/tex" id="MathJax-Element-1">\newcommand{\arraycolsep}[3]{}
\newcommand{\dd}[2][]{\frac{d #1}{d #2}}
\newcommand{\pp}[2][]{\frac{\partial #1}{\partial #2}}
\newcommand{\veci}{\vec{\hat{\bf\imath}}}
\newcommand{\vecj}{\vec{\hat{\bf\jmath}}}
\newcommand{\utan}{\vec{\hat{t}}}
\newcommand{\unormal}{\vec{\hat{n}}}
\newenvironment{amatrix}[1]{%
  \begin{bmatrix}
}{%
  \end{bmatrix}
}</script></div><div class="container-fluid"><!-- BADBAD: only display navigation if the item can be found IN a navigation list--><div class="row"><div class="col-md-12"></div></div><div class="row justify-content-center"><div class="col-md-10"><main class="activity" id="theActivity" data-hash="102c8947a701a12c61c5237941cd04d2ef2e64dd" data-repository-name="johnweeks03-test" data-commit="5efd7a5b908d5ccf688e7941a1ff70bcd5451365" data-path="aFirstFolder/aFirstActivity" data-title="A Change In The Air" role="main" data-xourse-path="aFirstXourse" data-xourse-url="johnweeks03-test/aFirstXourse" data-points="3"><div class="activity-body" id="page-content"> 
<div class="preamble">
<span class="MathJax" id="MathJax-Element-2-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; />" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-3" style="width: 0em; display: inline-block;"><span style="display: inline-block; position: relative; width: 0em; height: 0px; font-size: 116%;"><span style="position: absolute; clip: rect(3.828em, 1000em, 4.151em, -999.997em); top: -3.984em; left: 0em;"><span class="mrow" id="MathJax-Span-4"></span><span style="display: inline-block; width: 0px; height: 3.99em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.059em; border-left: 0px solid; width: 0px; height: 0.128em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"></math></span></span><script type="math/tex" id="MathJax-Element-2">\newenvironment {prompt}{}{}
\newcommand {\accordion }[0]{}
\newcommand {\ungraded }[0]{}
\newcommand {\xmDefaultPreamble }[0]{xmPreamble.tex}
\newcommand {\refeq }[1]{\textup {\ref {#1}}}
\newcommand {\lparen }[0]{(}
\newcommand {\rparen }[0]{)}
\newcommand {\SwapAboveDisplaySkip }[0]{\noalign {\vskip -\abovedisplayskip \vskip \abovedisplayshortskip }}
\newcommand {\vdotswithin }[1]{{\mathmakebox [\widthof {\ensuremath {{}#1{}}}][c]{{\vdots }}}}
\newcommand {\MTFlushSpaceBelow }[0]{\\\noalign {\nobreak \vskip -\lineskip \vskip -\l_MT_shortvdotswithinadjustbelow_dim \vskip -\origjot \vskip \jot }}
\newcommand {\crampedsubstack }[1]{\crampedsubarray {c}#1\endcrampedsubarray }
\newcommand {\spreadlines }[1]{\setlength {\jot }{#1}\ignorespaces }
\newcommand {\splitfrac }[2]{\genfrac {}{}{0pt}{1}{\textstyle #1\quad \hfill }{\textstyle \hfill \quad \mathstrut #2}}
\newcommand {\splitdfrac }[2]{\genfrac {}{}{0pt}{0}{#1\quad \hfill }{\hfill \quad \mathstrut #2}}
\newcommand {\TickSize }[0]{2pt}
\newcommand {\w }[0]{\text }
\newcommand {\R }[0]{\mathbb {R}}
\newcommand {\Z }[0]{\mathbb {Z}}
\newcommand {\N }[0]{\mathbb {N}}
\newcommand {\C }[0]{\mathbb {C}}
\newcommand {\Q }[0]{\mathbb {Q}}
\newcommand {\bld }[0]{\textbf }
\newcommand {\ital }[0]{\textit }
\newcommand {\un }[0]{\underline }
\newcommand {\bmat }[1]{\begin {bmatrix} #1 \end {bmatrix}}
\newcommand {\pmat }[1]{\begin {pmatrix} #1 \end {pmatrix}}
\newcommand {\Power }[0]{\mathcal {P}}
\newcommand {\Orbit }[0]{\mathcal {O}}
\newcommand {\normal }[0]{\triangleleft }
\newcommand {\comp }[0]{\setminus }
\newcommand {\F }[0]{\mathbb {F}}
\newcommand {\injmap }[0]{\xhookrightarrow {}}
\newcommand {\salg }[0]{\sigma \w {-alg}}
\newcommand {\sa }[0]{$\sigma $-algebra}
\newcommand {\spc }[0]{\hspace {.8ex}}
\newcommand {\dl }[0]{\partial }
\newcommand {\eps }[0]{\varepsilon }
\newcommand {\Borel }[0]{\mathcal {B}}
\newcommand {\U }[0]{\mathcal {U}}
\newcommand {\ta }[0]{\uptau }
\newcommand {\Gb }[0]{\mathbb {G}}
\newcommand {\Cc }[0]{\mathcal {C}}
\newcommand {\Ac }[0]{\mathcal {A}}
\newcommand {\Bc }[0]{\mathcal {B}}
\newcommand {\Dc }[0]{\mathcal {D}}
\newcommand {\Ec }[0]{\mathcal {E}}
\newcommand {\T }[0]{\mathbb {T}}
\newcommand {\Hc }[0]{\mathcal {H}}
\newcommand {\Ic }[0]{\mathcal {I}}
\newcommand {\Jc }[0]{\mathcal {J}}
\newcommand {\Lc }[0]{\mathcal {L}}
\newcommand {\Oc }[0]{\mathcal {O}}
\newcommand {\Mc }[0]{\mathcal {M}}
\newcommand {\Nc }[0]{\mathcal {N}}
\newcommand {\Pc }[0]{\mathcal {P}}
\newcommand {\Tc }[0]{\mathcal {T}}
\DeclareMathOperator {\card }{card}
\DeclareMathOperator {\Ker }{Ker}
\DeclareMathOperator {\im }{Im}
\DeclareMathOperator {\dom }{dom}
\DeclareMathOperator {\ran }{ran}
\DeclareMathOperator {\Sym }{Sym}
\DeclareMathOperator {\Aut }{Aut}
\DeclareMathOperator {\Loc }{L^1_{\w {loc}}}
\DeclareMathOperator {\diag }{diag}
\DeclareMathOperator {\End }{End}
\DeclareMathOperator {\Hom }{Hom}
\DeclareMathOperator {\Mor }{Mor}
\DeclareMathOperator {\Lip }{Lip}
\DeclareMathOperator {\id }{id}
\DeclareMathOperator {\Irr }{Irr}
\DeclareMathOperator {\supp }{supp}
\DeclareMathOperator {\Span }{span}
\DeclareMathOperator {\Tr }{Tr}
\DeclareMathOperator {\tr }{tr}
\newcommand {\xmDefaultPrintstyle }[0]{xmPrintstyle.sty}
\newcommand {\luastring }[1]{"\luatexluaescapestring {#1}"}
\newcommand {\luastringO }[1]{\luastring {\unexpanded \expandafter {#1}}}
\newcommand {\luastringN }[1]{\luastring {\unexpanded {#1}}}
\newcommand {\RestoreMathJaxEnvironment }[1]{\expandafter \let \csname #1\expandafter \endcsname \csname mathjax-#1\endcsname \expandafter \let \csname end#1\expandafter \endcsname \csname mathjax-end#1\endcsname }
\newcommand {\DeclareMicrotypeVariants }[1]{}
\newcommand {\DeclareMicrotypeAlias }[2]{}
\newcommand {\LoadMicrotypeFile }[1]{}
\newcommand {\DeclareMicrotypeFilePrefix }[1]{}
\newcommand {\DeclareMicrotypeBabelHook }[2]{}
\newcommand {\microtypesetup }[1]{}
\newcommand {\microtypecontext }[1]{}
\newcommand {\textmicrotypecontext }[2]{#2}
\newcommand {\leftprotrusion }[1]{#1}
\newcommand {\rightprotrusion }[1]{#1}
\newcommand {\noprotrusionifhmode }[0]{}
\newcommand {\lsstyle }[0]{}
\newcommand {\lslig }[1]{#1}
\newcommand {\maketitle }[0]{}
\newcommand {\ConfigureQuestionEnv }[2]{\renewenvironment {#1}{\refstepcounter {problem}}{}\ConfigureEnv {#1}{\stepcounter {identification}\ifvmode \IgnorePar \fi \EndP \HCode {&lt;div role="article" class="problem-environment #2" id="problem\arabic {identification}"&gt;}}{\ifvmode \IgnorePar \fi \EndP \HCode {&lt;/div&gt;}\IgnoreIndent }{}{}}
\newcommand {\problem }[0]{\refstepcounter {problem}}
\newcommand {\exercise }[0]{\refstepcounter {problem}}
\newcommand {\question }[0]{\refstepcounter {problem}}
\newcommand {\exploration }[0]{\refstepcounter {problem}}
\newcommand {\hint }[0]{\refstepcounter {problem}}
\newcommand {\ConfigureTheoremEnv }[1]{\renewenvironment {#1}[1][]{\refstepcounter {problem}\ifthenelse {\equal {###1}{}}{}{\HCode {&lt;span class="theorem-like-title"&gt;}###1\HCode {&lt;/span&gt;}}}{} \ConfigureEnv {#1}{\stepcounter {identification}\ifvmode \IgnorePar \fi \EndP \HCode {&lt;div class="theorem-like problem-environment #1" id="problem\arabic {identification}"&gt;}}{\ifvmode \IgnorePar \fi \EndP \HCode {&lt;/div&gt;}\IgnoreIndent }{}{}}
\newcommand {\dialogue }[0]{\begin {description}}
\newcommand {\foldable }[0]{\stepcounter {identification}\ifvmode \IgnorePar \fi \EndP \HCode {&lt;div id="foldable\arabic {identification}" class="foldable"&gt;}}
\newcommand {\expandable }[0]{\stepcounter {identification}\ifvmode \IgnorePar \fi \EndP \HCode {&lt;div data-original="expandable" id="foldable\arabic {identification}" class="foldable"&gt;}}
\newcommand {\unfoldable }[1]{\HCode {&lt;span class="unfoldable"&gt;}#1\HCode {&lt;/span&gt;}}
\newcommand {\selectAll }[0]{\refstepcounter {problem}}
\newcommand {\freeResponse }[0]{\refstepcounter {problem}}
\newcommand {\javascript }[0]{\NoFonts }
\newcommand {\label }[1]{\oldlabel {#1}\HCode {&lt;a class="ximera-label" id="#1"&gt;&lt;/a&gt;}}
\newcommand {\ref }[1]{\HCode {&lt;a class="reference" href="\##1"&gt;#1&lt;/a&gt;}}
\newcommand {\sageCell }[0]{\NoFonts }
\newcommand {\sageOutput }[0]{\NoFonts }
\newcommand {\sagesilent }[0]{\NoFonts }
\newcommand {\ungraded }[0]{\ifvmode \IgnorePar \fi \EndP \HCode {&lt;div class="ungraded"&gt;}\IgnoreIndent }
\newcommand {\accordion }[0]{\ifvmode \IgnorePar \fi \EndP \HCode {&lt;div class="accordion"&gt;} }
\newcommand {\paragraph }[1]{\HCode {&lt;span class="paragraphHead"&gt;}#1\HCode {&lt;/span&gt;}\par \IgnorePar }
\newcommand {\subparagraph }[1]{\HCode {&lt;span class="subparagraphHead"&gt;}#1\HCode {&lt;/span&gt;}\par \IgnorePar }
\newcommand {\outcome }[1]{\HCode {&lt;span class="learning-outcome"&gt;#1&lt;/span&gt;} }
\newcommand {\javascriptCode }[0]{\NoFonts }
\newcommand {\ref }[1]{\HCode {&lt;a class="reference" href="\##1"&gt;#1&lt;/a&gt;}}</script></div>
<style> .activity-body pre { white-space: pre; background-color: lightgray; } .xmyoutube { aspect-ratio: 16/9; min-width: 75%; } .image-environment img { width: unset; } </style> 
  
<div class="abstract">
<!--  l. 10  --><p class="noindent">A simple Ximera activity.</p> 
</div>
<div class="maketitle"></div><p><a id="x1-1doc"></a><a class="ximera-label" id="xim_aFirstActivity"></a>
</p><!--  l. 14  --><p class="noindent">Ps the most natural setting for Ximera content is that of a <em>worksheet</em>. This is
some document that may contain discussion as well as questions that check
understanding.
</p><!--  l. 18  --><p class="noindent">Ximera comes pre-equipped with many environments. If you are ever curious about
the source code, you can visit this source at
</p>
<div class="center">
<!--  l. 21  --><!--  l. 22  --><p class="noindent"><a class="url" href="https://github.com/ximeraProject/ximeraFirstSteps">https://github.com/ximeraProject/ximeraFirstSteps</a></p></div>
<!--  l. 24  --><p class="noindent">or by appending <span class="obeylines-h"><code class="verb">.tex</code></span> to the URL of this page online.
</p>
<h3 class="sectionHead" id="a-basic-use-case"><span class="titlemark">1   </span> <a id="x1-10001"></a>A basic use case</h3>
<!--  l. 28  --><p class="noindent">We use<span class="obeylines-h"><code class="verb">\begin{definition}</code></span> for definitions and <span class="obeylines-h"><code class="verb">\begin{question}</code></span> for questions.
Since Ximera provides immediate feedback, we suggest following definitions like this
one by a quick question. Here’s an example:
</p>
<div class="theorem-like problem-environment definition" id="problem1" style="visibility: visible; position: relative; opacity: 1;" numbered=" 2"><a id="x1-1001r1"></a><a class="ximera-label" id="def_absolute_value"></a> The <strong>absolute value</strong> of a real number <span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-3-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>a</mi></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-5" style="width: 0.555em; display: inline-block;"><span style="display: inline-block; position: relative; width: 0.555em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.535em, 1000.55em, 2.331em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-6"><span class="mi" id="MathJax-Span-7" style="font-family: MathJax_Math-italic;">a</span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.059em; border-left: 0px solid; width: 0px; height: 0.566em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi></math></span></span><script type="math/tex" id="MathJax-Element-3">a</script></span>, denoted by <span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-4-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mi>a</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-8" style="width: 1.167em; display: inline-block;"><span style="display: inline-block; position: relative; width: 1.106em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.229em, 1000.98em, 2.577em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-9"><span class="texatom" id="MathJax-Span-10"><span class="mrow" id="MathJax-Span-11"><span class="mo" id="MathJax-Span-12" style="font-family: MathJax_Main;">|</span></span></span><span class="mi" id="MathJax-Span-13" style="font-family: MathJax_Math-italic;">a</span><span class="texatom" id="MathJax-Span-14"><span class="mrow" id="MathJax-Span-15"><span class="mo" id="MathJax-Span-16" style="font-family: MathJax_Main;">|</span></span></span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.309em; border-left: 0px solid; width: 0px; height: 1.128em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mi>a</mi><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow></math></span></span><script type="math/tex" id="MathJax-Element-4">|a|</script></span>, is <div class="mathjax-block"><div class="MathJax_Display" style="text-align: center;"><span class="MathJax" id="MathJax-Element-5-Frame" tabindex="0" style="text-align: center; position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mi>a</mi><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mo>=</mo><mrow><mo>{</mo><mtable columnalign=&quot;left left&quot; rowspacing=&quot;.2em&quot; columnspacing=&quot;1em&quot; displaystyle=&quot;false&quot;><mtr><mtd><mi>a</mi></mtd><mtd><mrow><mtext>if&amp;#xA0;</mtext><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>a</mi><mo>&amp;#x2265;</mo><mn>0</mn></mrow></mrow></mtd></mtr><mtr><mtd><mo>&amp;#x2212;</mo><mi>a</mi></mtd><mtd><mrow><mtext>if&amp;#xA0;</mtext><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mi>a</mi><mo>&amp;lt;</mo><mn>0</mn></mrow><mtext>.</mtext></mrow></mtd></mtr></mtable><mo fence=&quot;true&quot; stretchy=&quot;true&quot; symmetric=&quot;true&quot;></mo></mrow></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-17" style="width: 9.623em; display: inline-block;"><span style="display: inline-block; position: relative; width: 9.439em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.719em, 1009.44em, 4.476em, -999.997em); top: -3.367em; left: 0em;"><span class="mrow" id="MathJax-Span-18"><span class="texatom" id="MathJax-Span-19"><span class="mrow" id="MathJax-Span-20"><span class="mo" id="MathJax-Span-21" style="font-family: MathJax_Main;">|</span></span></span><span class="mi" id="MathJax-Span-22" style="font-family: MathJax_Math-italic;">a</span><span class="texatom" id="MathJax-Span-23"><span class="mrow" id="MathJax-Span-24"><span class="mo" id="MathJax-Span-25" style="font-family: MathJax_Main;">|</span></span></span><span class="mo" id="MathJax-Span-26" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mrow" id="MathJax-Span-27" style="padding-left: 0.309em;"><span class="mo" id="MathJax-Span-28" style="vertical-align: 0em;"><span style="font-family: MathJax_Size3;">{</span></span><span class="mtable" id="MathJax-Span-29" style="padding-right: 0.187em; padding-left: 0.187em;"><span style="display: inline-block; position: relative; width: 5.824em; height: 0px;"><span style="position: absolute; clip: rect(2.822em, 1001.29em, 4.905em, -999.997em); top: -3.98em; left: 0em;"><span style="display: inline-block; position: relative; width: 1.29em; height: 0px;"><span style="position: absolute; clip: rect(3.373em, 1000.49em, 4.17em, -999.997em); top: -4.531em; left: 0em;"><span class="mtd" id="MathJax-Span-30"><span class="mrow" id="MathJax-Span-31"><span class="mi" id="MathJax-Span-32" style="font-family: MathJax_Math-italic;">a</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.189em, 1001.29em, 4.231em, -999.997em); top: -3.306em; left: 0em;"><span class="mtd" id="MathJax-Span-42"><span class="mrow" id="MathJax-Span-43"><span class="mo" id="MathJax-Span-44" style="font-family: MathJax_Main;">−</span><span class="mi" id="MathJax-Span-45" style="font-family: MathJax_Math-italic;">a</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(2.577em, 1003.43em, 4.844em, -999.997em); top: -3.98em; left: 2.331em;"><span style="display: inline-block; position: relative; width: 3.557em; height: 0px;"><span style="position: absolute; clip: rect(3.067em, 1003.25em, 4.292em, -999.997em); top: -4.531em; left: 0em;"><span class="mtd" id="MathJax-Span-33"><span class="mrow" id="MathJax-Span-34"><span class="mrow" id="MathJax-Span-35"><span class="mtext" id="MathJax-Span-36" style="font-family: MathJax_Main;">if&nbsp;</span><span class="texatom" id="MathJax-Span-37"><span class="mrow" id="MathJax-Span-38"><span class="mi" id="MathJax-Span-39" style="font-family: MathJax_Math-italic;">a</span><span class="mo" id="MathJax-Span-40" style="font-family: MathJax_Main; padding-left: 0.309em;">≥</span><span class="mn" id="MathJax-Span-41" style="font-family: MathJax_Main; padding-left: 0.309em;">0</span></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1003.43em, 4.231em, -999.997em); top: -3.306em; left: 0em;"><span class="mtd" id="MathJax-Span-46"><span class="mrow" id="MathJax-Span-47"><span class="mrow" id="MathJax-Span-48"><span class="mtext" id="MathJax-Span-49" style="font-family: MathJax_Main;">if&nbsp;</span><span class="texatom" id="MathJax-Span-50"><span class="mrow" id="MathJax-Span-51"><span class="mi" id="MathJax-Span-52" style="font-family: MathJax_Math-italic;">a</span><span class="mo" id="MathJax-Span-53" style="font-family: MathJax_Main; padding-left: 0.309em;">&lt;</span><span class="mn" id="MathJax-Span-54" style="font-family: MathJax_Main; padding-left: 0.309em;">0</span></span></span><span class="mtext" id="MathJax-Span-55" style="font-family: MathJax_Main;">.</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="mo" id="MathJax-Span-56"></span></span></span><span style="display: inline-block; width: 0px; height: 3.373em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.997em; border-left: 0px solid; width: 0px; height: 2.566em;"></span></span></nobr><span class="MJX_Assistive_MathML MJX_Assistive_MathML_Block" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mi>a</mi><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mo>=</mo><mrow><mo>{</mo><mtable columnalign="left left" rowspacing=".2em" columnspacing="1em" displaystyle="false"><mtr><mtd><mi>a</mi></mtd><mtd><mrow><mtext>if&nbsp;</mtext><mrow class="MJX-TeXAtom-ORD"><mi>a</mi><mo>≥</mo><mn>0</mn></mrow></mrow></mtd></mtr><mtr><mtd><mo>−</mo><mi>a</mi></mtd><mtd><mrow><mtext>if&nbsp;</mtext><mrow class="MJX-TeXAtom-ORD"><mi>a</mi><mo>&lt;</mo><mn>0</mn></mrow><mtext>.</mtext></mrow></mtd></mtr></mtable><mo fence="true" stretchy="true" symmetric="true"></mo></mrow></math></span></span></div><script type="math/tex; mode=display" id="MathJax-Element-5"> |a| = \begin {cases} a & \text {if $a \geq 0$} \\ -a & \text {if $a<0$.} \end {cases} </script></div> </div><p> Now students can check
their understanding: </p><div class="problem-environment question" id="problem2" role="article" style="visibility: visible; position: relative; opacity: 1;" data-answer-count="4" data-blocking="true"><a id="x1-1002r2"></a> Evaluate the following:
<dl class="enumerate-enumitem"><dt class="enumerate-enumitem"> 
(a) 
</dt><dd class="enumerate-enumitem"><span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-6-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mn>2</mn><mo>&amp;#x2212;</mo><mn>5</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mo>=</mo><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mn>3</mn></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input narrow&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; style=&quot;width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-57" style="width: 8.704em; display: inline-block;"><span style="display: inline-block; position: relative; width: 8.52em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(2.27em, 1008.52em, 6.192em, -999.997em); top: -4.531em; left: 0em;"><span class="mrow" id="MathJax-Span-58"><span class="texatom" id="MathJax-Span-59"><span class="mrow" id="MathJax-Span-60"><span class="mo" id="MathJax-Span-61" style="font-family: MathJax_Main;">|</span></span></span><span class="mn" id="MathJax-Span-62" style="font-family: MathJax_Main;">2</span><span class="mo" id="MathJax-Span-63" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="mn" id="MathJax-Span-64" style="font-family: MathJax_Main; padding-left: 0.248em;">5</span><span class="texatom" id="MathJax-Span-65"><span class="mrow" id="MathJax-Span-66"><span class="mo" id="MathJax-Span-67" style="font-family: MathJax_Main;">|</span></span></span><span class="mo" id="MathJax-Span-68" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mpadded" id="MathJax-Span-69" style="padding-left: 0.309em;"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-70"><span class="mphantom" id="MathJax-Span-71"><span class="mrow" id="MathJax-Span-72" style="visibility: hidden;"><span class="mn" id="MathJax-Span-73" style="font-family: MathJax_Main;">3</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-74"><span class="annotation-xml" id="MathJax-Span-75" style="font-size: 98%;"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer0problem2" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-76"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-77"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 4.537em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -1.559em; border-left: 0px solid; width: 0px; height: 3.753em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mn>2</mn><mo>−</mo><mn>5</mn><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mo>=</mo><mpadded width="0" height="0"><mphantom><mn>3</mn></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded></math></span></span><script type="math/tex" id="MathJax-Element-6">|2-5| = \answer {3}</script></span>
</dd>     
<dt class="enumerate-enumitem">
(b) 
</dt><dd class="enumerate-enumitem"><span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-7-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mn>5</mn><mo>&amp;#x2212;</mo><mn>2</mn><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mo>=</mo><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mn>3</mn></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input narrow&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; style=&quot;width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-78" style="width: 8.704em; display: inline-block;"><span style="display: inline-block; position: relative; width: 8.52em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(2.27em, 1008.52em, 6.192em, -999.997em); top: -4.531em; left: 0em;"><span class="mrow" id="MathJax-Span-79"><span class="texatom" id="MathJax-Span-80"><span class="mrow" id="MathJax-Span-81"><span class="mo" id="MathJax-Span-82" style="font-family: MathJax_Main;">|</span></span></span><span class="mn" id="MathJax-Span-83" style="font-family: MathJax_Main;">5</span><span class="mo" id="MathJax-Span-84" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="mn" id="MathJax-Span-85" style="font-family: MathJax_Main; padding-left: 0.248em;">2</span><span class="texatom" id="MathJax-Span-86"><span class="mrow" id="MathJax-Span-87"><span class="mo" id="MathJax-Span-88" style="font-family: MathJax_Main;">|</span></span></span><span class="mo" id="MathJax-Span-89" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mpadded" id="MathJax-Span-90" style="padding-left: 0.309em;"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-91"><span class="mphantom" id="MathJax-Span-92"><span class="mrow" id="MathJax-Span-93" style="visibility: hidden;"><span class="mn" id="MathJax-Span-94" style="font-family: MathJax_Main;">3</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-95"><span class="annotation-xml" id="MathJax-Span-96" style="font-size: 98%;"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer1problem2" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-97"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-98"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 4.537em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -1.559em; border-left: 0px solid; width: 0px; height: 3.753em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mn>5</mn><mo>−</mo><mn>2</mn><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mo>=</mo><mpadded width="0" height="0"><mphantom><mn>3</mn></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded></math></span></span><script type="math/tex" id="MathJax-Element-7">|5-2| = \answer {3}</script></span>
</dd>     
<dt class="enumerate-enumitem">
(c) 
</dt><dd class="enumerate-enumitem"><span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-8-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mn>5</mn><mo>&amp;#x2212;</mo><msqrt><mn>2</mn></msqrt><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mo>=</mo><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mn>3.58578643763</mn></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; style=&quot;width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-99" style="width: 14.893em; display: inline-block;"><span style="display: inline-block; position: relative; width: 14.586em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(2.27em, 1014.59em, 6.192em, -999.997em); top: -4.531em; left: 0em;"><span class="mrow" id="MathJax-Span-100"><span class="texatom" id="MathJax-Span-101"><span class="mrow" id="MathJax-Span-102"><span class="mo" id="MathJax-Span-103" style="font-family: MathJax_Main;">|</span></span></span><span class="mn" id="MathJax-Span-104" style="font-family: MathJax_Main;">5</span><span class="mo" id="MathJax-Span-105" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="msqrt" id="MathJax-Span-106" style="padding-left: 0.248em;"><span style="display: inline-block; position: relative; width: 1.351em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000.43em, 4.17em, -999.997em); top: -3.98em; left: 0.861em;"><span class="mrow" id="MathJax-Span-107"><span class="mn" id="MathJax-Span-108" style="font-family: MathJax_Main;">2</span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.496em, 1000.49em, 3.925em, -999.997em); top: -4.531em; left: 0.861em;"><span style="font-family: MathJax_Main;">–</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.006em, 1000.86em, 4.354em, -999.997em); top: -4.041em; left: 0em;"><span style="font-family: MathJax_Main;">√</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="texatom" id="MathJax-Span-109"><span class="mrow" id="MathJax-Span-110"><span class="mo" id="MathJax-Span-111" style="font-family: MathJax_Main;">|</span></span></span><span class="mo" id="MathJax-Span-112" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mpadded" id="MathJax-Span-113" style="padding-left: 0.309em;"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-114"><span class="mphantom" id="MathJax-Span-115"><span class="mrow" id="MathJax-Span-116" style="visibility: hidden;"><span class="mn" id="MathJax-Span-117" style="font-family: MathJax_Main;">3.58578643763</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-118"><span class="annotation-xml" id="MathJax-Span-119" style="font-size: 98%;"><form class="form-inline mathjaxed-input" xmlns="http://www.w3.org/1999/xhtml" style="width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer2problem2" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-120"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-121"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 4.537em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -1.559em; border-left: 0px solid; width: 0px; height: 3.753em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mn>5</mn><mo>−</mo><msqrt><mn>2</mn></msqrt><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mo>=</mo><mpadded width="0" height="0"><mphantom><mn>3.58578643763</mn></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input" xmlns="http://www.w3.org/1999/xhtml" style="width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded></math></span></span><script type="math/tex" id="MathJax-Element-8">|5-\sqrt {2}| = \answer {3.58578643763}</script></span>
</dd>     
<dt class="enumerate-enumitem">
(d) 
</dt><dd class="enumerate-enumitem"><span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-9-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mn>5</mn><mo>&amp;#x2212;</mo><msqrt><mn>2</mn></msqrt><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mo>=</mo><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mn>5</mn><mo>&amp;#x2212;</mo><msqrt><mn>2</mn></msqrt></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; style=&quot;width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-122" style="width: 14.893em; display: inline-block;"><span style="display: inline-block; position: relative; width: 14.586em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(2.27em, 1014.59em, 6.192em, -999.997em); top: -4.531em; left: 0em;"><span class="mrow" id="MathJax-Span-123"><span class="texatom" id="MathJax-Span-124"><span class="mrow" id="MathJax-Span-125"><span class="mo" id="MathJax-Span-126" style="font-family: MathJax_Main;">|</span></span></span><span class="mn" id="MathJax-Span-127" style="font-family: MathJax_Main;">5</span><span class="mo" id="MathJax-Span-128" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="msqrt" id="MathJax-Span-129" style="padding-left: 0.248em;"><span style="display: inline-block; position: relative; width: 1.351em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000.43em, 4.17em, -999.997em); top: -3.98em; left: 0.861em;"><span class="mrow" id="MathJax-Span-130"><span class="mn" id="MathJax-Span-131" style="font-family: MathJax_Main;">2</span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.496em, 1000.49em, 3.925em, -999.997em); top: -4.531em; left: 0.861em;"><span style="font-family: MathJax_Main;">–</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.006em, 1000.86em, 4.354em, -999.997em); top: -4.041em; left: 0em;"><span style="font-family: MathJax_Main;">√</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="texatom" id="MathJax-Span-132"><span class="mrow" id="MathJax-Span-133"><span class="mo" id="MathJax-Span-134" style="font-family: MathJax_Main;">|</span></span></span><span class="mo" id="MathJax-Span-135" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mpadded" id="MathJax-Span-136" style="padding-left: 0.309em;"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(2.944em, 1000em, 4.354em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-137"><span class="mphantom" id="MathJax-Span-138"><span class="mrow" id="MathJax-Span-139" style="visibility: hidden;"><span class="mn" id="MathJax-Span-140" style="font-family: MathJax_Main;">5</span><span class="mo" id="MathJax-Span-141" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="msqrt" id="MathJax-Span-142" style="padding-left: 0.248em;"><span style="display: inline-block; position: relative; width: 1.351em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000.43em, 4.17em, -999.997em); top: -3.98em; left: 0.861em;"><span class="mrow" id="MathJax-Span-143"><span class="mn" id="MathJax-Span-144" style="font-family: MathJax_Main;">2</span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.496em, 1000.49em, 3.925em, -999.997em); top: -4.531em; left: 0.861em;"><span style="font-family: MathJax_Main;">–</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.006em, 1000.86em, 4.354em, -999.997em); top: -4.041em; left: 0em;"><span style="font-family: MathJax_Main;">√</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-145"><span class="annotation-xml" id="MathJax-Span-146" style="font-size: 98%;"><form class="form-inline mathjaxed-input" xmlns="http://www.w3.org/1999/xhtml" style="width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer3problem2" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-147"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-148"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 4.537em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -1.559em; border-left: 0px solid; width: 0px; height: 3.753em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mn>5</mn><mo>−</mo><msqrt><mn>2</mn></msqrt><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mo>=</mo><mpadded width="0" height="0"><mphantom><mn>5</mn><mo>−</mo><msqrt><mn>2</mn></msqrt></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input" xmlns="http://www.w3.org/1999/xhtml" style="width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded></math></span></span><script type="math/tex" id="MathJax-Element-9">|5-\sqrt {2}| = \answer {5-\sqrt {2}}</script></span></dd></dl>
                                                                  

                                                                  
</div>
<!--  l. 52  --><p class="noindent">To see why there are two versions of the <span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-10-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow><mn>5</mn><mo>&amp;#x2212;</mo><msqrt><mn>2</mn></msqrt><mrow class=&quot;MJX-TeXAtom-ORD&quot;><mo stretchy=&quot;false&quot;>|</mo></mrow></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-149" style="width: 3.741em; display: inline-block;"><span style="display: inline-block; position: relative; width: 3.68em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.106em, 1003.56em, 2.577em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-150"><span class="texatom" id="MathJax-Span-151"><span class="mrow" id="MathJax-Span-152"><span class="mo" id="MathJax-Span-153" style="font-family: MathJax_Main;">|</span></span></span><span class="mn" id="MathJax-Span-154" style="font-family: MathJax_Main;">5</span><span class="mo" id="MathJax-Span-155" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="msqrt" id="MathJax-Span-156" style="padding-left: 0.248em;"><span style="display: inline-block; position: relative; width: 1.351em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000.43em, 4.17em, -999.997em); top: -3.98em; left: 0.861em;"><span class="mrow" id="MathJax-Span-157"><span class="mn" id="MathJax-Span-158" style="font-family: MathJax_Main;">2</span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.496em, 1000.49em, 3.925em, -999.997em); top: -4.531em; left: 0.861em;"><span style="font-family: MathJax_Main;">–</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.006em, 1000.86em, 4.354em, -999.997em); top: -4.041em; left: 0em;"><span style="font-family: MathJax_Main;">√</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="texatom" id="MathJax-Span-159"><span class="mrow" id="MathJax-Span-160"><span class="mo" id="MathJax-Span-161" style="font-family: MathJax_Main;">|</span></span></span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.309em; border-left: 0px solid; width: 0px; height: 1.253em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow><mn>5</mn><mo>−</mo><msqrt><mn>2</mn></msqrt><mrow class="MJX-TeXAtom-ORD"><mo stretchy="false">|</mo></mrow></math></span></span><script type="math/tex" id="MathJax-Element-10">|5-\sqrt {2}|</script></span> question, view the source code for this
question by appending <span class="obeylines-h"><code class="verb">.tex</code></span> to the end of the URL.
</p><!--  l. 54  -->
<h3 class="sectionHead" id="a-paradox"><span class="titlemark">2   </span> <a id="x1-20002"></a>A paradox</h3>
<!--  l. 57  --><p class="noindent">Here’s something fun
</p>
<div class="theorem-like problem-environment paradox" id="problem3" style="visibility: visible; position: relative; opacity: 1;" data-answer-count="2" data-blocking="true"><a id="x1-2001r3"></a><span class="theorem-like-title"><span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-11-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mn>0</mn><mo>=</mo><mn>1</mn></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-162" style="width: 2.454em; display: inline-block;"><span style="display: inline-block; position: relative; width: 2.393em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.29em, 1002.33em, 2.331em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-163"><span class="mn" id="MathJax-Span-164" style="font-family: MathJax_Main;">0</span><span class="mo" id="MathJax-Span-165" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mn" id="MathJax-Span-166" style="font-family: MathJax_Main; padding-left: 0.309em;">1</span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.059em; border-left: 0px solid; width: 0px; height: 0.816em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>0</mn><mo>=</mo><mn>1</mn></math></span></span><script type="math/tex" id="MathJax-Element-11">0=1</script></span></span> Let <span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-12-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>x</mi><mo>=</mo><mi>y</mi></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-167" style="width: 2.515em; display: inline-block;"><span style="display: inline-block; position: relative; width: 2.454em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.535em, 1002.45em, 2.515em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-168"><span class="mi" id="MathJax-Span-169" style="font-family: MathJax_Math-italic;">x</span><span class="mo" id="MathJax-Span-170" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mi" id="MathJax-Span-171" style="font-family: MathJax_Math-italic; padding-left: 0.309em;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.247em; border-left: 0px solid; width: 0px; height: 0.816em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi><mo>=</mo><mi>y</mi></math></span></span><script type="math/tex" id="MathJax-Element-12">x=y</script></span> and write <div class="mathjax-env mathjax-align"><div class="MathJax_Display"><span class="MathJax MathJax_FullWidth" id="MathJax-Element-13-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtable columnalign=&quot;right left right left right left right left right left right left&quot; rowspacing=&quot;3pt&quot; columnspacing=&quot;0em 2em 0em 2em 0em 2em 0em 2em 0em 2em 0em&quot; displaystyle=&quot;true&quot;><mlabeledtr><mtd id=&quot;mjx-eqn-1&quot;><mtext>(1)</mtext></mtd><mtd><msup><mi>x</mi><mn>2</mn></msup></mtd><mtd><mi></mi><mo>=</mo><mi>x</mi><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id=&quot;mjx-eqn-2&quot;><mtext>(2)</mtext></mtd><mtd><msup><mi>x</mi><mn>2</mn></msup><mo>&amp;#x2212;</mo><msup><mi>y</mi><mn>2</mn></msup></mtd><mtd><mi></mi><mo>=</mo><mi>x</mi><mi>y</mi><mo>&amp;#x2212;</mo><msup><mi>y</mi><mn>2</mn></msup></mtd></mlabeledtr><mlabeledtr><mtd id=&quot;mjx-eqn-3&quot;><mtext>(3)</mtext></mtd><mtd><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>&amp;#x2212;</mo><mi>y</mi><mo stretchy=&quot;false&quot;>)</mo><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>+</mo><mi>y</mi><mo stretchy=&quot;false&quot;>)</mo></mtd><mtd><mi></mi><mo>=</mo><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>&amp;#x2212;</mo><mi>y</mi><mo stretchy=&quot;false&quot;>)</mo><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id=&quot;mjx-eqn-4&quot;><mtext>(4)</mtext></mtd><mtd><mo stretchy=&quot;false&quot;>(</mo><mi>x</mi><mo>+</mo><mi>y</mi><mo stretchy=&quot;false&quot;>)</mo></mtd><mtd><mi></mi><mo>=</mo><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id=&quot;mjx-eqn-5&quot;><mtext>(5)</mtext></mtd><mtd><mn>2</mn><mi>y</mi></mtd><mtd><mi></mi><mo>=</mo><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id=&quot;mjx-eqn-6&quot;><mtext>(6)</mtext></mtd><mtd><mn>2</mn></mtd><mtd><mi></mi><mo>=</mo><mn>1.</mn></mtd></mlabeledtr></mtable></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-172" style="width: 100%; display: inline-block; min-width: 15.383em;"><span style="display: inline-block; position: relative; width: 100%; height: 0px; font-size: 102%; min-width: 15.383em;"><span style="position: absolute; clip: rect(4.537em, 1011.28em, 12.871em, -999.997em); top: -8.943em; left: 0em; width: 100%;"><span class="mrow" id="MathJax-Span-173"><span class="mtable" id="MathJax-Span-174" style="min-width: 15.383em;"><span style="display: inline-block; position: relative; width: 100%; height: 0px; min-width: 15.383em;"><span style="display: inline-block; position: absolute; width: 11.278em; height: 0px; clip: rect(-4.409em, 1011.28em, 3.925em, -999.997em); top: 0em; left: 50%; margin-left: -5.634em;"><span style="position: absolute; clip: rect(4.292em, 1006.13em, 12.381em, -999.997em); top: -8.698em; left: 0em;"><span style="display: inline-block; position: relative; width: 6.253em; height: 0px;"><span style="position: absolute; clip: rect(2.944em, 1000.98em, 4.17em, -999.997em); top: -7.35em; right: 0em;"><span class="mtd" id="MathJax-Span-178"><span class="mrow" id="MathJax-Span-179"><span class="msubsup" id="MathJax-Span-180"><span style="display: inline-block; position: relative; width: 0.983em; height: 0px;"><span style="position: absolute; clip: rect(3.373em, 1000.55em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mi" id="MathJax-Span-181" style="font-family: MathJax_Math-italic;">x</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; top: -4.409em; left: 0.555em;"><span class="mn" id="MathJax-Span-182" style="font-size: 70.7%; font-family: MathJax_Main;">2</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(2.944em, 1003.25em, 4.354em, -999.997em); top: -5.879em; right: 0em;"><span class="mtd" id="MathJax-Span-192"><span class="mrow" id="MathJax-Span-193"><span class="msubsup" id="MathJax-Span-194"><span style="display: inline-block; position: relative; width: 0.983em; height: 0px;"><span style="position: absolute; clip: rect(3.373em, 1000.55em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mi" id="MathJax-Span-195" style="font-family: MathJax_Math-italic;">x</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; top: -4.409em; left: 0.555em;"><span class="mn" id="MathJax-Span-196" style="font-size: 70.7%; font-family: MathJax_Main;">2</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="mo" id="MathJax-Span-197" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="msubsup" id="MathJax-Span-198" style="padding-left: 0.248em;"><span style="display: inline-block; position: relative; width: 0.983em; height: 0px;"><span style="position: absolute; clip: rect(3.373em, 1000.49em, 4.354em, -999.997em); top: -3.98em; left: 0em;"><span class="mi" id="MathJax-Span-199" style="font-family: MathJax_Math-italic;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; top: -4.409em; left: 0.555em;"><span class="mn" id="MathJax-Span-200" style="font-size: 70.7%; font-family: MathJax_Main;">2</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1006.13em, 4.415em, -999.997em); top: -4.531em; right: 0em;"><span class="mtd" id="MathJax-Span-214"><span class="mrow" id="MathJax-Span-215"><span class="mo" id="MathJax-Span-216" style="font-family: MathJax_Main;">(</span><span class="mi" id="MathJax-Span-217" style="font-family: MathJax_Math-italic;">x</span><span class="mo" id="MathJax-Span-218" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="mi" id="MathJax-Span-219" style="font-family: MathJax_Math-italic; padding-left: 0.248em;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span><span class="mo" id="MathJax-Span-220" style="font-family: MathJax_Main;">)</span><span class="mo" id="MathJax-Span-221" style="font-family: MathJax_Main;">(</span><span class="mi" id="MathJax-Span-222" style="font-family: MathJax_Math-italic;">x</span><span class="mo" id="MathJax-Span-223" style="font-family: MathJax_Main; padding-left: 0.248em;">+</span><span class="mi" id="MathJax-Span-224" style="font-family: MathJax_Math-italic; padding-left: 0.248em;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span><span class="mo" id="MathJax-Span-225" style="font-family: MathJax_Main;">)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1003.01em, 4.415em, -999.997em); top: -3.183em; right: 0em;"><span class="mtd" id="MathJax-Span-239"><span class="mrow" id="MathJax-Span-240"><span class="mo" id="MathJax-Span-241" style="font-family: MathJax_Main;">(</span><span class="mi" id="MathJax-Span-242" style="font-family: MathJax_Math-italic;">x</span><span class="mo" id="MathJax-Span-243" style="font-family: MathJax_Main; padding-left: 0.248em;">+</span><span class="mi" id="MathJax-Span-244" style="font-family: MathJax_Math-italic; padding-left: 0.248em;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span><span class="mo" id="MathJax-Span-245" style="font-family: MathJax_Main;">)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.128em, 1000.98em, 4.354em, -999.997em); top: -1.835em; right: 0em;"><span class="mtd" id="MathJax-Span-254"><span class="mrow" id="MathJax-Span-255"><span class="mn" id="MathJax-Span-256" style="font-family: MathJax_Main;">2</span><span class="mi" id="MathJax-Span-257" style="font-family: MathJax_Math-italic;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.128em, 1000.43em, 4.17em, -999.997em); top: -0.487em; right: 0em;"><span class="mtd" id="MathJax-Span-266"><span class="mrow" id="MathJax-Span-267"><span class="mn" id="MathJax-Span-268" style="font-family: MathJax_Main;">2</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span><span style="display: inline-block; width: 0px; height: 8.704em;"></span></span><span style="position: absolute; clip: rect(4.292em, 1005.03em, 11.952em, -999.997em); top: -8.269em; left: 6.253em;"><span style="display: inline-block; position: relative; width: 5.028em; height: 0px;"><span style="position: absolute; clip: rect(3.373em, 1002.45em, 4.354em, -999.997em); top: -7.35em; left: 0em;"><span class="mtd" id="MathJax-Span-183"><span class="mrow" id="MathJax-Span-184"><span class="mi" id="MathJax-Span-185"></span><span class="mo" id="MathJax-Span-186" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mi" id="MathJax-Span-187" style="font-family: MathJax_Math-italic; padding-left: 0.309em;">x</span><span class="mi" id="MathJax-Span-188" style="font-family: MathJax_Math-italic;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(2.944em, 1004.72em, 4.354em, -999.997em); top: -5.879em; left: 0em;"><span class="mtd" id="MathJax-Span-201"><span class="mrow" id="MathJax-Span-202"><span class="mi" id="MathJax-Span-203"></span><span class="mo" id="MathJax-Span-204" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mi" id="MathJax-Span-205" style="font-family: MathJax_Math-italic; padding-left: 0.309em;">x</span><span class="mi" id="MathJax-Span-206" style="font-family: MathJax_Math-italic;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span><span class="mo" id="MathJax-Span-207" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="msubsup" id="MathJax-Span-208" style="padding-left: 0.248em;"><span style="display: inline-block; position: relative; width: 0.983em; height: 0px;"><span style="position: absolute; clip: rect(3.373em, 1000.49em, 4.354em, -999.997em); top: -3.98em; left: 0em;"><span class="mi" id="MathJax-Span-209" style="font-family: MathJax_Math-italic;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; top: -4.409em; left: 0.555em;"><span class="mn" id="MathJax-Span-210" style="font-size: 70.7%; font-family: MathJax_Main;">2</span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1005.03em, 4.415em, -999.997em); top: -4.531em; left: 0em;"><span class="mtd" id="MathJax-Span-226"><span class="mrow" id="MathJax-Span-227"><span class="mi" id="MathJax-Span-228"></span><span class="mo" id="MathJax-Span-229" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mo" id="MathJax-Span-230" style="font-family: MathJax_Main; padding-left: 0.309em;">(</span><span class="mi" id="MathJax-Span-231" style="font-family: MathJax_Math-italic;">x</span><span class="mo" id="MathJax-Span-232" style="font-family: MathJax_Main; padding-left: 0.248em;">−</span><span class="mi" id="MathJax-Span-233" style="font-family: MathJax_Math-italic; padding-left: 0.248em;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span><span class="mo" id="MathJax-Span-234" style="font-family: MathJax_Main;">)</span><span class="mi" id="MathJax-Span-235" style="font-family: MathJax_Math-italic;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.373em, 1001.9em, 4.354em, -999.997em); top: -3.183em; left: 0em;"><span class="mtd" id="MathJax-Span-246"><span class="mrow" id="MathJax-Span-247"><span class="mi" id="MathJax-Span-248"></span><span class="mo" id="MathJax-Span-249" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mi" id="MathJax-Span-250" style="font-family: MathJax_Math-italic; padding-left: 0.309em;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.373em, 1001.9em, 4.354em, -999.997em); top: -1.835em; left: 0em;"><span class="mtd" id="MathJax-Span-258"><span class="mrow" id="MathJax-Span-259"><span class="mi" id="MathJax-Span-260"></span><span class="mo" id="MathJax-Span-261" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mi" id="MathJax-Span-262" style="font-family: MathJax_Math-italic; padding-left: 0.309em;">y<span style="display: inline-block; overflow: hidden; height: 1px; width: 0.003em;"></span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.128em, 1002.09em, 4.17em, -999.997em); top: -0.487em; left: 0em;"><span class="mtd" id="MathJax-Span-269"><span class="mrow" id="MathJax-Span-270"><span class="mi" id="MathJax-Span-271"></span><span class="mo" id="MathJax-Span-272" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mn" id="MathJax-Span-273" style="font-family: MathJax_Main; padding-left: 0.309em;">1.</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span><span style="display: inline-block; width: 0px; height: 8.275em;"></span></span></span><span style="display: inline-block; position: absolute; width: 1.29em; height: 0px; clip: rect(-4.286em, 1001.17em, 3.925em, -999.997em); top: 0em; right: 0em; margin-right: 0em;"><span style="position: absolute; clip: rect(3.067em, 1001.17em, 4.415em, -999.997em); top: -7.35em; right: 0em;"><span class="mtd" id="mjx-eqn-1"><span class="mrow" id="MathJax-Span-176"><span class="mtext" id="MathJax-Span-177" style="font-family: MathJax_Main;">(1)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1001.17em, 4.415em, -999.997em); top: -5.879em; right: 0em;"><span class="mtd" id="mjx-eqn-2"><span class="mrow" id="MathJax-Span-190"><span class="mtext" id="MathJax-Span-191" style="font-family: MathJax_Main;">(2)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1001.17em, 4.415em, -999.997em); top: -4.531em; right: 0em;"><span class="mtd" id="mjx-eqn-3"><span class="mrow" id="MathJax-Span-212"><span class="mtext" id="MathJax-Span-213" style="font-family: MathJax_Main;">(3)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1001.17em, 4.415em, -999.997em); top: -3.183em; right: 0em;"><span class="mtd" id="mjx-eqn-4"><span class="mrow" id="MathJax-Span-237"><span class="mtext" id="MathJax-Span-238" style="font-family: MathJax_Main;">(4)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1001.17em, 4.415em, -999.997em); top: -1.835em; right: 0em;"><span class="mtd" id="mjx-eqn-5"><span class="mrow" id="MathJax-Span-252"><span class="mtext" id="MathJax-Span-253" style="font-family: MathJax_Main;">(5)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span><span style="position: absolute; clip: rect(3.067em, 1001.17em, 4.415em, -999.997em); top: -0.487em; right: 0em;"><span class="mtd" id="mjx-eqn-6"><span class="mrow" id="MathJax-Span-264"><span class="mtext" id="MathJax-Span-265" style="font-family: MathJax_Main;">(6)</span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 8.949em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -3.872em; border-left: 0px solid; width: 0px; height: 8.253em;"></span></span></nobr><span class="MJX_Assistive_MathML MJX_Assistive_MathML_Block" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mtable columnalign="right left right left right left right left right left right left" rowspacing="3pt" columnspacing="0em 2em 0em 2em 0em 2em 0em 2em 0em 2em 0em" displaystyle="true"><mlabeledtr><mtd id="mjx-eqn-1"><mtext>(1)</mtext></mtd><mtd><msup><mi>x</mi><mn>2</mn></msup></mtd><mtd><mi></mi><mo>=</mo><mi>x</mi><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id="mjx-eqn-2"><mtext>(2)</mtext></mtd><mtd><msup><mi>x</mi><mn>2</mn></msup><mo>−</mo><msup><mi>y</mi><mn>2</mn></msup></mtd><mtd><mi></mi><mo>=</mo><mi>x</mi><mi>y</mi><mo>−</mo><msup><mi>y</mi><mn>2</mn></msup></mtd></mlabeledtr><mlabeledtr><mtd id="mjx-eqn-3"><mtext>(3)</mtext></mtd><mtd><mo stretchy="false">(</mo><mi>x</mi><mo>−</mo><mi>y</mi><mo stretchy="false">)</mo><mo stretchy="false">(</mo><mi>x</mi><mo>+</mo><mi>y</mi><mo stretchy="false">)</mo></mtd><mtd><mi></mi><mo>=</mo><mo stretchy="false">(</mo><mi>x</mi><mo>−</mo><mi>y</mi><mo stretchy="false">)</mo><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id="mjx-eqn-4"><mtext>(4)</mtext></mtd><mtd><mo stretchy="false">(</mo><mi>x</mi><mo>+</mo><mi>y</mi><mo stretchy="false">)</mo></mtd><mtd><mi></mi><mo>=</mo><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id="mjx-eqn-5"><mtext>(5)</mtext></mtd><mtd><mn>2</mn><mi>y</mi></mtd><mtd><mi></mi><mo>=</mo><mi>y</mi></mtd></mlabeledtr><mlabeledtr><mtd id="mjx-eqn-6"><mtext>(6)</mtext></mtd><mtd><mn>2</mn></mtd><mtd><mi></mi><mo>=</mo><mn>1.</mn></mtd></mlabeledtr></mtable></math></span></span></div><script type="math/tex; mode=display" id="MathJax-Element-13">\begin{align} x^2 & = xy \\ x^2 - y^2 & = xy - y^2 \\ (x-y)(x+y) & = (x-y)y \\ (x+y) & = y \\ 2y & = y \\ 2 & =1. \end{align}</script></div>
<!--  l. 68  --><p class="noindent">Where is the mistake in the work above?  </p><div class="mathjax-block"><div class="MathJax_Display" style="text-align: center;"><span class="MathJax" id="MathJax-Element-14-Frame" tabindex="0" style="text-align: center; position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtext>Between line&amp;#xA0;</mtext><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mn>3</mn></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input narrow&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; style=&quot;width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /><mtext>&amp;#xA0;and line&amp;#xA0;</mtext><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mn>4</mn></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input narrow&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; style=&quot;width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /><mo>.</mo></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-274" style="width: 18.937em; display: inline-block;"><span style="display: inline-block; position: relative; width: 18.569em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(2.27em, 1018.51em, 6.192em, -999.997em); top: -4.531em; left: 0em;"><span class="mrow" id="MathJax-Span-275"><span class="mtext" id="MathJax-Span-276" style="font-family: MathJax_Main;">Between line&nbsp;</span><span class="mpadded" id="MathJax-Span-277"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-278"><span class="mphantom" id="MathJax-Span-279"><span class="mrow" id="MathJax-Span-280" style="visibility: hidden;"><span class="mn" id="MathJax-Span-281" style="font-family: MathJax_Main;">3</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-282"><span class="annotation-xml" id="MathJax-Span-283" style="font-size: 98%;"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer0problem3" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-284"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-285"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="mtext" id="MathJax-Span-286" style="font-family: MathJax_Main;">&nbsp;and line&nbsp;</span><span class="mpadded" id="MathJax-Span-287"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-288"><span class="mphantom" id="MathJax-Span-289"><span class="mrow" id="MathJax-Span-290" style="visibility: hidden;"><span class="mn" id="MathJax-Span-291" style="font-family: MathJax_Main;">4</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-292"><span class="annotation-xml" id="MathJax-Span-293" style="font-size: 98%;"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer1problem3" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-294"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-295"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="mo" id="MathJax-Span-296" style="font-family: MathJax_Main;">.</span></span><span style="display: inline-block; width: 0px; height: 4.537em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -1.559em; border-left: 0px solid; width: 0px; height: 3.753em;"></span></span></nobr><span class="MJX_Assistive_MathML MJX_Assistive_MathML_Block" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mtext>Between line&nbsp;</mtext><mpadded width="0" height="0"><mphantom><mn>3</mn></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded><mtext>&nbsp;and line&nbsp;</mtext><mpadded width="0" height="0"><mphantom><mn>4</mn></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded><mo>.</mo></math></span></span></div><script type="math/tex; mode=display" id="MathJax-Element-14"> \text {Between line }\answer {3} \text { and line }\answer {4}. </script></div>  </div>
<!--  l. 77  -->
<h3 class="sectionHead" id="basic-exercises"><span class="titlemark">3   </span> <a id="x1-30003"></a>Basic exercises</h3>
<!--  l. 79  --><p class="noindent">After that, you might want to have some exercises. You will not find any inspiration
in the above <a href="#x1-1001r1">definition of the absolute value</a>.
</p>
<div class="problem-environment exercise" id="problem4" role="article" style="visibility: visible; position: relative; opacity: 1;" data-answer-count="1" data-blocking="true"><a id="x1-3001r4"></a> Let <span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-15-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>x</mi></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-297" style="width: 0.555em; display: inline-block;"><span style="display: inline-block; position: relative; width: 0.555em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.535em, 1000.49em, 2.331em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-298"><span class="mi" id="MathJax-Span-299" style="font-family: MathJax_Math-italic;">x</span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.059em; border-left: 0px solid; width: 0px; height: 0.566em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span></span><script type="math/tex" id="MathJax-Element-15">x</script></span> be the number of people out of <span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-16-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mn>100</mn></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-300" style="width: 1.535em; display: inline-block;"><span style="display: inline-block; position: relative; width: 1.474em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.29em, 1001.41em, 2.331em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-301"><span class="mn" id="MathJax-Span-302" style="font-family: MathJax_Main;">100</span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.059em; border-left: 0px solid; width: 0px; height: 0.816em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mn>100</mn></math></span></span><script type="math/tex" id="MathJax-Element-16">100</script></span> that LOVE Ximera.
<!--  l. 86  --><p class="noindent">Find the value of <span class="mathjax-inline"><span class="MathJax" id="MathJax-Element-17-Frame" tabindex="0" style="position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot;><mi>x</mi></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-303" style="width: 0.555em; display: inline-block;"><span style="display: inline-block; position: relative; width: 0.555em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(1.535em, 1000.49em, 2.331em, -999.997em); top: -2.142em; left: 0em;"><span class="mrow" id="MathJax-Span-304"><span class="mi" id="MathJax-Span-305" style="font-family: MathJax_Math-italic;">x</span></span><span style="display: inline-block; width: 0px; height: 2.148em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -0.059em; border-left: 0px solid; width: 0px; height: 0.566em;"></span></span></nobr><span class="MJX_Assistive_MathML" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML"><mi>x</mi></math></span></span><script type="math/tex" id="MathJax-Element-17">x</script></span>. </p><div class="mathjax-block"><div class="MathJax_Display" style="text-align: center;"><span class="MathJax" id="MathJax-Element-18-Frame" tabindex="0" style="text-align: center; position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mi>x</mi><mo>=</mo><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mn>100</mn></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input narrow&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; style=&quot;width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-306" style="width: 6.376em; display: inline-block;"><span style="display: inline-block; position: relative; width: 6.253em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(2.27em, 1006.25em, 6.192em, -999.997em); top: -4.531em; left: 0em;"><span class="mrow" id="MathJax-Span-307"><span class="mi" id="MathJax-Span-308" style="font-family: MathJax_Math-italic;">x</span><span class="mo" id="MathJax-Span-309" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mpadded" id="MathJax-Span-310" style="padding-left: 0.309em;"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-311"><span class="mphantom" id="MathJax-Span-312"><span class="mrow" id="MathJax-Span-313" style="visibility: hidden;"><span class="mn" id="MathJax-Span-314" style="font-family: MathJax_Main;">100</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-315"><span class="annotation-xml" id="MathJax-Span-316" style="font-size: 98%;"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer0problem4" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-317"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-318"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 4.537em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -1.559em; border-left: 0px solid; width: 0px; height: 3.753em;"></span></span></nobr><span class="MJX_Assistive_MathML MJX_Assistive_MathML_Block" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi>x</mi><mo>=</mo><mpadded width="0" height="0"><mphantom><mn>100</mn></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input narrow" xmlns="http://www.w3.org/1999/xhtml" style="width: 70px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded></math></span></span></div><script type="math/tex; mode=display" id="MathJax-Element-18"> x = \answer {100} </script></div> </div>
<!--  l. 92  --><p class="noindent">Maybe you want a problem with one or more parts,
</p>
<div class="problem-environment exercise" id="problem5" role="article" style="visibility: visible; position: relative; opacity: 1;" data-blocking="true"><a id="x1-3002r5"></a> Ximera is so awesome because it feels like: <div class="multiple-choice" id="problem6"><div class="ximera-horizontal"><div class="btn-group-vertical" role="group" data-toggle="buttons" style="padding-right: 1em;"><button class="text-left btn btn-secondary" id="choice1"><span class="choice  "><input type="radio">Doing taxes </span></button><button class="text-left btn btn-secondary" id="choice2"><span class="choice  "><input type="radio">Writing a book by hand </span></button><button class="text-left btn btn-secondary correct" id="choice3"><span class="choice correct
"><input type="radio">A walk in the park with free ice cream </span></button><button class="text-left btn btn-secondary" id="choice4"><span class="choice  "><input type="radio">Solving a puzzle blindfolded</span></button> </div><div class="btn-group" style="vertical-align: bottom; " aria-live="assertive"><button class="btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none"><i class="fa fa-check"></i>&nbsp;Correct</button></div><div class="btn-group" style="vertical-align: bottom; " aria-live="assertive"><button class="btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none" disabled=""><i class="fa fa-times"></i>&nbsp;Try again</button></div><div class="btn-group" style="vertical-align: bottom; "><button class="btn btn-primary btn-ximera-submit" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="" disabled=""><i class="fa fa-question"></i>&nbsp;Check work</button></div></div></div> <div class="problem-environment exercise" id="problem7" role="article" style="visibility: hidden; position: absolute; opacity: 1;" data-blocking="true"><a id="x1-3003r6"></a> Why is
Ximera the best thing since the chalkboard? <div class="select-all" id="problem8"><div class="ximera-horizontal"><div class="btn-group-vertical" role="group" data-toggle="buttons" style="padding-right: 1em;"><a id="x1-3004r7"></a> <button class="btn text-left btn-secondary correct" id="choice5"><span class="choice correct " id="choice5"><input type="checkbox">It turns LaTeX into online materials </span></button><button class="btn text-left btn-secondary correct" id="choice6"><span class="choice correct " id="choice6"><input type="checkbox">It boosts student engagement </span></button><button class="btn text-left btn-secondary" id="choice7"><span class="choice  " id="choice7"><input type="checkbox">It makes coffee and hugs you </span></button><button class="btn text-left btn-secondary correct" id="choice8"><span class="choice correct " id="choice8"><input type="checkbox">Its open-source and
free</span></button> </div><div class="btn-group" style="vertical-align: bottom; " aria-live="assertive"><button class="btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none"><i class="fa fa-check"></i>&nbsp;Correct</button></div><div class="btn-group" style="vertical-align: bottom; " aria-live="assertive"><button class="btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none" disabled=""><i class="fa fa-times"></i>&nbsp;Try again</button></div><div class="btn-group" style="vertical-align: bottom; "><button class="btn btn-primary btn-ximera-submit" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="" disabled=""><i class="fa fa-question"></i>&nbsp;Check work</button></div></div></div> </div> </div>
<!--  l. 113  --><p class="noindent">Finally we can include pictures using <span class="obeylines-h"><code class="verb">includegraphics</code></span>. Here’s an example of a
question with a picture. </p><div class="problem-environment question" id="problem9" role="article" style="visibility: visible; position: relative; opacity: 1;" data-answer-count="1" data-blocking="true"><button class="btn btn-info btn-reveal-hint" type="button" data-toggle="tooltip" data-placement="top" title="Reveal the next hint."><i class="fa fa-life-ring"></i>&nbsp; Reveal Hint<span class="counter" style="display: none;"> (<span class="count">1</span> of <span class="total">3</span>)</span><span class="hint-locked" style="display: none;"><span class="countdown" style="display: none;"> (<i class="fa fa-lock"></i> <span class="seconds-remaining">0</span>)</span><span class="hint-unlocked" style=""> <i class="fa fa-unlock"></i></span></span></button><a id="x1-3005r8"></a> Here is a picture of the Ximera Octolion:
<div class="center">
<!--  l. 116  --><!--  l. 117  --><p class="noindent"><img alt="PIC" height="142" src="../xmPictures/missionPatch.jpg" width="142"></p></div>
                                                                  

                                                                  
<!--  l. 119  --><p class="noindent">What’s their name? </p><div class="mathjax-block"><div class="MathJax_Display" style="text-align: center;"><span class="MathJax" id="MathJax-Element-19-Frame" tabindex="0" style="text-align: center; position: relative;" data-mathml="<math xmlns=&quot;http://www.w3.org/1998/Math/MathML&quot; display=&quot;block&quot;><mtext>Name</mtext><mo>=</mo><mpadded width=&quot;0&quot; height=&quot;0&quot;><mphantom><mtext>Xarlie</mtext></mphantom></mpadded><semantics><annotation-xml encoding=&quot;application/xhtml+xml&quot;><form class=&quot;form-inline mathjaxed-input&quot; xmlns=&quot;http://www.w3.org/1999/xhtml&quot; data-format=&quot;string&quot; style=&quot;width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;&quot;><div class=&quot;input-group&quot;><input class=&quot;form-control&quot; aria-label=&quot;answer&quot; type=&quot;text&quot;><span class=&quot;input-group-btn&quot;><button class=&quot;px-0 btn btn-success btn-ximera-correct&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Correct answer!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;correct answer&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-check&quot;></i></button><button class=&quot;px-0 btn btn-danger btn-ximera-incorrect&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Incorrect.  Try again!&quot; style=&quot;display: none; z-index: 1;&quot; aria-label=&quot;incorrect!  try again&quot; aria-live=&quot;assertive&quot;><i class=&quot;fa fa-fw fa-times&quot;></i></button><button class=&quot;px-0 btn btn-primary disabled btn-ximera-checking&quot; aria-label=&quot;evaluating your work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Evaluating your work...&quot; style=&quot;z-index: 1; display: none;&quot;><i class=&quot;fa fa-fw fa-spinner fa-spin&quot;></i></button><button class=&quot;px-0 btn btn-primary btn-ximera-submit&quot; aria-label=&quot;check work&quot; data-toggle=&quot;tooltip&quot; data-placement=&quot;top&quot; title=&quot;Click to check your answer.&quot; style=&quot;z-index: 1;&quot;><i class=&quot;fa fa-fw fa-question&quot;></i></button></span></div></form></annotation-xml></semantics><mpadded width=&quot;0&quot; height=&quot;30px&quot; /></math>" role="presentation"><nobr aria-hidden="true"><span class="math" id="MathJax-Span-319" style="width: 13.729em; display: inline-block;"><span style="display: inline-block; position: relative; width: 13.422em; height: 0px; font-size: 102%;"><span style="position: absolute; clip: rect(2.27em, 1013.42em, 6.192em, -999.997em); top: -4.531em; left: 0em;"><span class="mrow" id="MathJax-Span-320"><span class="mtext" id="MathJax-Span-321" style="font-family: MathJax_Main;">Name</span><span class="mo" id="MathJax-Span-322" style="font-family: MathJax_Main; padding-left: 0.309em;">=</span><span class="mpadded" id="MathJax-Span-323" style="padding-left: 0.309em;"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.128em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-324"><span class="mphantom" id="MathJax-Span-325"><span class="mrow" id="MathJax-Span-326" style="visibility: hidden;"><span class="mtext" id="MathJax-Span-327" style="font-family: MathJax_Main;">Xarlie</span></span></span></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span><span class="semantics" id="MathJax-Span-328"><span class="annotation-xml" id="MathJax-Span-329" style="font-size: 98%;"><form class="form-inline mathjaxed-input" xmlns="http://www.w3.org/1999/xhtml" data-format="string" style="width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;" id="answer0problem9" data-original-title="" title=""><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></span></span><span class="mpadded" id="MathJax-Span-330"><span style="display: inline-block; position: relative; width: 0em; height: 0px;"><span style="position: absolute; clip: rect(3.802em, 1000em, 4.17em, -999.997em); top: -3.98em; left: 0em;"><span class="mrow" id="MathJax-Span-331"></span><span style="display: inline-block; width: 0px; height: 3.986em;"></span></span></span></span></span><span style="display: inline-block; width: 0px; height: 4.537em;"></span></span></span><span style="display: inline-block; overflow: hidden; vertical-align: -1.559em; border-left: 0px solid; width: 0px; height: 3.753em;"></span></span></nobr><span class="MJX_Assistive_MathML MJX_Assistive_MathML_Block" role="presentation"><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mtext>Name</mtext><mo>=</mo><mpadded width="0" height="0"><mphantom><mtext>Xarlie</mtext></mphantom></mpadded><semantics><annotation-xml encoding="application/xhtml+xml"><form class="form-inline mathjaxed-input" xmlns="http://www.w3.org/1999/xhtml" data-format="string" style="width: 155px; margin-bottom: 10px; margin-top: 10px; display: inline-block;"><div class="input-group"><input class="form-control" aria-label="answer" type="text"><span class="input-group-btn"><button class="px-0 btn btn-success btn-ximera-correct" data-toggle="tooltip" data-placement="top" title="Correct answer!" style="display: none; z-index: 1;" aria-label="correct answer" aria-live="assertive"><i class="fa fa-fw fa-check"></i></button><button class="px-0 btn btn-danger btn-ximera-incorrect" data-toggle="tooltip" data-placement="top" title="Incorrect.  Try again!" style="display: none; z-index: 1;" aria-label="incorrect!  try again" aria-live="assertive"><i class="fa fa-fw fa-times"></i></button><button class="px-0 btn btn-primary disabled btn-ximera-checking" aria-label="evaluating your work" data-toggle="tooltip" data-placement="top" title="Evaluating your work..." style="z-index: 1; display: none;"><i class="fa fa-fw fa-spinner fa-spin"></i></button><button class="px-0 btn btn-primary btn-ximera-submit" aria-label="check work" data-toggle="tooltip" data-placement="top" title="Click to check your answer." style="z-index: 1;"><i class="fa fa-fw fa-question"></i></button></span></div></form></annotation-xml></semantics><mpadded width="0" height="30px"></mpadded></math></span></span></div><script type="math/tex; mode=display" id="MathJax-Element-19"> \text {Name} = \answer [format=string]{Xarlie} </script></div> <button class="btn btn-info btn-xs btn-hint-collapse" type="button" aria-expanded="false" aria-controls="collapse" style="display: none;"><i class="fa fa-chevron-down"></i></button><div class="problem-environment hint collapse" id="problem10" role="article" aria-expanded="false"><a id="x1-3006r9"></a> Their name begins with an “X.” </div> <button class="btn btn-info btn-xs btn-hint-collapse" type="button" aria-expanded="false" aria-controls="collapse" style="display: none;"><i class="fa fa-chevron-down"></i></button><div class="problem-environment hint collapse" id="problem11" role="article" aria-expanded="false"><a id="x1-3007r10"></a> It ends with an “arlie.” </div> <button class="btn btn-info btn-xs btn-hint-collapse" type="button" aria-expanded="false" aria-controls="collapse" style="display: none;"><i class="fa fa-chevron-down"></i></button><div class="problem-environment hint collapse" id="problem12" role="article" aria-expanded="false"><a id="x1-3008r11"></a> It’s
almost Karlie! </div> </div>
<!--  l. 134  --><p class="noindent">We include JPGs and PDFs in exactly the same way.
</p>
            <nav class="my-4" aria-label="page navigation"><ul class="pagination justify-content-start"><li class="page-item disabled" id="previous-activity"><span class="page-link" aria-label="previous activity" href="#">             ← Previous</span></li><li class="page-item ml-auto" id="next-activity" completion-blink="" aria-label="next activity"><a class="page-link" href="/johnweeks03-test/aFirstXourse/aFirstFolder/exercises/someExercises"><span id="next-activity-label">Next</span> →</a></li></ul></nav></div></main></div></div><svg id="pencil" style="position: absolute; top: 0px; left: 0px; width: 100%; height: 100%; overflow: visible; z-index: 1029; pointer-events: none;"></svg></div><footer class="bg-inverse text-white"><div class="container"><div class="row"><div class="col-md-3 hidden-sm-down"><h5><a href="/mooculus/">Courses</a></h5><ul><a href="/mooculus/calculus1">Calculus One</a><a href="/mooculus/calculus2">Calculus Two</a><a href="/mooculus/calculus3">Calculus Three</a></ul></div><div class="col-md-3"><h5 class="hidden-sm-down"><a href="/about/overview">About</a></h5><ul><a href="/about/faq">FAQ</a><a href="/about/team">Development Team</a><a href="/about/workshop">Workshop</a><a href="/about/contact">Contact Us <i class="fa fa-envelope">           </i></a></ul></div><div class="col-md-3 hidden-sm-down"><h5>Social</h5><ul><a href="http://www.facebook.com/sharer.php?u=https://ximera.osu.edu/johnweeks03-test/aFirstXourse/aFirstFolder/aFirstActivity">Facebook <i class="fa fa-facebook"></i></a><a href="http://twitter.com/intent/tweet?status=https://ximera.osu.edu/johnweeks03-test/aFirstXourse/aFirstFolder/aFirstActivity @XimeraProject">Twitter <i class="fa fa-twitter"></i></a><a href="https://plus.google.com/share?url=https://ximera.osu.edu/johnweeks03-test/aFirstXourse/aFirstFolder/aFirstActivity">Google Plus <i class="fa fa-google-plus"></i></a><a href="https://github.com/kisonecat/ximera">GitHub <i class="fa fa-github-alt"></i></a></ul></div><div class="col-md-3 address hidden-sm-down"><p>Built at <a href="http://www.osu.edu/"><span class="hidden-md-down">The Ohio State University</span><span class="hidden-lg-up">OSU</span></a> with <a href="/about/support">support from</a> <a href="http://www.nsf.gov/awardsearch/showAward?AWD_ID=1245433">NSF Grant DUE-1245433</a>, <span class="hidden-md-down">the</span> <a href="/about/support">Shuttleworth<span class="hidden-md-down"> Foundation</span></a>, <span class="hidden-md-down">the <a href="http://math.osu.edu/">Department of Mathematics</a>,</span> and <span class="hidden-md-down">the <a href="https://affordablelearning.osu.edu/">Affordable Learning Exchange</a></span><span class="hidden-lg-up"><a href="https://affordablelearning.osu.edu/">ALX</a></span>.</p></div></div><div class="row"><div class="col-md-12 osu"><img class="hidden-sm-down" src="/public/v1.8.1/images/osu/osu-web-footer-wordmark-rev.png"><p>© 2013–2025, The Ohio State University <span class="hidden-xs-down">— <a href="/about/team">Ximera team</a></span></p><p class="hidden-xs-down">100 Math Tower, 231 West 18th Avenue, Columbus OH, 43210–1174</p><p class="hidden-xs-down">Phone: (773) 809–5659 | <a href="/about/contact">Contact</a></p><p>If you have trouble accessing this page and need to request an alternate format, contact <a href="mailto:ximera@math.osu.edu">ximera@math.osu.edu</a>.</p></div></div></div></footer><script src="//browser-update.org/update.min.js" style="display: none !important;"></script><div class="guppy_help" style="padding: 10px; border: 1px solid black; background-color: rgb(255, 255, 255); position: absolute; top: 0px; left: 0px; display: none;"><p>Start typing the name of a mathematical function to automatically insert it.  </p><p>(For example, "sqrt" for root, "mat" for matrix, or "defi" for definite integral.)</p>
<style>div.guppy_help td{ vertical-align:top;padding: 2px;}</style>
<h3>Controls</h3><table id="guppy_help_table"><tbody><tr><td><b>Press...</b></td><td><b>...to do</b></td></tr></tbody><tr><td><font face="monospace">left/right arrows</font></td><td>Move cursor</td></tr><tr><td><font face="monospace">shift+left/right arrows</font></td><td>Select region</td></tr><tr><td><font face="monospace">ctrl+a</font></td><td>Select all</td></tr><tr><td><font face="monospace">ctrl+x/c/v</font></td><td>Cut/copy/paste</td></tr><tr><td><font face="monospace">ctrl+z/y</font></td><td>Undo/redo</td></tr><tr><td><font face="monospace">ctrl+left/right</font></td><td>Add entry to list or column to matrix</td></tr><tr><td><font face="monospace">shift+ctrl+left/right</font></td><td>Add copy of current entry/column to to list/matrix</td></tr><tr><td><font face="monospace">ctrl+up/down</font></td><td>Add row to matrix</td></tr><tr><td><font face="monospace">shift+ctrl+up/down</font></td><td>Add copy of current row to matrix</td></tr><tr><td><font face="monospace">ctrl+backspace</font></td><td>Delete current entry in list or column in matrix</td></tr><tr><td><font face="monospace">ctrl+shift+backspace</font></td><td>Delete current row in matrix</td></tr></table><div class="guppy-card-x" style="cursor: pointer; position: absolute; top: 0px; right: 0px; padding-right: 5px; line-height: 1;"><font size="6pt">×</font></div></div><div class="guppy_help" style="padding: 10px; border: 1px solid black; background-color: rgb(255, 255, 255); position: absolute; top: 0px; left: 0px; display: none;"><p>Start typing the name of a mathematical function to automatically insert it.  </p><p>(For example, "sqrt" for root, "mat" for matrix, or "defi" for definite integral.)</p>
<style>div.guppy_help td{ vertical-align:top;padding: 2px;}</style>
<h3>Symbols</h3><table id="guppy_syms_table"><tbody><tr><td><b>Type...</b></td><td><b>...to get</b></td></tr></tbody><tr><td><font face="monospace">norm</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">∣</mi><mi mathvariant="normal">∣</mi><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mi mathvariant="normal">∣</mi><mi mathvariant="normal">∣</mi></mrow><annotation encoding="application/x-tex">||\blue{[?]}||</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mord">∣</span><span class="mord">∣</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mord">∣</span><span class="mord">∣</span></span></span></span></td></tr><tr><td><font face="monospace">text</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mstyle mathcolor="katex-blue"><mtext>[</mtext><mtext>?</mtext><mtext>]</mtext></mstyle></mrow><annotation encoding="application/x-tex">\text{\blue{[?]}}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mord text"><span class="mord" style="color: rgb(100, 149, 237);">[?]</span></span></span></span></span></td></tr><tr><td><font face="monospace">sym_name</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">\</mi><mstyle mathcolor="katex-blue"><mtext>[</mtext><mtext>?</mtext><mtext>]</mtext></mstyle></mrow><annotation encoding="application/x-tex">\backslash\texttt{\blue{[?]}}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mord">\</span><span class="mord text"><span class="mord texttt" style="color: rgb(100, 149, 237);">[?]</span></span></span></span></span></td></tr><tr><td><font face="monospace">abs</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mrow><mo fence="true">∣</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">∣</mo></mrow></mrow><annotation encoding="application/x-tex">\left|\blue{[?]}\right|</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="minner"><span class="mopen delimcenter" style="top: 0em;">∣</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">∣</span></span></span></span></span></td></tr><tr><td><font face="monospace">sqrt</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><msqrt><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow></msqrt></mrow><annotation encoding="application/x-tex">\sqrt{\blue{[?]}}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.935em;"></span><span class="strut bottom" style="height: 1.24em; vertical-align: -0.305em;"></span><span class="base"><span class="mord sqrt"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist svg-align" style="height: 0.935em;"><span class="" style="top: -3.2em;"><span class="pstrut" style="height: 3.2em;"></span><span class="mord" style="padding-left: 1em;"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span><span class="" style="top: -2.895em;"><span class="pstrut" style="height: 3.2em;"></span><span class="hide-tail" style="min-width: 1.02em; height: 1.2em;"><svg class="" width="400em" height="1.2em" viewBox="0 0 400000 1200" preserveAspectRatio="xMinYMin slice"><path d="M263 601c.667 0 18 39.667 52 119s68.167
 158.667 102.5 238 51.833 119.333 52.5 120C810 373.333 980.667 17.667 982 11
c4.667-7.333 11-11 19-11h398999v40H1012.333L741 607c-38.667 80.667-84 175-136
 283s-89.167 185.333-111.5 232-33.833 70.333-34.5 71c-4.667 4.667-12.333 7-23
 7l-12-1-109-253c-72.667-168-109.333-252-110-252-10.667 8-22 16.667-34 26-22
 17.333-33.333 26-34 26l-26-26 76-59 76-60zM1001 0h398999v40H1012z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.305em;"></span></span></span></span></span></span></span></td></tr><tr><td><font face="monospace">paren</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">floor</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mo>⌊</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo>⌋</mo></mrow><annotation encoding="application/x-tex">\lfloor \blue{[?]} \rfloor</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mopen">⌊</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose">⌋</span></span></span></span></td></tr><tr><td><font face="monospace">factorial</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo>!</mo></mrow><annotation encoding="application/x-tex">\blue{[?]}!</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose">!</span></span></span></span></td></tr><tr><td><font face="monospace">exp</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><msup><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></msup></mrow><annotation encoding="application/x-tex">{\blue{[?]}}^{\blue{[?]}}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 1.0279em;"></span><span class="strut bottom" style="height: 1.2779em; vertical-align: -0.25em;"></span><span class="base"><span class="mord"><span class="mord"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span><span class="msupsub"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 1.0279em;"><span class="" style="top: -3.2029em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span></span></span></span></span></span></span></span></span></td></tr><tr><td><font face="monospace">sub</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><msub><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></msub></mrow><annotation encoding="application/x-tex">{\blue{[?]}}_{\blue{[?]}}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1.2247em; vertical-align: -0.4747em;"></span><span class="base"><span class="mord"><span class="mord"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.2253em;"><span class="" style="top: -2.4003em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.4747em;"></span></span></span></span></span></span></span></span></td></tr><tr><td><font face="monospace">frac</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mfrac><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow></mfrac></mrow><annotation encoding="application/x-tex">\dfrac{\blue{[?]}}{\blue{[?]}}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 1.427em;"></span><span class="strut bottom" style="height: 2.363em; vertical-align: -0.936em;"></span><span class="base"><span class="mord"><span class="mopen nulldelimiter"></span><span class="mfrac"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 1.427em;"><span class="" style="top: -2.314em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span><span class="" style="top: -3.23em;"><span class="pstrut" style="height: 3em;"></span><span class="frac-line hide-tail" style="height: 0.04em;"><svg class="" width="400em" height="400em" viewBox="0 0 400000 400000" preserveAspectRatio="xMinYMin slice"><path d="M0 0 h400000 v400000 h-400000z M0 0 h400000 v400000 h-400000z"></path></svg></span></span><span class="" style="top: -3.677em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.936em;"></span></span></span></span><span class="mclose nulldelimiter"></span></span></span></span></span></td></tr><tr><td><font face="monospace">int</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mstyle scriptlevel="0" displaystyle="true"><mo>∫</mo><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow><mi>d</mi><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mstyle></mrow><annotation encoding="application/x-tex">\displaystyle\int{\blue{[?]}}d\blue{[?]}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 1.36em;"></span><span class="strut bottom" style="height: 2.22225em; vertical-align: -0.86225em;"></span><span class="base"><span class="mop op-symbol large-op" style="margin-right: 0.44445em; position: relative; top: -0.001125em;">∫</span><span class="mord"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span><span class="mord mathit">d</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span></span></td></tr><tr><td><font face="monospace">defi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mstyle scriptlevel="0" displaystyle="true"><msubsup><mo>∫</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></msubsup><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mi>d</mi><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mstyle></mrow><annotation encoding="application/x-tex">\displaystyle\int_{\blue{[?]}}^{\blue{[?]}}\blue{[?]}d\blue{[?]}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 1.6379em;"></span><span class="strut bottom" style="height: 2.72485em; vertical-align: -1.08695em;"></span><span class="base"><span class="mop"><span class="mop op-symbol large-op" style="margin-right: 0.44445em; position: relative; top: -0.001125em;">∫</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 1.6379em;"><span class="" style="top: -1.78805em; margin-left: -0.44445em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span><span class="" style="top: -3.8129em; margin-right: 0.05em;"><span class="pstrut" style="height: 2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 1.08695em;"></span></span></span></span></span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mord mathit">d</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span></span></td></tr><tr><td><font face="monospace">deriv</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mstyle scriptlevel="0" displaystyle="true"><mfrac><mrow><mi>d</mi></mrow><mrow><mi>d</mi><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow></mfrac><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mstyle></mrow><annotation encoding="application/x-tex">\displaystyle\frac{d}{d\blue{[?]}}\blue{[?]}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 1.37144em;"></span><span class="strut bottom" style="height: 2.30744em; vertical-align: -0.936em;"></span><span class="base"><span class="mord"><span class="mopen nulldelimiter"></span><span class="mfrac"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 1.37144em;"><span class="" style="top: -2.314em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mord mathit">d</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span><span class="" style="top: -3.23em;"><span class="pstrut" style="height: 3em;"></span><span class="frac-line hide-tail" style="height: 0.04em;"><svg class="" width="400em" height="400em" viewBox="0 0 400000 400000" preserveAspectRatio="xMinYMin slice"><path d="M0 0 h400000 v400000 h-400000z M0 0 h400000 v400000 h-400000z"></path></svg></span></span><span class="" style="top: -3.677em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mord mathit">d</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.936em;"></span></span></span></span><span class="mclose nulldelimiter"></span></span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span></span></td></tr><tr><td><font face="monospace">sum</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mstyle scriptlevel="0" displaystyle="true"><munderover><mo>∑</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></munderover><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mstyle></mrow><annotation encoding="application/x-tex">\displaystyle\sum_{\blue{[?]}}^{\blue{[?]}}\blue{[?]}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 1.96101em;"></span><span class="strut bottom" style="height: 3.47701em; vertical-align: -1.516em;"></span><span class="base"><span class="mop op-limits"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 1.96101em;"><span class="" style="top: -1.809em; margin-left: 0em;"><span class="pstrut" style="height: 3.05em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span><span class="" style="top: -3.05001em;"><span class="pstrut" style="height: 3.05em;"></span><span class=""><span class="mop op-symbol large-op">∑</span></span></span><span class="" style="top: -4.386em; margin-left: 0em;"><span class="pstrut" style="height: 3.05em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 1.516em;"></span></span></span></span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span></span></td></tr><tr><td><font face="monospace">prod</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mstyle scriptlevel="0" displaystyle="true"><munderover><mo>∏</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></munderover><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mstyle></mrow><annotation encoding="application/x-tex">\displaystyle\prod_{\blue{[?]}}^{\blue{[?]}}\blue{[?]}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 1.96101em;"></span><span class="strut bottom" style="height: 3.47701em; vertical-align: -1.516em;"></span><span class="base"><span class="mop op-limits"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 1.96101em;"><span class="" style="top: -1.809em; margin-left: 0em;"><span class="pstrut" style="height: 3.05em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span><span class="" style="top: -3.05001em;"><span class="pstrut" style="height: 3.05em;"></span><span class=""><span class="mop op-symbol large-op">∏</span></span></span><span class="" style="top: -4.386em; margin-left: 0em;"><span class="pstrut" style="height: 3.05em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 1.516em;"></span></span></span></span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span></span></td></tr><tr><td><font face="monospace">root</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mroot><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow></mroot></mrow><annotation encoding="application/x-tex">\sqrt[\blue{[?]}]{\blue{[?]}}</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.935em;"></span><span class="strut bottom" style="height: 1.24em; vertical-align: -0.305em;"></span><span class="base"><span class="mord sqrt"><span class="root"><span class="vlist-t"><span class="vlist-r"><span class="vlist" style="height: 0.753em;"><span class="" style="top: -2.878em;"><span class="pstrut" style="height: 2.5em;"></span><span class="sizing reset-size6 size1 mtight"><span class="mord mtight"><span class="mopen mtight" style="color: rgb(100, 149, 237);">[</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">?</span><span class="mclose mtight" style="color: rgb(100, 149, 237);">]</span></span></span></span></span></span></span></span><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist svg-align" style="height: 0.935em;"><span class="" style="top: -3.2em;"><span class="pstrut" style="height: 3.2em;"></span><span class="mord" style="padding-left: 1em;"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span><span class="" style="top: -2.895em;"><span class="pstrut" style="height: 3.2em;"></span><span class="hide-tail" style="min-width: 1.02em; height: 1.2em;"><svg class="" width="400em" height="1.2em" viewBox="0 0 400000 1200" preserveAspectRatio="xMinYMin slice"><path d="M263 601c.667 0 18 39.667 52 119s68.167
 158.667 102.5 238 51.833 119.333 52.5 120C810 373.333 980.667 17.667 982 11
c4.667-7.333 11-11 19-11h398999v40H1012.333L741 607c-38.667 80.667-84 175-136
 283s-89.167 185.333-111.5 232-33.833 70.333-34.5 71c-4.667 4.667-12.333 7-23
 7l-12-1-109-253c-72.667-168-109.333-252-110-252-10.667 8-22 16.667-34 26-22
 17.333-33.333 26-34 26l-26-26 76-59 76-60zM1001 0h398999v40H1012z"></path></svg></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.305em;"></span></span></span></span></span></span></span></td></tr><tr><td><font face="monospace">vec</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mrow><mo fence="true">⟨</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">⟩</mo></mrow></mrow><annotation encoding="application/x-tex">\left\langle \blue{[?]} \right\rangle</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="minner"><span class="mopen delimcenter" style="top: 0em;">⟨</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">⟩</span></span></span></span></span></td></tr><tr><td><font face="monospace">mat</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mrow><mo fence="true">(</mo><mtable><mtr><mtd><mstyle scriptlevel="0" displaystyle="false"><mrow><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle></mrow></mstyle></mtd></mtr></mtable><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\left(\begin{matrix} \blue{[?]} \end{matrix}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.85em;"></span><span class="strut bottom" style="height: 1.20001em; vertical-align: -0.35001em;"></span><span class="base"><span class="minner"><span class="mopen delimcenter" style="top: 0em;"><span class="delimsizing size1">(</span></span><span class="mord"><span class="mtable"><span class="col-align-c"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height: 0.85em;"><span class="" style="top: -3.01em;"><span class="pstrut" style="height: 3em;"></span><span class="mord"><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height: 0.35em;"></span></span></span></span></span></span><span class="mclose delimcenter" style="top: 0em;"><span class="delimsizing size1">)</span></span></span></span></span></span></td></tr><tr><td><font face="monospace">*</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mo>⋅</mo></mrow><annotation encoding="application/x-tex">\cdot</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.44445em;"></span><span class="strut bottom" style="height: 0.44445em; vertical-align: 0em;"></span><span class="base"><span class="mord">⋅</span></span></span></span></td></tr><tr><td><font face="monospace">infinity</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">∞</mi></mrow><annotation encoding="application/x-tex">\infty</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord">∞</span></span></span></span></td></tr><tr><td><font face="monospace">arcsin</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>arcsin</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\arcsin\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">arcsin</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">arccos</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>arccos</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\arccos\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">arccos</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">arctan</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>arctan</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\arctan\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">arctan</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">sin</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>sin</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\sin\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">sin</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">cos</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>cos</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\cos\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">cos</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">tan</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>tan</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\tan\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">tan</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">sec</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>sec</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\sec\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">sec</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">csc</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>csc</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\csc\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">csc</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">cot</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>cot</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\cot\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">cot</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">log</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>log</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\log\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">lo<span style="margin-right: 0.01389em;">g</span></span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">ln</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ln</mi><mo>⁡</mo><mrow><mo fence="true">(</mo><mstyle mathcolor="katex-blue"><mo>[</mo><mo>?</mo><mo>]</mo></mstyle><mo fence="true">)</mo></mrow></mrow><annotation encoding="application/x-tex">\ln\left(\blue{[?]}\right)</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.75em;"></span><span class="strut bottom" style="height: 1em; vertical-align: -0.25em;"></span><span class="base"><span class="mop">ln</span><span class="minner"><span class="mopen delimcenter" style="top: 0em;">(</span><span class="mopen" style="color: rgb(100, 149, 237);">[</span><span class="mclose" style="color: rgb(100, 149, 237);">?</span><span class="mclose" style="color: rgb(100, 149, 237);">]</span><span class="mclose delimcenter" style="top: 0em;">)</span></span></span></span></span></td></tr><tr><td><font face="monospace">alpha</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>α</mi></mrow><annotation encoding="application/x-tex">\alpha</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.0037em;">α</span></span></span></span></td></tr><tr><td><font face="monospace">beta</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>β</mi></mrow><annotation encoding="application/x-tex">\beta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.05278em;">β</span></span></span></span></td></tr><tr><td><font face="monospace">gamma</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>γ</mi></mrow><annotation encoding="application/x-tex">\gamma</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.625em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.05556em;">γ</span></span></span></span></td></tr><tr><td><font face="monospace">delta</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>δ</mi></mrow><annotation encoding="application/x-tex">\delta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.69444em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.03785em;">δ</span></span></span></span></td></tr><tr><td><font face="monospace">epsilon</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ϵ</mi></mrow><annotation encoding="application/x-tex">\epsilon</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit">ϵ</span></span></span></span></td></tr><tr><td><font face="monospace">zeta</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ζ</mi></mrow><annotation encoding="application/x-tex">\zeta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.07378em;">ζ</span></span></span></span></td></tr><tr><td><font face="monospace">eta</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>η</mi></mrow><annotation encoding="application/x-tex">\eta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.625em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.03588em;">η</span></span></span></span></td></tr><tr><td><font face="monospace">theta</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>θ</mi></mrow><annotation encoding="application/x-tex">\theta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.69444em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.02778em;">θ</span></span></span></span></td></tr><tr><td><font face="monospace">iota</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ι</mi></mrow><annotation encoding="application/x-tex">\iota</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit">ι</span></span></span></span></td></tr><tr><td><font face="monospace">kappa</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>κ</mi></mrow><annotation encoding="application/x-tex">\kappa</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit">κ</span></span></span></span></td></tr><tr><td><font face="monospace">lambda</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>λ</mi></mrow><annotation encoding="application/x-tex">\lambda</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.69444em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit">λ</span></span></span></span></td></tr><tr><td><font face="monospace">mu</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>μ</mi></mrow><annotation encoding="application/x-tex">\mu</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.625em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit">μ</span></span></span></span></td></tr><tr><td><font face="monospace">nu</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ν</mi></mrow><annotation encoding="application/x-tex">\nu</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.06366em;">ν</span></span></span></span></td></tr><tr><td><font face="monospace">xi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ξ</mi></mrow><annotation encoding="application/x-tex">\xi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.04601em;">ξ</span></span></span></span></td></tr><tr><td><font face="monospace">omicron</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ο</mi></mrow><annotation encoding="application/x-tex">\omicron</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit">ο</span></span></span></span></td></tr><tr><td><font face="monospace">pi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>π</mi></mrow><annotation encoding="application/x-tex">\pi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.03588em;">π</span></span></span></span></td></tr><tr><td><font face="monospace">rho</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ρ</mi></mrow><annotation encoding="application/x-tex">\rho</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.625em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit">ρ</span></span></span></span></td></tr><tr><td><font face="monospace">sigma</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>σ</mi></mrow><annotation encoding="application/x-tex">\sigma</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.03588em;">σ</span></span></span></span></td></tr><tr><td><font face="monospace">tau</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>τ</mi></mrow><annotation encoding="application/x-tex">\tau</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.1132em;">τ</span></span></span></span></td></tr><tr><td><font face="monospace">upsilon</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>υ</mi></mrow><annotation encoding="application/x-tex">\upsilon</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.03588em;">υ</span></span></span></span></td></tr><tr><td><font face="monospace">phi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ϕ</mi></mrow><annotation encoding="application/x-tex">\phi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit">ϕ</span></span></span></span></td></tr><tr><td><font face="monospace">chi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>χ</mi></mrow><annotation encoding="application/x-tex">\chi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.625em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit">χ</span></span></span></span></td></tr><tr><td><font face="monospace">psi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ψ</mi></mrow><annotation encoding="application/x-tex">\psi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.69444em;"></span><span class="strut bottom" style="height: 0.88888em; vertical-align: -0.19444em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.03588em;">ψ</span></span></span></span></td></tr><tr><td><font face="monospace">omega</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi>ω</mi></mrow><annotation encoding="application/x-tex">\omega</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.43056em;"></span><span class="strut bottom" style="height: 0.43056em; vertical-align: 0em;"></span><span class="base"><span class="mord mathit" style="margin-right: 0.03588em;">ω</span></span></span></span></td></tr><tr><td><font face="monospace">Gamma</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Γ</mi></mrow><annotation encoding="application/x-tex">\Gamma</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Γ</span></span></span></span></td></tr><tr><td><font face="monospace">Delta</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Δ</mi></mrow><annotation encoding="application/x-tex">\Delta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Δ</span></span></span></span></td></tr><tr><td><font face="monospace">Theta</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Θ</mi></mrow><annotation encoding="application/x-tex">\Theta</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Θ</span></span></span></span></td></tr><tr><td><font face="monospace">Lambda</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Λ</mi></mrow><annotation encoding="application/x-tex">\Lambda</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Λ</span></span></span></span></td></tr><tr><td><font face="monospace">Xi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Ξ</mi></mrow><annotation encoding="application/x-tex">\Xi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Ξ</span></span></span></span></td></tr><tr><td><font face="monospace">Pi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Π</mi></mrow><annotation encoding="application/x-tex">\Pi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Π</span></span></span></span></td></tr><tr><td><font face="monospace">Sigma</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Σ</mi></mrow><annotation encoding="application/x-tex">\Sigma</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Σ</span></span></span></span></td></tr><tr><td><font face="monospace">Phi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Φ</mi></mrow><annotation encoding="application/x-tex">\Phi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Φ</span></span></span></span></td></tr><tr><td><font face="monospace">Psi</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Ψ</mi></mrow><annotation encoding="application/x-tex">\Psi</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Ψ</span></span></span></span></td></tr><tr><td><font face="monospace">Omega</font></td><td><span class="katex"><span class="katex-mathml"><math><semantics><mrow><mi mathvariant="normal">Ω</mi></mrow><annotation encoding="application/x-tex">\Omega</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="strut" style="height: 0.68333em;"></span><span class="strut bottom" style="height: 0.68333em; vertical-align: 0em;"></span><span class="base"><span class="mord">Ω</span></span></span></span></td></tr></table><div class="guppy-card-x" style="cursor: pointer; position: absolute; top: 0px; right: 0px; padding-right: 5px; line-height: 1;"><font size="6pt">×</font></div></div><div class="guppy_help" style="padding: 10px; border: 1px solid black; background-color: rgb(255, 255, 255); position: absolute; top: 0px; left: 0px; display: none;"><p>Global settings: </p>
<style>div.guppy_help td{ vertical-align:top;padding: 2px;}</style>
<h3>Settings</h3><table id="guppy_settings_table"></table><div class="guppy-card-x" style="cursor: pointer; position: absolute; top: 0px; right: 0px; padding-right: 5px; line-height: 1;"><font size="6pt">×</font></div></div><div style="position: absolute; width: 0px; height: 0px; overflow: hidden; padding: 0px; border: 0px; margin: 0px;"><div id="MathJax_Font_Test" style="position: absolute; visibility: hidden; top: 0px; left: 0px; width: auto; min-width: 0px; max-width: none; padding: 0px; border: 0px; margin: 0px; white-space: nowrap; text-align: left; text-indent: 0px; text-transform: none; line-height: normal; letter-spacing: normal; word-spacing: normal; font-size: 40px; font-weight: normal; font-style: normal; font-size-adjust: none; font-family: MathJax_Size3, sans-serif;"></div></div></body>
</html>
