---
layout: page
permalink: ai-study/secure-and-private-ai/deep-learning-with-pytorch/part7
---
<html>
<head><meta charset="utf-8" />

<title>Part7 Study</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>
<style type="text/css">
    
/* Temporary definitions which will become obsolete with Notebook release 5.0 */
.ansi-black-fg { color: #3E424D; }
.ansi-black-bg { background-color: #3E424D; }
.ansi-black-intense-fg { color: #282C36; }
.ansi-black-intense-bg { background-color: #282C36; }
.ansi-red-fg { color: #E75C58; }
.ansi-red-bg { background-color: #E75C58; }
.ansi-red-intense-fg { color: #B22B31; }
.ansi-red-intense-bg { background-color: #B22B31; }
.ansi-green-fg { color: #00A250; }
.ansi-green-bg { background-color: #00A250; }
.ansi-green-intense-fg { color: #007427; }
.ansi-green-intense-bg { background-color: #007427; }
.ansi-yellow-fg { color: #DDB62B; }
.ansi-yellow-bg { background-color: #DDB62B; }
.ansi-yellow-intense-fg { color: #B27D12; }
.ansi-yellow-intense-bg { background-color: #B27D12; }
.ansi-blue-fg { color: #208FFB; }
.ansi-blue-bg { background-color: #208FFB; }
.ansi-blue-intense-fg { color: #0065CA; }
.ansi-blue-intense-bg { background-color: #0065CA; }
.ansi-magenta-fg { color: #D160C4; }
.ansi-magenta-bg { background-color: #D160C4; }
.ansi-magenta-intense-fg { color: #A03196; }
.ansi-magenta-intense-bg { background-color: #A03196; }
.ansi-cyan-fg { color: #60C6C8; }
.ansi-cyan-bg { background-color: #60C6C8; }
.ansi-cyan-intense-fg { color: #258F8F; }
.ansi-cyan-intense-bg { background-color: #258F8F; }
.ansi-white-fg { color: #C5C1B4; }
.ansi-white-bg { background-color: #C5C1B4; }
.ansi-white-intense-fg { color: #A1A6B2; }
.ansi-white-intense-bg { background-color: #A1A6B2; }

.ansi-bold { font-weight: bold; }

    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Cat-Vs.-Dog">Cat Vs. Dog<a class="anchor-link" href="#Cat-Vs.-Dog">&#182;</a></h2><h1 id="1.-Transform-&amp;-Estabilish-Loader">1. Transform &amp; Estabilish Loader<a class="anchor-link" href="#1.-Transform-&amp;-Estabilish-Loader">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Transform &amp; Establish loader</span>
<span class="kn">import</span> <span class="nn">torch</span>
<span class="kn">from</span> <span class="nn">torchvision</span> <span class="k">import</span> <span class="n">datasets</span><span class="p">,</span> <span class="n">transforms</span>

<span class="n">data_dir</span> <span class="o">=</span> <span class="s1">&#39;Cat_Dog_data&#39;</span>
<span class="n">train_transforms</span> <span class="o">=</span> <span class="n">transforms</span><span class="o">.</span><span class="n">Compose</span><span class="p">([</span><span class="n">transforms</span><span class="o">.</span><span class="n">RandomRotation</span><span class="p">(</span><span class="mi">30</span><span class="p">),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">RandomResizedCrop</span><span class="p">(</span><span class="mi">224</span><span class="p">),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">RandomHorizontalFlip</span><span class="p">(),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">ToTensor</span><span class="p">(),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">Normalize</span><span class="p">([</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">],</span> 
                                                            <span class="p">[</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">])])</span> 

<span class="n">test_transforms</span> <span class="o">=</span> <span class="n">transforms</span><span class="o">.</span><span class="n">Compose</span><span class="p">([</span><span class="n">transforms</span><span class="o">.</span><span class="n">Resize</span><span class="p">(</span><span class="mi">255</span><span class="p">),</span>
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">CenterCrop</span><span class="p">(</span><span class="mi">224</span><span class="p">),</span>
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">ToTensor</span><span class="p">(),</span>                                       
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">Normalize</span><span class="p">([</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">],</span> 
                                                           <span class="p">[</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">])])</span>

<span class="c1"># Pass transforms to loader</span>
<span class="n">train_data</span> <span class="o">=</span> <span class="n">datasets</span><span class="o">.</span><span class="n">ImageFolder</span><span class="p">(</span><span class="n">data_dir</span> <span class="o">+</span> <span class="s1">&#39;/train&#39;</span><span class="p">,</span> <span class="n">transform</span><span class="o">=</span><span class="n">train_transforms</span><span class="p">)</span>
<span class="n">test_data</span> <span class="o">=</span> <span class="n">datasets</span><span class="o">.</span><span class="n">ImageFolder</span><span class="p">(</span><span class="n">data_dir</span> <span class="o">+</span> <span class="s1">&#39;/test&#39;</span><span class="p">,</span> <span class="n">transform</span><span class="o">=</span><span class="n">test_transforms</span><span class="p">)</span>

<span class="n">trainloader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">train_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="mi">32</span><span class="p">)</span>
<span class="n">testloader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">test_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="mi">32</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="2.-Define-Model">2. Define Model<a class="anchor-link" href="#2.-Define-Model">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">torch</span> <span class="k">import</span> <span class="n">nn</span>
<span class="kn">from</span> <span class="nn">torch</span> <span class="k">import</span> <span class="n">optim</span>

<span class="n">model</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">Sequential</span><span class="p">(</span><span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">150528</span><span class="p">,</span> <span class="mi">600</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">ReLU</span><span class="p">(),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="n">p</span><span class="o">=</span><span class="mf">0.2</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">600</span><span class="p">,</span> <span class="mi">100</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">ReLU</span><span class="p">(),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="n">p</span><span class="o">=</span><span class="mf">0.2</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">100</span><span class="p">,</span> <span class="mi">30</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">LogSoftmax</span><span class="p">(</span><span class="n">dim</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>

<span class="c1"># if using GPU</span>
<span class="c1"># model = sq.cuda()</span>
<span class="c1"># device = torch.device(&#39;cuda:0&#39; if torch.cuda.is_available() else &#39;cpu&#39;)</span>
<span class="c1"># print(device)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="3.-Loss-Function-and-Optimizer">3. Loss Function and Optimizer<a class="anchor-link" href="#3.-Loss-Function-and-Optimizer">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">criterion</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">NLLLoss</span><span class="p">()</span>
<span class="n">optimizer</span> <span class="o">=</span> <span class="n">optim</span><span class="o">.</span><span class="n">Adam</span><span class="p">(</span><span class="n">model</span><span class="o">.</span><span class="n">parameters</span><span class="p">(),</span> <span class="n">lr</span><span class="o">=</span><span class="mf">0.003</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="4.-Train-&amp;-Validation">4. Train &amp; Validation<a class="anchor-link" href="#4.-Train-&amp;-Validation">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">epochs</span> <span class="o">=</span> <span class="mi">3</span>
<span class="n">steps</span> <span class="o">=</span> <span class="mi">0</span>

<span class="n">train_losses</span><span class="p">,</span> <span class="n">test_losses</span> <span class="o">=</span> <span class="p">[],</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">e</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">epochs</span><span class="p">):</span>
    <span class="n">running_loss</span> <span class="o">=</span> <span class="mi">0</span>
    <span class="k">for</span> <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="ow">in</span> <span class="n">trainloader</span><span class="p">:</span>
        <span class="c1"># images = images.to(device) # if using GPU</span>
        <span class="c1"># labels = labels.to(device) # if using GPU</span>
        <span class="n">images</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="n">images</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="o">-</span><span class="mi">1</span><span class="p">)</span>
        
        <span class="n">optimizer</span><span class="o">.</span><span class="n">zero_grad</span><span class="p">()</span>
        
        <span class="n">log_ps</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>
        <span class="n">loss</span> <span class="o">=</span> <span class="n">criterion</span><span class="p">(</span><span class="n">log_ps</span><span class="p">,</span> <span class="n">labels</span><span class="p">)</span>
        <span class="n">loss</span><span class="o">.</span><span class="n">backward</span><span class="p">()</span>
        <span class="n">optimizer</span><span class="o">.</span><span class="n">step</span><span class="p">()</span>
        
        <span class="n">running_loss</span> <span class="o">+=</span> <span class="n">loss</span><span class="o">.</span><span class="n">item</span><span class="p">()</span>
        
    <span class="k">else</span><span class="p">:</span>
        <span class="n">test_loss</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="n">accuracy</span> <span class="o">=</span> <span class="mi">0</span>
        
        <span class="c1"># Turn off gradients for validation, saves memory and computations</span>
        <span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
            <span class="n">model</span><span class="o">.</span><span class="n">eval</span><span class="p">()</span>
            <span class="k">for</span> <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="ow">in</span> <span class="n">testloader</span><span class="p">:</span>
                <span class="n">images</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="n">images</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="o">-</span><span class="mi">1</span><span class="p">)</span>
                <span class="n">log_ps</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>
                <span class="n">test_loss</span> <span class="o">+=</span> <span class="n">criterion</span><span class="p">(</span><span class="n">log_ps</span><span class="p">,</span> <span class="n">labels</span><span class="p">)</span>
                
                <span class="n">ps</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">exp</span><span class="p">(</span><span class="n">log_ps</span><span class="p">)</span>
                <span class="n">top_p</span><span class="p">,</span> <span class="n">top_class</span> <span class="o">=</span> <span class="n">ps</span><span class="o">.</span><span class="n">topk</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="n">dim</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
                <span class="n">equals</span> <span class="o">=</span> <span class="n">top_class</span> <span class="o">==</span> <span class="n">labels</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="o">*</span><span class="n">top_class</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
                <span class="n">accuracy</span> <span class="o">+=</span> <span class="n">torch</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">equals</span><span class="o">.</span><span class="n">type</span><span class="p">(</span><span class="n">torch</span><span class="o">.</span><span class="n">FloatTensor</span><span class="p">))</span>
        
        <span class="n">model</span><span class="o">.</span><span class="n">train</span><span class="p">()</span>
        
        <span class="n">train_losses</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">running_loss</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">trainloader</span><span class="p">))</span>
        <span class="n">test_losses</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">test_loss</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">testloader</span><span class="p">))</span>

        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Epoch: </span><span class="si">{}</span><span class="s2">/</span><span class="si">{}</span><span class="s2">.. &quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">e</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">epochs</span><span class="p">),</span>
              <span class="s2">&quot;Training Loss: </span><span class="si">{:.3f}</span><span class="s2">.. &quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">train_losses</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]),</span>
              <span class="s2">&quot;Test Loss: </span><span class="si">{:.3f}</span><span class="s2">.. &quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">test_losses</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]),</span>
              <span class="s2">&quot;Test Accuracy: </span><span class="si">{:.3f}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">accuracy</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">testloader</span><span class="p">)))</span>        
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Epoch: 1/3..  Training Loss: 8.796..  Test Loss: 22111.641..  Test Accuracy: 0.506
Epoch: 2/3..  Training Loss: 244.482..  Test Loss: 4970.770..  Test Accuracy: 0.506
Epoch: 3/3..  Training Loss: 46.383..  Test Loss: 3957.413..  Test Accuracy: 0.506
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="5.-The-First-Time-Save">5. The First-Time Save<a class="anchor-link" href="#5.-The-First-Time-Save">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[16]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># The First Save</span>
<span class="n">checkpoint</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;state_dict&#39;</span><span class="p">:</span> <span class="n">model</span><span class="o">.</span><span class="n">state_dict</span><span class="p">(),</span>
              <span class="s1">&#39;optimizer&#39;</span><span class="p">:</span><span class="n">optimizer</span><span class="o">.</span><span class="n">state_dict</span><span class="p">(),</span>
              <span class="s1">&#39;train_losses&#39;</span><span class="p">:</span><span class="n">train_losses</span><span class="p">,</span>
              <span class="s1">&#39;test_losses&#39;</span><span class="p">:</span><span class="n">test_losses</span>
<span class="p">}</span>

<span class="n">torch</span><span class="o">.</span><span class="n">save</span><span class="p">(</span><span class="n">checkpoint</span><span class="p">,</span> <span class="s1">&#39;cat-vs-dog-checkpoint.pth&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="New-Iteration-Of-Training">New Iteration Of Training<a class="anchor-link" href="#New-Iteration-Of-Training">&#182;</a></h2><h1 id="6.-Load-Checkpoint">6. Load Checkpoint<a class="anchor-link" href="#6.-Load-Checkpoint">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[17]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">torch</span>
<span class="kn">from</span> <span class="nn">torch</span> <span class="k">import</span> <span class="n">nn</span>
<span class="kn">from</span> <span class="nn">torch</span> <span class="k">import</span> <span class="n">optim</span>

<span class="n">model</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">Sequential</span><span class="p">(</span><span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">150528</span><span class="p">,</span> <span class="mi">600</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">ReLU</span><span class="p">(),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="n">p</span><span class="o">=</span><span class="mf">0.2</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">600</span><span class="p">,</span> <span class="mi">100</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">ReLU</span><span class="p">(),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="n">p</span><span class="o">=</span><span class="mf">0.2</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">100</span><span class="p">,</span> <span class="mi">30</span><span class="p">),</span>
                      <span class="n">nn</span><span class="o">.</span><span class="n">LogSoftmax</span><span class="p">(</span><span class="n">dim</span><span class="o">=</span><span class="mi">1</span><span class="p">))</span>
<span class="n">criterion</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">NLLLoss</span><span class="p">()</span>
<span class="n">optimizer</span> <span class="o">=</span> <span class="n">optim</span><span class="o">.</span><span class="n">Adam</span><span class="p">(</span><span class="n">model</span><span class="o">.</span><span class="n">parameters</span><span class="p">(),</span> <span class="n">lr</span><span class="o">=</span><span class="mf">0.003</span><span class="p">)</span>

<span class="n">checkpoint</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">load</span><span class="p">(</span><span class="s1">&#39;cat-vs-dog-checkpoint.pth&#39;</span><span class="p">)</span>
<span class="n">model</span><span class="o">.</span><span class="n">load_state_dict</span><span class="p">(</span><span class="n">checkpoint</span><span class="p">[</span><span class="s1">&#39;state_dict&#39;</span><span class="p">])</span>
<span class="n">optimizer</span><span class="o">.</span><span class="n">load_state_dict</span><span class="p">(</span><span class="n">checkpoint</span><span class="p">[</span><span class="s1">&#39;optimizer&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="7.-Check-The-Loaded-Data">7. Check The Loaded Data<a class="anchor-link" href="#7.-Check-The-Loaded-Data">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[18]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">for</span> <span class="n">param_tensor</span> <span class="ow">in</span> <span class="n">model</span><span class="o">.</span><span class="n">state_dict</span><span class="p">():</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">param_tensor</span><span class="p">,</span> <span class="s2">&quot;</span><span class="se">\t</span><span class="s2">&quot;</span><span class="p">,</span> <span class="n">model</span><span class="o">.</span><span class="n">state_dict</span><span class="p">()[</span><span class="n">param_tensor</span><span class="p">]</span><span class="o">.</span><span class="n">size</span><span class="p">())</span>
<span class="nb">print</span><span class="p">(</span><span class="n">checkpoint</span><span class="p">[</span><span class="s1">&#39;train_losses&#39;</span><span class="p">])</span>
<span class="nb">print</span><span class="p">(</span><span class="n">checkpoint</span><span class="p">[</span><span class="s1">&#39;test_losses&#39;</span><span class="p">])</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>0.weight 	 torch.Size([600, 150528])
0.bias 	 torch.Size([600])
3.weight 	 torch.Size([100, 600])
3.bias 	 torch.Size([100])
6.weight 	 torch.Size([30, 100])
6.bias 	 torch.Size([30])
[8.796342773870988, 244.482233172399, 46.3833776791289]
[tensor(22111.6406), tensor(4970.7700), tensor(3957.4133)]
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="8.-Transfrom-&amp;-Establish-Loader">8. Transfrom &amp; Establish Loader<a class="anchor-link" href="#8.-Transfrom-&amp;-Establish-Loader">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[19]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">torchvision</span> <span class="k">import</span> <span class="n">datasets</span><span class="p">,</span> <span class="n">transforms</span>
<span class="n">data_dir</span> <span class="o">=</span> <span class="s1">&#39;Cat_Dog_data&#39;</span>
<span class="n">train_transforms</span> <span class="o">=</span> <span class="n">transforms</span><span class="o">.</span><span class="n">Compose</span><span class="p">([</span><span class="n">transforms</span><span class="o">.</span><span class="n">RandomRotation</span><span class="p">(</span><span class="mi">30</span><span class="p">),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">RandomResizedCrop</span><span class="p">(</span><span class="mi">224</span><span class="p">),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">RandomHorizontalFlip</span><span class="p">(),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">ToTensor</span><span class="p">(),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">Normalize</span><span class="p">([</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">],</span> 
                                                            <span class="p">[</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">])])</span> 

<span class="n">test_transforms</span> <span class="o">=</span> <span class="n">transforms</span><span class="o">.</span><span class="n">Compose</span><span class="p">([</span><span class="n">transforms</span><span class="o">.</span><span class="n">Resize</span><span class="p">(</span><span class="mi">255</span><span class="p">),</span>
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">CenterCrop</span><span class="p">(</span><span class="mi">224</span><span class="p">),</span>
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">ToTensor</span><span class="p">(),</span>                                       
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">Normalize</span><span class="p">([</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">],</span> 
                                                           <span class="p">[</span><span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">,</span> <span class="mf">0.5</span><span class="p">])])</span>

<span class="c1"># Pass transforms to loader</span>
<span class="n">train_data</span> <span class="o">=</span> <span class="n">datasets</span><span class="o">.</span><span class="n">ImageFolder</span><span class="p">(</span><span class="n">data_dir</span> <span class="o">+</span> <span class="s1">&#39;/train&#39;</span><span class="p">,</span> <span class="n">transform</span><span class="o">=</span><span class="n">train_transforms</span><span class="p">)</span>
<span class="n">test_data</span> <span class="o">=</span> <span class="n">datasets</span><span class="o">.</span><span class="n">ImageFolder</span><span class="p">(</span><span class="n">data_dir</span> <span class="o">+</span> <span class="s1">&#39;/test&#39;</span><span class="p">,</span> <span class="n">transform</span><span class="o">=</span><span class="n">test_transforms</span><span class="p">)</span>

<span class="n">trainloader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">train_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="mi">32</span><span class="p">)</span>
<span class="n">testloader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">test_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="mi">32</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="9.Train-&amp;-Validation">9.Train &amp; Validation<a class="anchor-link" href="#9.Train-&amp;-Validation">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[20]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Train &amp; Validation</span>
<span class="n">epochs</span> <span class="o">=</span> <span class="mi">1</span>
<span class="n">steps</span> <span class="o">=</span> <span class="mi">0</span>

<span class="n">train_losses</span><span class="p">,</span> <span class="n">test_losses</span> <span class="o">=</span> <span class="p">[],</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">e</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">epochs</span><span class="p">):</span>
    <span class="n">running_loss</span> <span class="o">=</span> <span class="mi">0</span>
    <span class="k">for</span> <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="ow">in</span> <span class="n">trainloader</span><span class="p">:</span>
        <span class="c1"># images = images.to(device)</span>
        <span class="c1"># labels = labels.to(device)</span>
        <span class="n">images</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="n">images</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="o">-</span><span class="mi">1</span><span class="p">)</span>
        
        <span class="n">optimizer</span><span class="o">.</span><span class="n">zero_grad</span><span class="p">()</span>
        
        <span class="n">log_ps</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>
        <span class="n">loss</span> <span class="o">=</span> <span class="n">criterion</span><span class="p">(</span><span class="n">log_ps</span><span class="p">,</span> <span class="n">labels</span><span class="p">)</span>
        <span class="n">loss</span><span class="o">.</span><span class="n">backward</span><span class="p">()</span>
        <span class="n">optimizer</span><span class="o">.</span><span class="n">step</span><span class="p">()</span>
        
        <span class="n">running_loss</span> <span class="o">+=</span> <span class="n">loss</span><span class="o">.</span><span class="n">item</span><span class="p">()</span>
        
    <span class="k">else</span><span class="p">:</span>
        <span class="n">test_loss</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="n">accuracy</span> <span class="o">=</span> <span class="mi">0</span>
        
        <span class="c1"># Turn off gradients for validation, saves memory and computations</span>
        <span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
            <span class="n">model</span><span class="o">.</span><span class="n">eval</span><span class="p">()</span>
            <span class="k">for</span> <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="ow">in</span> <span class="n">testloader</span><span class="p">:</span>
                <span class="n">images</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="n">images</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="o">-</span><span class="mi">1</span><span class="p">)</span>
                <span class="n">log_ps</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>
                <span class="n">test_loss</span> <span class="o">+=</span> <span class="n">criterion</span><span class="p">(</span><span class="n">log_ps</span><span class="p">,</span> <span class="n">labels</span><span class="p">)</span>
                
                <span class="n">ps</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">exp</span><span class="p">(</span><span class="n">log_ps</span><span class="p">)</span>
                <span class="n">top_p</span><span class="p">,</span> <span class="n">top_class</span> <span class="o">=</span> <span class="n">ps</span><span class="o">.</span><span class="n">topk</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="n">dim</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
                <span class="n">equals</span> <span class="o">=</span> <span class="n">top_class</span> <span class="o">==</span> <span class="n">labels</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="o">*</span><span class="n">top_class</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
                <span class="n">accuracy</span> <span class="o">+=</span> <span class="n">torch</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">equals</span><span class="o">.</span><span class="n">type</span><span class="p">(</span><span class="n">torch</span><span class="o">.</span><span class="n">FloatTensor</span><span class="p">))</span>
        
        <span class="n">model</span><span class="o">.</span><span class="n">train</span><span class="p">()</span>
        
        <span class="n">train_losses</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">running_loss</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">trainloader</span><span class="p">))</span>
        <span class="n">test_losses</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">test_loss</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">testloader</span><span class="p">))</span>

        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Epoch: </span><span class="si">{}</span><span class="s2">/</span><span class="si">{}</span><span class="s2">.. &quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">e</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">epochs</span><span class="p">),</span>
              <span class="s2">&quot;Training Loss: </span><span class="si">{:.3f}</span><span class="s2">.. &quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">train_losses</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]),</span>
              <span class="s2">&quot;Test Loss: </span><span class="si">{:.3f}</span><span class="s2">.. &quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">test_losses</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]),</span>
              <span class="s2">&quot;Test Accuracy: </span><span class="si">{:.3f}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">accuracy</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">testloader</span><span class="p">)))</span>        
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Epoch: 1/1..  Training Loss: 34.287..  Test Loss: 1815.335..  Test Accuracy: 0.506
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="10.-The-Second-time-Save">10. The Second-time Save<a class="anchor-link" href="#10.-The-Second-time-Save">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># to preserve the first training data</span>
<span class="n">train_losses</span> <span class="o">=</span> <span class="n">checkpoint</span><span class="p">[</span><span class="s1">&#39;train_losses&#39;</span><span class="p">]</span> <span class="o">+</span> <span class="n">train_losses</span>
<span class="n">test_losses</span> <span class="o">=</span> <span class="n">checkpoint</span><span class="p">[</span><span class="s1">&#39;test_losses&#39;</span><span class="p">]</span> <span class="o">+</span> <span class="n">test_losses</span>

<span class="n">checkpoint</span> <span class="o">=</span> <span class="p">{</span><span class="s1">&#39;state_dict&#39;</span><span class="p">:</span> <span class="n">model</span><span class="o">.</span><span class="n">state_dict</span><span class="p">(),</span>
              <span class="s1">&#39;optimizer&#39;</span><span class="p">:</span><span class="n">optimizer</span><span class="o">.</span><span class="n">state_dict</span><span class="p">(),</span>
              <span class="s1">&#39;train_losses&#39;</span><span class="p">:</span><span class="n">train_losses</span><span class="p">,</span>
              <span class="s1">&#39;test_losses&#39;</span><span class="p">:</span><span class="n">test_losses</span>
<span class="p">}</span>

<span class="n">torch</span><span class="o">.</span><span class="n">save</span><span class="p">(</span><span class="n">checkpoint</span><span class="p">,</span> <span class="s1">&#39;cat-vs-dog-checkpoint.pth&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="11.-Test-An-Image">11. Test An Image<a class="anchor-link" href="#11.-Test-An-Image">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[91]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">helper</span>
<span class="o">%</span><span class="k">matplotlib</span> inline

<span class="n">imgloader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">train_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span> <span class="c1"># load only 1 image</span>
<span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="nb">next</span><span class="p">(</span><span class="nb">iter</span><span class="p">(</span><span class="n">imgloader</span><span class="p">))</span>

<span class="n">helper</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">images</span><span class="p">[</span><span class="mi">0</span><span class="p">,:])</span>
<span class="n">img</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="n">images</span><span class="o">.</span><span class="n">shape</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span> <span class="o">-</span><span class="mi">1</span><span class="p">)</span>

<span class="c1"># Turn off gradients to speed up this part</span>
<span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
    <span class="n">logps</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">img</span><span class="p">)</span>

<span class="c1"># Output of the network are log-probabilities, need to take exponential for probabilities</span>
<span class="n">ps</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">exp</span><span class="p">(</span><span class="n">logps</span><span class="p">)</span>
<span class="n">top_p</span><span class="p">,</span> <span class="n">top_class</span> <span class="o">=</span> <span class="n">ps</span><span class="o">.</span><span class="n">topk</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="n">dim</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">equals</span> <span class="o">=</span> <span class="n">top_class</span> <span class="o">==</span> <span class="n">labels</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="o">*</span><span class="n">top_class</span><span class="o">.</span><span class="n">shape</span><span class="p">)</span>
<span class="n">accuracy</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">equals</span><span class="o">.</span><span class="n">type</span><span class="p">(</span><span class="n">torch</span><span class="o">.</span><span class="n">FloatTensor</span><span class="p">))</span>
    
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Test Accuracy: </span><span class="si">{:.3f}</span><span class="s2">&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">accuracy</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Test Accuracy: 0.000
</pre>
</div>
</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
