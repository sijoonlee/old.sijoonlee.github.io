---
layout: page
permalink: ai-study/intro-to-deep-learning-with-pytorch/CNN/part2
---
<html>
<head><meta charset="utf-8" />

<title>MNIST_CONV</title>

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
<h1 id="Train-MNIST-Dataset-Using-CNN">Train MNIST Dataset Using CNN<a class="anchor-link" href="#Train-MNIST-Dataset-Using-CNN">&#182;</a></h1><p><strong>Classifier</strong> is consist of</p>
<ul>
<li>2 Convolution Layer</li>
<li>2 Fully Connected Layer</li>
<li>Log SoftMax Output</li>
</ul>
<p><strong>NLL Loss Function</strong></p>
<p><strong>Adam Optimizer</strong></p>
<p><strong>Many of codes here are taken from below and modified</strong></p>
<blockquote><p><a href="https://github.com/udacity/deep-learning-v2-pytorch/tree/master/convolutional-neural-networks/mnist-mlp">https://github.com/udacity/deep-learning-v2-pytorch/tree/master/convolutional-neural-networks/mnist-mlp</a></p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Load-Data">Load Data<a class="anchor-link" href="#Load-Data">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># import libraries</span>
<span class="kn">import</span> <span class="nn">torch</span>
<span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">from</span> <span class="nn">torchvision</span> <span class="k">import</span> <span class="n">datasets</span>
<span class="kn">import</span> <span class="nn">torchvision.transforms</span> <span class="k">as</span> <span class="nn">transforms</span>
<span class="kn">from</span> <span class="nn">torch.utils.data.sampler</span> <span class="k">import</span> <span class="n">SubsetRandomSampler</span> <span class="c1"># for validation</span>

<span class="c1"># number of subprocesses to use for data loading</span>
<span class="n">num_workers</span> <span class="o">=</span> <span class="mi">0</span>
<span class="c1"># how many samples per batch to load</span>
<span class="n">batch_size</span> <span class="o">=</span> <span class="mi">20</span>
<span class="c1"># percentage of training set to use as validation</span>
<span class="n">valid_size</span> <span class="o">=</span> <span class="mf">0.2</span>

<span class="c1"># transforms</span>
<span class="n">train_transforms</span> <span class="o">=</span> <span class="n">transforms</span><span class="o">.</span><span class="n">Compose</span><span class="p">([</span><span class="c1">#transforms.RandomRotation(30),</span>
                                       <span class="c1"># transforms.RandomResizedCrop(224),</span>
                                       <span class="c1"># transforms.RandomHorizontalFlip(),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">ToTensor</span><span class="p">(),</span>
                                       <span class="n">transforms</span><span class="o">.</span><span class="n">Normalize</span><span class="p">([</span><span class="mf">0.5</span><span class="p">,],</span> <span class="p">[</span><span class="mf">0.5</span><span class="p">,])])</span> <span class="c1"># mean, std</span>
 

<span class="n">test_transforms</span> <span class="o">=</span> <span class="n">transforms</span><span class="o">.</span><span class="n">Compose</span><span class="p">([</span><span class="c1">#transforms.Resize(255),</span>
                                      <span class="c1">#transforms.CenterCrop(224),</span>
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">ToTensor</span><span class="p">(),</span>
                                      <span class="n">transforms</span><span class="o">.</span><span class="n">Normalize</span><span class="p">([</span><span class="mf">0.5</span><span class="p">,],</span> <span class="p">[</span><span class="mf">0.5</span><span class="p">,])])</span> <span class="c1"># mean, std</span>


<span class="c1"># choose the training and test datasets</span>
<span class="n">train_data</span> <span class="o">=</span> <span class="n">datasets</span><span class="o">.</span><span class="n">MNIST</span><span class="p">(</span><span class="n">root</span><span class="o">=</span><span class="s1">&#39;data&#39;</span><span class="p">,</span> <span class="n">train</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span>
                                   <span class="n">download</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">transform</span><span class="o">=</span><span class="n">train_transforms</span><span class="p">)</span>
<span class="n">test_data</span> <span class="o">=</span> <span class="n">datasets</span><span class="o">.</span><span class="n">MNIST</span><span class="p">(</span><span class="n">root</span><span class="o">=</span><span class="s1">&#39;data&#39;</span><span class="p">,</span> <span class="n">train</span><span class="o">=</span><span class="kc">False</span><span class="p">,</span>
                                  <span class="n">download</span><span class="o">=</span><span class="kc">True</span><span class="p">,</span> <span class="n">transform</span><span class="o">=</span><span class="n">test_transforms</span><span class="p">)</span>

<span class="c1"># obtain training indices that will be used for validation</span>
<span class="n">num_train</span> <span class="o">=</span> <span class="nb">len</span><span class="p">(</span><span class="n">train_data</span><span class="p">)</span>
<span class="n">indices</span> <span class="o">=</span> <span class="nb">list</span><span class="p">(</span><span class="nb">range</span><span class="p">(</span><span class="n">num_train</span><span class="p">))</span>
<span class="n">np</span><span class="o">.</span><span class="n">random</span><span class="o">.</span><span class="n">shuffle</span><span class="p">(</span><span class="n">indices</span><span class="p">)</span>
<span class="n">split</span> <span class="o">=</span> <span class="nb">int</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">floor</span><span class="p">(</span><span class="n">valid_size</span> <span class="o">*</span> <span class="n">num_train</span><span class="p">))</span>
<span class="n">train_idx</span><span class="p">,</span> <span class="n">valid_idx</span> <span class="o">=</span> <span class="n">indices</span><span class="p">[</span><span class="n">split</span><span class="p">:],</span> <span class="n">indices</span><span class="p">[:</span><span class="n">split</span><span class="p">]</span>

<span class="c1"># define samplers for obtaining training and validation batches</span>
<span class="n">train_sampler</span> <span class="o">=</span> <span class="n">SubsetRandomSampler</span><span class="p">(</span><span class="n">train_idx</span><span class="p">)</span>
<span class="n">valid_sampler</span> <span class="o">=</span> <span class="n">SubsetRandomSampler</span><span class="p">(</span><span class="n">valid_idx</span><span class="p">)</span>

<span class="c1"># prepare data loaders</span>
<span class="n">train_loader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">train_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="n">batch_size</span><span class="p">,</span>
    <span class="n">sampler</span><span class="o">=</span><span class="n">train_sampler</span><span class="p">,</span> <span class="n">num_workers</span><span class="o">=</span><span class="n">num_workers</span><span class="p">)</span> <span class="c1"># for validation: sampler = train_sampler</span>
<span class="n">valid_loader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">train_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="n">batch_size</span><span class="p">,</span> 
    <span class="n">sampler</span><span class="o">=</span><span class="n">valid_sampler</span><span class="p">,</span> <span class="n">num_workers</span><span class="o">=</span><span class="n">num_workers</span><span class="p">)</span> <span class="c1"># for validation: sampler = train_sampler</span>
<span class="n">test_loader</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">utils</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">DataLoader</span><span class="p">(</span><span class="n">test_data</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">=</span><span class="n">batch_size</span><span class="p">,</span> 
    <span class="n">num_workers</span><span class="o">=</span><span class="n">num_workers</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Visualize-a-batch">Visualize a batch<a class="anchor-link" href="#Visualize-a-batch">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[2]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="o">%</span><span class="k">matplotlib</span> inline
    
<span class="c1"># obtain one batch of training images</span>
<span class="n">dataiter</span> <span class="o">=</span> <span class="nb">iter</span><span class="p">(</span><span class="n">train_loader</span><span class="p">)</span>
<span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">dataiter</span><span class="o">.</span><span class="n">next</span><span class="p">()</span>
<span class="n">images</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">numpy</span><span class="p">()</span>

<span class="c1"># plot the images in the batch, along with the corresponding labels</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">25</span><span class="p">,</span> <span class="mi">4</span><span class="p">))</span>
<span class="k">for</span> <span class="n">idx</span> <span class="ow">in</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="mi">20</span><span class="p">):</span>
    <span class="n">ax</span> <span class="o">=</span> <span class="n">fig</span><span class="o">.</span><span class="n">add_subplot</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="n">batch_size</span><span class="o">/</span><span class="mi">2</span><span class="p">,</span> <span class="n">idx</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">xticks</span><span class="o">=</span><span class="p">[],</span> <span class="n">yticks</span><span class="o">=</span><span class="p">[])</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">squeeze</span><span class="p">(</span><span class="n">images</span><span class="p">[</span><span class="n">idx</span><span class="p">]),</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;gray&#39;</span><span class="p">)</span>
    <span class="c1"># print out the correct label for each image</span>
    <span class="c1"># .item() gets the value contained in a Tensor</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">labels</span><span class="p">[</span><span class="n">idx</span><span class="p">]</span><span class="o">.</span><span class="n">item</span><span class="p">()))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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buM5c+aktzEAQGhq165t4yAIVO2YY45R+fTp0218/PHHp7cxAJFTp04dG991112q1r59+4S3s2vXLhv7s77Hjh1r4/nz56vahg0bEt5HpnGnLgAAAAAAAABECIu6AAAAAAAAABAhjF8AEuA/Hu8/TmqMsXGLFi1UjfEL+VfJkiVV3rFjRxsfffTRqla9enWV5+YxEddBBx1k49KlS6sa4xcAZEr9+vVtPGLECFUrVqyYjRs3bqxqS5YsSWdbAFLAv+6tWLFizNe+/PLLKl+5cmVC+6hUqZLKr7322gS70/bs2WPjxx57LKltID0uu+yyhF9bs2bNNHYCIGr8NZXJkyfb2B9ruHPnzr+M/4p7jdqlSxdVc/N77rlH1R599NEDdBwe7tQFAAAAAAAAgAhhURcAAAAAAAAAIoRFXQAAAAAAAACIkKyeqVu2bFmVX3nllTFf+8svv9j4tddei/m6Qw89VOWtW7dWefPmzW188cUXq9qGDRtsfN5556na/PnzY+4T0VS0aFEbX3rppQm/7913301HOwhJ4cKFVe7O2rnrrrtU7aijjkp4u7t27bKxPwvXnfVTpkwZVZsxY0bM96FgKV68uMpvvvlmG1944YWq5s54PvLII9PbGPKNUqVK2fihhx5SNfd4mzhxoqrdcccdNl6xYkWaugOQF//6179U7n7Pcv/ui+jfjvDdf//9Kt+7d29S/fi/E5AM//uZ+70OmXfIIYfYOAiCEDtBbgwcOFDl/mzR/OYf//iHyvv06WPjbdu2Zbod7OeeP0Tin0NOOeUUGx/o94xq1apl4xdffFHV6tata+MePXqomrvdN998M+4+Mo07dQEAAAAAAAAgQljUBQAAAAAAAIAICX38QtWqVVVerVo1G99yyy2q1rZt25jb2b59u4179+6taoUK/bF2XbJkSVWrUaNGzG36t3i77z3++ONVjfEL+U+LFi1sfPbZZyf8viZNmqj8888/T1lPyDz3cQ4RkWeffTah97kjYUREhg0bpvJZs2bZ+K233lK1Y445xsZ9+/ZVtRtuuMHGW7ZsSagXZJfDDjtM5atWrYr52tNPP13llSpVsvGdd96pauecc07M7axcuTI3LaKAatSokcrdx7Nr1qyparfffruN/fPizp0709AdgNzyr2GmTp1qY/+zKN6IhXj871bJcseXLVy4UNWmTJli408/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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="View-an-Image-in-More-Detail">View an Image in More Detail<a class="anchor-link" href="#View-an-Image-in-More-Detail">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[3]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">img</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">squeeze</span><span class="p">(</span><span class="n">images</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span>

<span class="n">fig</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span> <span class="o">=</span> <span class="p">(</span><span class="mi">12</span><span class="p">,</span><span class="mi">12</span><span class="p">))</span> 
<span class="n">ax</span> <span class="o">=</span> <span class="n">fig</span><span class="o">.</span><span class="n">add_subplot</span><span class="p">(</span><span class="mi">111</span><span class="p">)</span>
<span class="n">ax</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">img</span><span class="p">,</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;gray&#39;</span><span class="p">)</span>
<span class="n">width</span><span class="p">,</span> <span class="n">height</span> <span class="o">=</span> <span class="n">img</span><span class="o">.</span><span class="n">shape</span>
<span class="n">thresh</span> <span class="o">=</span> <span class="n">img</span><span class="o">.</span><span class="n">max</span><span class="p">()</span><span class="o">/</span><span class="mf">2.5</span>
<span class="k">for</span> <span class="n">x</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">width</span><span class="p">):</span>
    <span class="k">for</span> <span class="n">y</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">height</span><span class="p">):</span>
        <span class="n">val</span> <span class="o">=</span> <span class="nb">round</span><span class="p">(</span><span class="n">img</span><span class="p">[</span><span class="n">x</span><span class="p">][</span><span class="n">y</span><span class="p">],</span><span class="mi">2</span><span class="p">)</span> <span class="k">if</span> <span class="n">img</span><span class="p">[</span><span class="n">x</span><span class="p">][</span><span class="n">y</span><span class="p">]</span> <span class="o">!=</span><span class="mi">0</span> <span class="k">else</span> <span class="mi">0</span>
        <span class="n">ax</span><span class="o">.</span><span class="n">annotate</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">val</span><span class="p">),</span> <span class="n">xy</span><span class="o">=</span><span class="p">(</span><span class="n">y</span><span class="p">,</span><span class="n">x</span><span class="p">),</span>
                    <span class="n">horizontalalignment</span><span class="o">=</span><span class="s1">&#39;center&#39;</span><span class="p">,</span>
                    <span class="n">verticalalignment</span><span class="o">=</span><span class="s1">&#39;center&#39;</span><span class="p">,</span>
                    <span class="n">color</span><span class="o">=</span><span class="s1">&#39;white&#39;</span> <span class="k">if</span> <span class="n">img</span><span class="p">[</span><span class="n">x</span><span class="p">][</span><span class="n">y</span><span class="p">]</span><span class="o">&lt;</span><span class="n">thresh</span> <span class="k">else</span> <span class="s1">&#39;black&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


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
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Define-Classifier">Define Classifier<a class="anchor-link" href="#Define-Classifier">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[4]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">torch.nn</span> <span class="k">as</span> <span class="nn">nn</span>
<span class="kn">import</span> <span class="nn">torch.nn.functional</span> <span class="k">as</span> <span class="nn">F</span>

<span class="c1"># define the CNN architecture</span>
<span class="k">class</span> <span class="nc">Net</span><span class="p">(</span><span class="n">nn</span><span class="o">.</span><span class="n">Module</span><span class="p">):</span>
    <span class="k">def</span> <span class="nf">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="nb">super</span><span class="p">(</span><span class="n">Net</span><span class="p">,</span> <span class="bp">self</span><span class="p">)</span><span class="o">.</span><span class="fm">__init__</span><span class="p">()</span>
       <span class="c1"># convolutional layer (sees 28x28x1 image tensor)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">conv1</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">Conv2d</span><span class="p">(</span><span class="mi">1</span><span class="p">,</span> <span class="mi">4</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="n">padding</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
        <span class="c1"># convolutional layer (sees 14x14x4 tensor after MaxPool)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">conv2</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">Conv2d</span><span class="p">(</span><span class="mi">4</span><span class="p">,</span> <span class="mi">16</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="n">padding</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
        <span class="c1"># max pooling layer</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">pool</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">MaxPool2d</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)</span>
        <span class="c1"># linear layer (7 * 7 * 16)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">fc1</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">7</span> <span class="o">*</span> <span class="mi">7</span> <span class="o">*</span> <span class="mi">16</span><span class="p">,</span> <span class="mi">512</span><span class="p">)</span>
        <span class="c1"># linear layer (512 -&gt; 10)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">fc2</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">Linear</span><span class="p">(</span><span class="mi">512</span><span class="p">,</span> <span class="mi">10</span><span class="p">)</span>
        <span class="c1"># dropout layer (p=0.20)</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">dropout</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">Dropout</span><span class="p">(</span><span class="mf">0.20</span><span class="p">)</span>
        
        
    <span class="k">def</span> <span class="nf">forward</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">x</span><span class="p">):</span>
        <span class="c1"># add sequence of convolutional and max pooling layers</span>
        <span class="n">x</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">pool</span><span class="p">(</span><span class="n">F</span><span class="o">.</span><span class="n">relu</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">conv1</span><span class="p">(</span><span class="n">x</span><span class="p">)))</span>
        <span class="n">x</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">pool</span><span class="p">(</span><span class="n">F</span><span class="o">.</span><span class="n">relu</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">conv2</span><span class="p">(</span><span class="n">x</span><span class="p">)))</span>
        <span class="c1"># flatten image input</span>
        <span class="n">x</span> <span class="o">=</span> <span class="n">x</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span> <span class="mi">7</span> <span class="o">*</span> <span class="mi">7</span> <span class="o">*</span> <span class="mi">16</span><span class="p">)</span>
        <span class="c1"># add dropout layer</span>
        <span class="n">x</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">dropout</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
        <span class="c1"># add 1st hidden layer, with relu activation function</span>
        <span class="n">x</span> <span class="o">=</span> <span class="n">F</span><span class="o">.</span><span class="n">relu</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">fc1</span><span class="p">(</span><span class="n">x</span><span class="p">))</span>
        <span class="c1"># add dropout layer</span>
        <span class="n">x</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">dropout</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
        <span class="c1"># add 2nd hidden layer, with relu activation function</span>
        <span class="n">x</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">fc2</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
        <span class="c1"># LogSoftMax</span>
        <span class="k">return</span> <span class="n">F</span><span class="o">.</span><span class="n">log_softmax</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">dim</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
        
<span class="c1"># create a complete CNN</span>
<span class="n">model</span> <span class="o">=</span> <span class="n">Net</span><span class="p">()</span>
<span class="nb">print</span><span class="p">(</span><span class="n">model</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Net(
  (conv1): Conv2d(1, 4, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
  (conv2): Conv2d(4, 16, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
  (pool): MaxPool2d(kernel_size=2, stride=2, padding=0, dilation=1, ceil_mode=False)
  (fc1): Linear(in_features=784, out_features=512, bias=True)
  (fc2): Linear(in_features=512, out_features=10, bias=True)
  (dropout): Dropout(p=0.2)
)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Set-Loss-Function-and-Optimizer">Set Loss Function and Optimizer<a class="anchor-link" href="#Set-Loss-Function-and-Optimizer">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[5]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">torch</span> <span class="k">import</span> <span class="n">optim</span>

<span class="c1"># Loss Function and Optimizer</span>
<span class="n">criterion</span> <span class="o">=</span> <span class="n">nn</span><span class="o">.</span><span class="n">NLLLoss</span><span class="p">()</span>
<span class="n">optimizer</span> <span class="o">=</span> <span class="n">optim</span><span class="o">.</span><span class="n">Adam</span><span class="p">(</span><span class="n">model</span><span class="o">.</span><span class="n">parameters</span><span class="p">(),</span> <span class="n">lr</span><span class="o">=</span><span class="mf">0.003</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Set-Cuda">Set Cuda<a class="anchor-link" href="#Set-Cuda">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[6]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># move tensors to GPU if CUDA is available</span>
<span class="n">train_on_gpu</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">cuda</span><span class="o">.</span><span class="n">is_available</span><span class="p">()</span>
<span class="k">if</span> <span class="n">train_on_gpu</span><span class="p">:</span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;CUDA is available!  Training on GPU ...&#39;</span><span class="p">)</span>
    <span class="n">model</span><span class="o">.</span><span class="n">cuda</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Train">Train<a class="anchor-link" href="#Train">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[8]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">epochs</span> <span class="o">=</span> <span class="mi">5</span>
<span class="n">steps</span> <span class="o">=</span> <span class="mi">0</span>
<span class="n">valid_loss_min</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">Inf</span> <span class="c1"># track change in validation loss</span>

<span class="n">train_losses</span><span class="p">,</span> <span class="n">test_losses</span> <span class="o">=</span> <span class="p">[],</span> <span class="p">[]</span>
<span class="k">for</span> <span class="n">epoch</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">epochs</span><span class="p">):</span>
    
    <span class="n">train_loss</span> <span class="o">=</span> <span class="mf">0.0</span>
    <span class="n">valid_loss</span> <span class="o">=</span> <span class="mf">0.0</span>
    
    <span class="n">model</span><span class="o">.</span><span class="n">train</span><span class="p">()</span>
    
    <span class="k">for</span> <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="ow">in</span> <span class="n">train_loader</span><span class="p">:</span>
        
        <span class="k">if</span> <span class="n">train_on_gpu</span><span class="p">:</span>
            <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">cuda</span><span class="p">(),</span> <span class="n">labels</span><span class="o">.</span><span class="n">cuda</span><span class="p">()</span>
            
        <span class="n">optimizer</span><span class="o">.</span><span class="n">zero_grad</span><span class="p">()</span>
        
        <span class="n">log_ps</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>
        <span class="n">loss</span> <span class="o">=</span> <span class="n">criterion</span><span class="p">(</span><span class="n">log_ps</span><span class="p">,</span> <span class="n">labels</span><span class="p">)</span>
        <span class="n">loss</span><span class="o">.</span><span class="n">backward</span><span class="p">()</span>
        <span class="n">optimizer</span><span class="o">.</span><span class="n">step</span><span class="p">()</span>
        
        <span class="n">train_loss</span> <span class="o">+=</span> <span class="n">loss</span><span class="o">.</span><span class="n">item</span><span class="p">()</span>

    <span class="n">model</span><span class="o">.</span><span class="n">eval</span><span class="p">()</span>
    <span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
        <span class="k">for</span> <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="ow">in</span> <span class="n">valid_loader</span><span class="p">:</span>
            <span class="c1"># move tensors to GPU if CUDA is available</span>
            <span class="k">if</span> <span class="n">train_on_gpu</span><span class="p">:</span>
                <span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">cuda</span><span class="p">(),</span> <span class="n">labels</span><span class="o">.</span><span class="n">cuda</span><span class="p">()</span>

            <span class="c1"># forward pass: compute predicted outputs by passing inputs to the model</span>
            <span class="n">output</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>
            <span class="c1"># calculate the batch loss</span>
            <span class="n">loss</span> <span class="o">=</span> <span class="n">criterion</span><span class="p">(</span><span class="n">output</span><span class="p">,</span> <span class="n">labels</span><span class="p">)</span>
            <span class="c1"># update average validation loss </span>
            <span class="n">valid_loss</span> <span class="o">+=</span> <span class="n">loss</span><span class="o">.</span><span class="n">item</span><span class="p">()</span>
    
    <span class="c1"># calculate average losses</span>
    <span class="n">train_loss</span> <span class="o">=</span> <span class="n">train_loss</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">train_loader</span><span class="o">.</span><span class="n">sampler</span><span class="p">)</span>
    <span class="n">valid_loss</span> <span class="o">=</span> <span class="n">valid_loss</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">valid_loader</span><span class="o">.</span><span class="n">sampler</span><span class="p">)</span>
        
    <span class="n">train_losses</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">train_loss</span><span class="p">)</span>
    <span class="n">test_losses</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">valid_loss</span><span class="p">)</span>
        
    <span class="c1"># print training/validation statistics </span>
    <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Epoch: </span><span class="si">{}</span><span class="s1"> </span><span class="se">\t</span><span class="s1">Training Loss: </span><span class="si">{:.6f}</span><span class="s1"> </span><span class="se">\t</span><span class="s1">Validation Loss: </span><span class="si">{:.6f}</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span>
        <span class="n">epoch</span><span class="p">,</span> <span class="n">train_loss</span><span class="p">,</span> <span class="n">valid_loss</span><span class="p">))</span>
    
    <span class="c1"># save model if validation loss has decreased</span>
    <span class="k">if</span> <span class="n">valid_loss</span> <span class="o">&lt;=</span> <span class="n">valid_loss_min</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Validation loss decreased (</span><span class="si">{:.6f}</span><span class="s1"> --&gt; </span><span class="si">{:.6f}</span><span class="s1">).  Saving model ...&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span>
        <span class="n">valid_loss_min</span><span class="p">,</span>
        <span class="n">valid_loss</span><span class="p">))</span>
        <span class="n">torch</span><span class="o">.</span><span class="n">save</span><span class="p">(</span><span class="n">model</span><span class="o">.</span><span class="n">state_dict</span><span class="p">(),</span> <span class="s1">&#39;model.pt&#39;</span><span class="p">)</span>
        <span class="n">valid_loss_min</span> <span class="o">=</span> <span class="n">valid_loss</span>        
        
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Epoch: 0 	Training Loss: 0.007150 	Validation Loss: 0.004005
Validation loss decreased (inf --&gt; 0.004005).  Saving model ...
Epoch: 1 	Training Loss: 0.004595 	Validation Loss: 0.002991
Validation loss decreased (0.004005 --&gt; 0.002991).  Saving model ...
Epoch: 2 	Training Loss: 0.003939 	Validation Loss: 0.002648
Validation loss decreased (0.002991 --&gt; 0.002648).  Saving model ...
Epoch: 3 	Training Loss: 0.003619 	Validation Loss: 0.003225
Epoch: 4 	Training Loss: 0.003354 	Validation Loss: 0.003415
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Check-Losses">Check Losses<a class="anchor-link" href="#Check-Losses">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[9]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="n">x</span> <span class="o">=</span> <span class="nb">range</span><span class="p">(</span><span class="n">epochs</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">train_losses</span><span class="p">,</span> <span class="n">label</span> <span class="o">=</span> <span class="s2">&quot;Train losses&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">test_losses</span><span class="p">,</span> <span class="n">label</span> <span class="o">=</span> <span class="s2">&quot;Validation losses&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s2">&quot;Traning losses vs Validation losses&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s2">&quot;Epoch&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s2">&quot;Losses&quot;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">()</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAZIAAAEWCAYAAABMoxE0AAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4zLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvnQurowAAIABJREFUeJzt3Xl8VPX1//HXyUIC2YAQICEgq0AIAQIiuCEFWbSKCyh+3ZfautR9ba27Fa211Gpr1crP1gUBxSKKWBRFqwVB2RcJixLCkrAkJAFCkvP7496EYcgykExulvN8POaRmbvNmTuZec/93Hs/V1QVY4wx5niFeF2AMcaYhs2CxBhjTI1YkBhjjKkRCxJjjDE1YkFijDGmRixIjDHG1IgFiak1InKViMwJ0rIzReTMYCy7MRGRr0Tkavd+le+H77TH8TxdRST/+KqscrlhIqIi0rm2l22Cx4KkERORfJ9bqYjs93l8WW0/n6q+rqpja3u5TYWIXCEiGyoY3kxEckRkzLEsrzbfD/8gV9WNqhpdG8s2DZ8FSSOmqtFlN+An4FyfYW/6Ty8iYXVfpfHxLpAgIqf5DT8bKAL+U/clGVM9C5ImTESeEJF3RORtEdkHXC4iQ0XkfyKyV0S2icjzIhLuTl/W7PBLEckQkT0i8rzP8q4Xkc8DnDZURCaLyC4R2SgivxaRgLpZEJFIt65tIrJVRJ4TkWbuuLYi8pFb/24RWeAz329EJEtE8kRkbdkvbBEJccdtcH/5TxWRVu64FiLyllvnXhFZJCJtKqjpQRGZ6jfsRRF5zr1/nYhsFpF97uud6L8MVS0EZgBX+o26EnhDVUtEJN59fdnuOv1ARDpUsp7K3w/38RgRWSciuSLyZ0B8xvUQkfnu68wRkX+JSJw77m0gCZjjbs3eKSLdfd8vEUkWkdnuOl8vItf6jHvC/R97w339K0UkvaKaK3gNLd35st3194CIiDvuRBFZ4L6eHBF5yx0e4v5/7HTHLReRFHdcpPv/skVEdojIX0Uk0h1X6f+OqYaq2q0J3IDNwEi/YU/g/NI9F+dHRXPgJOBkIAzoCvwA3OJOHwYo8G8gDugM7C5bLnA98HmA094CrAQ6AK2B+c6/Y6X1ZwJnuvd/D3wNJABtgYXAw+64PwAvAOFAM2CYO7wP8CPQ3n3cBejq3r8b+K9bSyTwD+Bf7ribgffddRMKDAKiK6ivK5APRPm8/p3u9LFALtDDHZcIpFTyOocBe4FI93Er4CCQ6j5OAC5w64kF3gNm+Mz/FXB1Be9HW7e+C9x1cw9Q7DPticAId521ddfHsxWtf/dxd9/3y53+L+76SwdyfNb9E8B+YLS7Dv8AfFXJ6y/7v+nsPn7LfY0x7jrOAK5yx00H7sP5340ETnWHnwMswvm/CwFSfN73F4CZ7nqNBT4CHq/qf8duAXy/eF2A3eroja48SD6rZr67genu/bIP+RCf8e8Bd7v3KwqSyqZdAFznM24MgQfJj8Aon3HnABnu/d+7z9PNb/6ewA73yzLMb9x63y8NoCPOl3cIcAPOl3PfANbx/4D/c++PBX5w78fihMMFuAFRxTIE2Ahc7D6+EVhSxfSDgGyfx5UFybW+X97ua9tWNm0Fyx0PfFvR+ncflwcJTigfwg1Rd9gfgFd9/s8+9hmXBuRX8rzlQeJ+oRcDJ/qMvxmY595/C/gb0MFvGaOAtTg/iEL8XvMB4ASfYacD66v637Fb9Tdr2jJbfB+ISC8R+VBEtotIHvAY4N+Us93nfiFQ1U7XyqZN8nvuI+qoRiJOmJT5EWdrAmCS+/hTt6nqHgBVXQfchfN6drpNLe3deToBH7hNGnuBFThfZm2B/wfMA6a5zWiTpPJ9SW8Bl7r3/w94033uPHf4zcB2twnoxIoW4H4z/4vDzVtXAK+XjReRKBF5VUR+ct+fzzj6/anIEetbVUtxwqFsue1FpOw15rmvO5Dlli07R1ULfIb5vidw9P9BVADLbYuzBVPZe30XTtgsFpEVInIVgKp+AryEEzI7ROQlEYkB2gMRwDKf93q2+zxQyf+OqZ4FifHfL/F3nCan7qoaCzyET1t6LdoGJPs87niM857g87gTsBWcL21VvUNVOwPnA/eJyDB33BuqeirOL+hQ4Cl3/kzgLFVt6XOLVNXtqlqkqo+oam/gNJytisqOeHsHGCkiycA4nGDBfe45qjoSJwQzcNZzZf4JjBKRU3C2ON72GXevW/9g9/35WRXL8bUNn3UsIiEcuf6fxtkK6+su92qOfN+r2n+VBbQREd9wKH9PamAnUELl7/U2Vb1eVRNxQvplEenijpusqulAKk7T1p04W6RFQE+f9zlOVePceSr93zFVsyAx/mJw2vMLRKQ38MsgPc804HYRSXJ3bB/Lr7+3gYdEpI2IJAC/A94AEJFzRaSbu0M2F+eLqEREeovIcBGJwGmv3++OA+fX6+9FpJO7jLYicp57/2cikup+8ebhNOGUUAFV3YHTtDQFWKeq691lJLp1tcD5IiuobBnucjbg7Pd5C5ijqtk+o2NwftHvEZF4nKAPxGygv4iMc7eo7sDZ3+K73AIgV0Q64jRp+tqBs4+iono3AYtx1mGEiPQHrsHdIjteqnoI5+CD34tItBsSd3D4vb7Y50CDvThhVyIig91bmPuaioASVS0BXgUmi0iCOJJFZJS7vAr/d2ryGpoKCxLj7y7gKmAfzq/md4L0PH8DPsdpRloCfIjzgQ/Eo8Ayd97lOF+6ZVsXPXGae/JxdgD/WVW/wmnSeAZnJ/B2nJ2tD7rzPAd8jNOksQ9nR/5J7rgknHbzPGAVTjOX7xaCv7eAkfhsjeBs/dyDs1WwCzgF52CDqryO80v8n37Dn8PZibzLrTOgE0DdkLsEZ9/FLpxf9gt9JnkYGIzzBToL51BkX78HHnWbhG6v4CkuAXrgrNsZwG9UdX4gtVXjJpz/i03AFzjrpWydnAx8KyIFOO/Rzar6E9AS54CJvTj7BrcBf3LnuQun+WoRzmv9xK0bKv/fMdUQdyeTMZ4SkXOByarazetajDHHxrZIjCfcncZjxDmfJBmniWam13UZY46dbZEYT4hINE5TRU+cduzZwO2qus/Twowxx8yCxBhjTI1Y05YxxpgaaRKd9LVp00Y7d+7sdRnGGNNgLFmyJEdVE6qfsokESefOnVm8eLHXZRhjTIMhIj9WP5XDmraMMcbUiAWJMcaYGrEgMcYYUyNNYh+JMaZmDh06RGZmJgcOHPC6FFPLIiMjSU5OJjw8/LiXYUFijKlWZmYmMTExdO7cGfcChaYRUFV27dpFZmYmXbp0Oe7lWNOWMaZaBw4cID4+3kKkkRER4uPja7ylaUFijAmIhUjjVBvvqwVJJYpLSvnr5xks3bLX61KMMaZesyCpROGhEt745kfumraUA4fs2jbGeGnXrl3079+f/v370759ezp06FD+uKgosMvYXHPNNaxbty7g53z11Ve5/faKLr1i/NnO9krERobz9Pg0rvjHIp6du44Hf57idUnGNFnx8fEsXboUgEceeYTo6GjuvvvIiziqKqpKSEjFv4+nTJkS9DqbKtsiqcLpPRK4fEgn/vHfTSzatNvrcowxfjIyMkhNTeVXv/oV6enpbNu2jRtuuIFBgwbRp08fHnvssfJpTzvtNJYuXUpxcTEtW7bk/vvvp1+/fgwdOpSdO3dW+TybNm1i+PDhpKWlcdZZZ5GZmQnA1KlTSU1NpV+/fgwfPhyAFStWcNJJJ9G/f3/S0tLYuHEjAK+//jqDBw+mf//+3HTTTZSWllJcXMwVV1xB3759SU1N5fnnnw/Smgou2yKpxgNje7Pghxzunr6MObedTlSErTLTtD36wSpWZ+XV6jJTkmJ5+Nw+xzXv6tWrmTJlCi+99BIAkyZNonXr1hQXFzN8+HDGjx9PSsqRLQq5ubkMGzaMSZMmceedd/Laa69x//33V/ocN910E9dffz2XXXYZL7/8MrfffjszZszg0Ucf5fPPP6ddu3bs3evsT/3rX//K3XffzSWXXMLBgwdRVVauXMnMmTP5+uuvCQsL44YbbmDq1Kl069aNnJwcVqxYAVC+jIYmqFsk7hXw1olIhogc9S6JSISIvOOOXyginX3GPeAOXycio91hPUVkqc8tr5LrR9eaqIgwnp3Qjy17Cpk0Z20wn8oYcxy6devGSSedVP747bffJj09nfT0dNasWcPq1auPmqd58+aMHTsWgIEDB7J58+Yqn2PhwoVMnDgRgCuvvJIvv/wSgFNPPZUrr7ySV199ldLSUgBOOeUUnnjiCZ555hm2bNlCZGQk8+bN49tvv2XQoEH079+fL774gg0bNtC9e3fWrVvHbbfdxty5c4mLi6uNVVLngvbzWkRCgReBs4BM4FsRmaWqvu/qdcAeVe0uIhOBp4FLRCQFmAj0AZKAeSJyoqquA/r7LH8rdXB51sFdWnPdqV149atNjOrTjtN7BNSzsjGN0vFuOQRLVFRU+f3169fz5z//mUWLFtGyZUsuv/zyCs+RaNasWfn90NBQiouLj+u5X3nlFRYuXMjs2bPp168fy5cv54orrmDo0KF8+OGHnHXWWbz++uuoKtdeey2PP/74UctYvnw5c+bM4fnnn+fdd9/l5ZdfPq5avBTMLZLBQIaqblTVImAqMM5vmnHA6+79GcAIcQ5qHgdMVdWDqroJyHCX52sEsEFVA+7quCbuHt2TbglR3DtjOXkHDtXFUxpjjlFeXh4xMTHExsaybds25s6dWyvLHTJkCNOmTQPgjTfe4IwzzgBg48aNDBkyhMcff5xWrVqxdetWNm7cSPfu3bnttts455xzWL58OSNHjmTatGnk5OQAzlFoP/30E9nZ2agqEyZM4NFHH+W7776rlXrrWjAb/DsAW3weZwInVzaNqhaLSC4Q7w7/n9+8HfzmnQi8XdmTi8gNwA0AnTp1Oo7yjxQZHsofL+7PhX/9L49/sJo/TOhX42UaY2pXeno6KSkppKam0rVrV0499dRaWe4LL7zAddddx1NPPUW7du3KjwC744472LRpE6rKqFGjSE1N5YknnuDtt98mPDycpKQknnjiCVq2bMnDDz/MyJEjKS0tJTw8nJdeeonQ0FCuu+46VBUR4emnn66Veuta0K7ZLiITgNGqer37+ApgsKr+2meaVe40me7jDThbHo8B36jqG+7wfwAfqeq77uNmQBbQR1V3VFfLoEGDtLYubPXs3HW8MD+DV68cxMiUdrWyTGPquzVr1tC7d2+vyzBBUtH7KyJLVHVQIPMHs2krE+jo8zgZ58u/wmlEJAyIA3YHMO9Y4LtAQqS23TqiB73ax3D/eyvYUxDYiVDGGNOYBTNIvgV6iEgXdwtiIjDLb5pZwFXu/fHAZ+psIs0CJrpHdXUBegCLfOa7lCqatYKpWVgIz13cn9z9RTw0a5UXJRhjTL0StCBR1WLgFmAusAaYpqqrROQxETnPnewfQLyIZAB3Ave7864CpgGrgY+Bm1W1BEBEWuAcCfZesGqvTkpSLLeN6MEHy7KYvdx/I8sYY5qWoJ5dp6ofAR/5DXvI5/4BYEIl8z4JPFnB8EKcHfKe+tWwbvxn9Q5+9/5KTu4ST0JMhNclGWOMJ6yLlOMUFhrCHy/uR0FRCQ+8t4JgHbRgjDH1nQVJDXRvG8O9o3syb80O3vtuq9flGGOMJyxIauiaU7twUudWPPLBKrbl7ve6HGMapTPPPPOokwsnT57MTTfdVOV80dHRAGRlZTF+/PhKl13d6QGTJ0+msLCw/PHZZ59dK/1iPfLIIzz77LM1Xo7XLEhqKDREeHZCP4pLlHtnLLcmLmOC4NJLL2Xq1KlHDJs6dSqXXnppQPMnJSUxY8aM435+/yD56KOPaNmy5XEvr7GxIKkFJ8RH8ZtzevPl+hzeWvST1+UY0+iMHz+e2bNnc/DgQQA2b95MVlYWp512Gvn5+YwYMYL09HT69u3Lv//976Pm37x5M6mpqQDs37+fiRMnkpaWxiWXXML+/YdbEm688cbyLugffvhhAJ5//nmysrIYPnx4eVfxnTt3Lu/u5LnnniM1NZXU1FQmT55c/ny9e/fmF7/4BX369GHUqFFHPE9Fli5dypAhQ0hLS+OCCy5gz5495c+fkpJCWlpaeceRX3zxRfmFvQYMGMC+ffsA+MMf/sBJJ51EWlpaef0FBQWcc8459OvXj9TUVN55553jeAeqZn2i15LLT+7E3JXbefLDNZzePYFO8S28LsmY4JhzP2xfUbvLbN8Xxk6qdHR8fDyDBw/m448/Zty4cUydOpVLLrkEESEyMpKZM2cSGxtLTk4OQ4YM4bzzzqv0WuR/+9vfaNGiBcuXL2f58uWkp6eXj3vyySdp3bo1JSUljBgxguXLl3Prrbfy3HPPMX/+fNq0aXPEspYsWcKUKVNYuHAhqsrJJ5/MsGHDaNWqFevXr+ftt9/mlVde4eKLL+bdd9/l8ssvr/Q1XnnllfzlL39h2LBhPPTQQzz66KNMnjyZSZMmsWnTJiIiIsqb05599llefPFFTj31VPLz84mMjOSTTz5h/fr1LFq0CFXlvPPOY8GCBWRnZ5OUlMSHH34IOF3o1zbbIqklIsLT49MIFeHuGcsoLbUmLmNqk2/zlm+zlqrym9/8hrS0NEaOHMnWrVvZsaPyTi8WLFhQ/oWelpZGWlpa+bhp06aRnp7OgAEDWLVqVYVd0Pv66quvuOCCC4iKiiI6OpoLL7ywvIv5Ll260L9/f6D6rupzc3PZu3cvw4YNA+Cqq65iwYIF5TVedtllvPHGG4SFOb/9Tz31VO68806ef/559u7dS1hYGJ988gmffPIJAwYMID09nbVr17J+/Xr69u3LvHnzuO+++/jyyy+D0lW9bZHUog4tm/PQuSncM2M5U77ezHWndfG6JGNqXxVbDsF0/vnnc+edd/Ldd9+xf//+8i2JN998k+zsbJYsWUJ4eDidO3eusOt4XxVtrWzatIlnn32Wb7/9llatWnH11VdXu5yq9olGRBw+tyw0NLTapq3KfPjhhyxYsIBZs2bx+OOPs2rVKu6//37OOeccPvroI4YMGcK8efNQVR544AF++ctfHrWMJUuW8NFHH/HAAw8watQoHnrooQqe6fjZFkktGz8wmRG92vLMx2vZkJ3vdTnGNBrR0dGceeaZXHvttUfsZM/NzaVt27aEh4czf/58fvyx6itLnHHGGbz55psArFy5kuXLlwNOF/RRUVHExcWxY8cO5syZUz5PTExM+X4I/2W9//77FBYWUlBQwMyZMzn99NOP+bXFxcXRqlWr8q2Zf/3rXwwbNozS0lK2bNnC8OHDeeaZZ9i7dy/5+fls2LCBvn37ct999zFo0CDWrl3L6NGjee2118jPd753tm7dys6dO8nKyqJFixZcfvnl3H333UHpqt62SGqZiPDUhX0ZNXkBd01bxoxfDSUs1PLamNpw6aWXcuGFFx5xBNdll13GueeeW371wV69elW5jBtvvJFrrrmGtLQ0+vfvz+DBzqWO+vXrx4ABA+jTp89RXdDfcMMNjB07lsTERObPn18+PD09nauvvrp8Gddffz0DBgyo9oqLFXn99df51a9+RWFhIV27dmXKlCmUlJRw+eWXk5ubi6pyxx130LJlS373u98xf/58QkNDSUlJYezYsURERLBmzRqGDh0KOMH7xhtvkJGRwT333ENISAjh4eH87W9/O+baqhO0buTrk9rsRj5QHyzL4tdvf889o3ty8/DudfrcxtQ260a+cavP3cg3aef2S+KcvolMnvcDa7bleV2OMcYEjQVJED1+fipxzcO5a9oyiopLvS7HGGOCwoIkiFpHNeOpC9NYvS2PFz5b73U5xtRIU2gGb4pq4321IAmys1LacWF6B178fAPLttS8bx5jvBAZGcmuXbssTBoZVWXXrl1ERkbWaDl21FYdePjcPnydsYu7pi9j9q9PIzI81OuSjDkmycnJZGZmkp2d7XUpppZFRkaSnJxco2VYkNSBuObhPD0+jateW8Rz//mB35xtR7+YhiU8PJwuXewEW1Mxa9qqI8NOTOD/Tu7EK19uZPHm3V6XY4wxtcaCpA795uzeJLdqzl3Tl1FYVOx1OcYYUyssSOpQdEQYfxjfjx93FTJpzlqvyzHGmFphQVLHhnSN59pTu/DPb37kvxk5XpdjjDE1ZkHigXvH9KRrQhT3zlhO3oFDXpdjjDE1YkHigcjwUP44oR/bcvfzxOyqr3dgjDH1nQWJRwZ0asWvhnVj2uJMPltb+UV4jDGmvrMg8dBtI3vQq30M9727gj0FRV6XY4wxx8WCxEMRYaH88eJ+7Cko4uFZq7wuxxhjjosFicf6JMVx64gezFqWxUcrtnldjjHGHDMLknrgxjO7kZYcx4PvryR730GvyzHGmGNiQVIPhIeG8McJ/cg/WMxvZ66wHlaNMQ2KBUk90aNdDHePOpFPVu/g/aVbvS7HGGMCZkFSj1x3WlcGndCKh/69im25+70uxxhjAmJBUo+EhgjPTuhHcYly37vWxGWMaRgsSOqZzm2ieODsXiz4IZup327xuhxjjKmWBUk9dPnJJ3Bq93iemL2aLbsLvS7HGGOqZEFSD4WECM+M74eIcPf0ZZSWWhOXMab+CmqQiMgYEVknIhkicn8F4yNE5B13/EIR6ewz7gF3+DoRGe0zvKWIzBCRtSKyRkSGBvM1eKVDy+Y89PMUFm7azevfbPa6HGOMqVTQgkREQoEXgbFACnCpiKT4TXYdsEdVuwN/Ap52500BJgJ9gDHAX93lAfwZ+FhVewH9gDXBeg1emzAomeE9E5g0Zy0bsvO9LscYYyoUzC2SwUCGqm5U1SJgKjDOb5pxwOvu/RnACBERd/hUVT2oqpuADGCwiMQCZwD/AFDVIlXdG8TX4CkRYdJFaUSGh3L39GWUWBOXMaYeCmaQdAB8DzvKdIdVOI2qFgO5QHwV83YFsoEpIvK9iLwqIlEVPbmI3CAii0VkcXZ2dm28Hk+0i43ksXF9+P6nvby8YKPX5RhjzFGCGSRSwTD/n9SVTVPZ8DAgHfibqg4ACoCj9r0AqOrLqjpIVQclJCQEXnU9dF6/JMamtudP//mBtdvzvC7HGGOOEMwgyQQ6+jxOBrIqm0ZEwoA4YHcV82YCmaq60B0+AydYGjUR4YnzU4mJDOOuacs4VFLqdUnGGFMumEHyLdBDRLqISDOcneez/KaZBVzl3h8PfKbO6dyzgInuUV1dgB7AIlXdDmwRkZ7uPCOAJnGt2vjoCH5/YV9WZeXxwmcZXpdjjDHlwoK1YFUtFpFbgLlAKPCaqq4SkceAxao6C2en+b9EJANnS2SiO+8qEZmGExLFwM2qWuIu+tfAm244bQSuCdZrqG9G92nPBQM68ML8DEb2bkff5DivSzLGGKQp9Oc0aNAgXbx4sddl1IrcwkOMmvwFcc3DmXXLaUSGh1Y/kzHGHCMRWaKqgwKZ1s5sb2DiWoTz9EVp/LAjnz/N+8HrcowxxoKkITqzZ1suHdyRlxdsZMmPu70uxxjTxFmQNFC/PSeFDi2bc9e0ZRQWFXtdjjGmCbMgaaCiI8L4w/h+bN5VyDMfr/O6HGNME2ZB0oAN7RbP1ad05v99vZmvM3K8LscY00RZkDRw943pRZc2UdwzYzn7DhzyuhxjTBNkQdLANW8WyrMT+rEtdz9PfthoO0I2xtRjFiSNwMATWnHDGd2Y+u0W5q/d6XU5xpgmxoKkkbjjrB6c2C6a+95dzt7CIq/LMcY0IRYkjUREWCjPXdyf3QVFPDJrldflGGOaEAuSRiS1Qxy3/Kw77y/N4uOV27wuxxjTRFiQNDI3D+9OaodYfjtzJTn5B70uxxjTBFiQNDLhoSE8d3F/9h0o5sGZK2kKnXIaY7xlQdIIndguhjtHncjHq7bz76X+1xIzxpjaZUHSSP3i9K6kd2rJQ/9eyY68A16XY4xpxCxIGqnQEOGPF/enqKSU+95dbk1cxpigsSBpxLq0ieL+Mb34fF0273y7xetyjDGNlAVJI3fl0M4M7RrP47NXs2V3odflGGMaIQuSRi4kRHhmfBoA985YTmmpNXEZY2qXBUkT0LF1C3738xS+2biLf36z2etyjDGNjAVJE3HJSR05s2cCkz5ey6acAq/LMcY0IhYkTYSI8PRFaTQLDeGuaUspsSYuY0wtsSBpQtrFRvLYuFS++2kvr3y50etyjDGNhAVJEzOufxJj+rTnuU9+4Icd+7wuxxjTCFiQNDEiwhMXpBIdGcad05ZyqKTU65KMMQ2cBUkT1CY6gt9fkMrKrXn8df4Gr8sxxjRwFiRN1JjURM7vn8RfPlvPyq25XpdjjGnALEiasEfPS6V1VDPunLaUg8UlXpdjjGmgLEiasLgW4Tx9URo/7Mhn8rz1XpdjjGmgAgoSEblNRGLF8Q8R+U5ERgW7OBN8w3u15ZJBHfn7FxtY8uMer8sxxjRAgW6RXKuqecAoIAG4BpgUtKpMnXrw571JjGvO3dOXsb/ImriMMccm0CAR9+/ZwBRVXeYzzDRwMZHh/GF8GptyCnhm7lqvyzHGNDCBBskSEfkEJ0jmikgMYCcgNCKndG/DVUNPYMp/N/P1hhyvyzHGNCCBBsl1wP3ASapaCDTDad4yjch9Y3vROb4F985YTv7BYq/LMcY0EIEGiQIpwK3u4yggsrqZRGSMiKwTkQwRub+C8REi8o47fqGIdPYZ94A7fJ2IjPYZvllEVojIUhFZHGD9JgAtmoXxx4v7kbV3P09+uMbrcowxDUSgQfJXYChwqft4H/BiVTOISKg7zVicELpURFL8JrsO2KOq3YE/AU+786YAE4E+wBjgr+7yygxX1f6qOijA+k2ABp7Qml+c3pW3F/3E5+t2el2OMaYBCDRITlbVm4EDAKq6B6d5qyqDgQxV3aiqRcBUYJzfNOOA1937M4ARIiLu8KmqelBVNwEZ7vJMHbjjrBPp0Taa+95dTm7hIa/LMcbUc4EGySF3i0ABRCSB6ne2dwC2+DzOdIdVOI2qFgO5QHw18yrwiYgsEZEbAqzfHIPI8FCeu7g/OflFPPrBKq/LMcbIKTJGAAAfyElEQVTUc4EGyfPATKCtiDwJfAX8vpp5Kjo82P9qSpVNU9W8p6pqOk6T2c0ickaFTy5yg4gsFpHF2dnZ1ZRq/PVNjuPm4d157/utfLxyu9flGGPqsYCCRFXfBO4FngK2Aeer6vRqZssEOvo8TgayKptGRMKAOGB3VfOqatnfnTjhVmGTl6q+rKqDVHVQQkJCdS/RVOCW4d3pkxTLb2euYFf+Qa/LMcbUU4F2kdIN2KSqLwIrgbNEpGU1s30L9BCRLiLSDGfn+Sy/aWYBV7n3xwOfqaq6wye6R3V1AXoAi0Qkyj2HBRGJwjnTfmUgr8Ecu2ZhIfzx4n7sO1DMg++vxHlrjDHmSIE2bb0LlIhId+BVoAvwVlUzuPs8bgHmAmuAaaq6SkQeE5Hz3Mn+AcSLSAZwJ865KqjqKmAasBr4GLhZVUuAdsBXIrIMWAR8qKofB/xqzTHr1T6W28/qwZyV25m1zH+D0hhjQAL5lSki36lquojcC+xX1b+IyPeqOiD4JdbcoEGDdPFiO+XkeBWXlDLh79+wMbuAT+44g3ax1Z5CZIxp4ERkSaCnWBzLUVuXAlcCs91h4cdTnGl4wkJD+OOEfhwsLuGB91ZYE5cx5giBBsk1OCckPqmqm9z9Fm8EryxT33RNiObe0b34bO1Opi/O9LocY0w9EuhRW6tV9VZVfVtEWgExqmrdyDcxV5/SmZO7tOax2avJ3FPodTnGmHoi0KO2PncvbNUaWAZMEZHngluaqW9CQoRnJ/RDVbl3xnJKS62JyxgTeNNWnHthqwtxrkcyEBgZvLJMfdWxdQt+e04KX2/YxRsLf/S6HGNMPRBokISJSCJwMYd3tpsm6tLBHTnjxASe+mgtm3MKvC7HGOOxQIPkMZzzQTao6rci0hVYH7yyTH0mIjx9UV/CQoW7py+jxJq4jGnSAt3ZPl1V01T1RvfxRlW9KLilmfosMa45j57Xh8U/7uEfX230uhxjjIcC3dmeLCIzRWSniOwQkXdFJDnYxZn67YIBHRiV0o5nP/mB9Tv2eV2OMcYjgTZtTcHp/yoJpzv3D9xhpgkTEZ68oC9RzUK5a/oyDpVUd2UBY0xjFGiQJKjqFFUtdm//D7AudQ0JMRE8eUFflmfm8rfPN3hdjjHGA4EGSY6IXC4ioe7tcmBXMAszDcfZfRM5r18Sz3+6nsWbd3tdjjGmjgUaJNfiHPq7Hed6JONxuk0xBoDHxvUhProZ41/6hgv/+l/eXvQT+w7YZXqNaQoC6v23whlFblfVybVcT1BY7791Iyf/IO8uyWT6kkwyduYTGR7C2NREJgxMZkjXeEJCKrrwpTGmPjqW3n9rEiQ/qWqn45q5jlmQ1C1VZemWvcxYksmsZVnsO1BMh5bNuWhgMhMGJtOxdQuvSzTGVKOugmSLqnasfkrvWZB458ChEuau2s6MJZl8lZGDKgzp2poJAzsytm97WjQL87pEY0wFbIvEjwVJ/bB1737eW5LJjO8y+XFXIdERYZzTN5EJg5IZeEIrRKzpy5j6otaCRET2ARVNIEBzVW0QPyctSOoXVWXRpt1MX5LJRyu2UVhUQtc2UVw0MJmL0pNpH2dXYDTGa3WyRdKQWJDUXwUHi/lwxTZmLMlk0abdhAic1iOBCQOTOSulHZHhoV6XaEyTZEHix4KkYdicU8C732Xy7pJMsnIPENc8nPP6JTFhUDJ9O8RZ05cxdciCxI8FScNSUqp8vSGH6Ysz+XjVdoqKS+nZLoYJg5I5f0AH2kRHeF2iMY2eBYkfC5KGK3f/IT5YlsX0JZks27KXsBBheK+2TBiYzPBebQkPDfScWmPMsbAg8WNB0jj8sGMfM5Zk8t53W8nJP0ib6Gac378DEwZ1pGf7GK/LM6ZRsSDxY0HSuBwqKeWLddnMWJLJp2t3cKhESUuOY8LAZM7r14G4FuFel2hMg2dB4seCpPHalX+Qfy91mr7WbMujWVgIo1LaMWFQR07r3oZQ65bFmONiQeLHgqRpWLk1lxlLMnl/6Vb2Fh6ifWwkF6Z3YPzAZLomRHtdnjENigWJHwuSpuVgcQmfrtnJ9MVb+OKHbEoVBp3QigmDkjknLYnoiAZxHq0xnrIg8WNB0nTtyDvAe99tZfqSLWzMLqB5eChj+7ZnwsCOnNyltfVIbEwlLEj8WJAYVeW7n5weiWcvy2LfwWI6tm7O+PSOXDSwA8mtrEdiY3xZkPixIDG+9hc5PRJPX7KF/2bsQgRO6RbPhIEdGd2nPc2bWbcsxliQ+LEgMZXJ3FPIu0u2MuO7LWzZvZ+YiDB+3i+R8QM7kt6ppXXLYposCxI/FiSmOqWlysJNu5m+ZAtzVmxn/6ESuiVEMX5gRy5M70C7WOuR2DQtFiR+LEjMscg/WMyHy7OYvjiTxT/uIURg2IkJTBjUkRG92xIRZk1fpvGzIPFjQWKO18bsfLdH4q1szztAyxbhnN/fOTcltUOc1+UZEzQWJH4sSExNlZQqX2XkMH3xFj5ZvYOi4lJ6J8YyYaDTI3HrqGZel2hMrao3QSIiY4A/A6HAq6o6yW98BPBPYCCwC7hEVTe74x4ArgNKgFtVda7PfKHAYmCrqv68ujosSExtyi08xKxlW5m+JJPlmbmEhwojerVjwqBkhp2YQJj1SGwagWMJkqCd4ut+2b8InAVkAt+KyCxVXe0z2XXAHlXtLiITgaeBS0QkBZgI9AGSgHkicqKqlrjz3QasAWKDVb8xlYlrEc4VQztzxdDOrNu+j+mLt/D+0q18vGo7baIjuDC9AxMGJtOjnfVIbJqGYP50GgxkqOpGVS0CpgLj/KYZB7zu3p8BjBDneMtxwFRVPaiqm4AMd3mISDJwDvBqEGt3LJ4CuzYE/WlMw9WzfQwP/jyFbx4YwctXDGRAp5a89tUmzvrTAsa9+F/e+N+P5O4/5HWZxgRVMDsd6gBs8XmcCZxc2TSqWiwiuUC8O/x/fvN2cO9PBu4Fgvtzb/8emPcwHNoPQ26CM+6GCPuFaSoWHhrCqD7tGdWnPTn5B3n/+61MX5zJg++v5PHZqxndpz0TBiVzSjfrkdg0PsEMkoo+Lf47ZCqbpsLhIvJzYKeqLhGRM6t8cpEbgBsAOnXqVH21/pq3gpsXwbxH4b+TYdlUOOsxSLsY7CQ1U4U20RFcf3pXrjutCyu35jF9yRb+vTSLWcuySIqL5KKByYwfmMwJ8VFel2pMrQjaznYRGQo8oqqj3ccPAKjqUz7TzHWn+UZEwoDtQAJwv++0ZdMB5wFXAMVAJM4+kvdU9fKqaqnxzvbMxfDRPZD1HXQ8GcY+DUkDjn95psk5cKiEeWt2MH1xJl+ud3okHtylNaNS2pGSFEtKYiwtW9iRX6b+qBdHbbnB8AMwAtgKfAv8n6qu8pnmZqCvqv7K3dl+oapeLCJ9gLdw9oskAZ8CPXx2tuNukdxdZ0dtlZbCsrdg3iNQkAPpV8DPHoLohJot1zQ523MPuOemZLIxp6B8eGJcJCmJsfR2bylJsZzQuoX1UGw8US+CxC3kbJx9GqHAa6r6pIg8BixW1VkiEgn8CxgA7AYmqupGd97fAtfibH3crqpz/JZ9JnUZJGUO5MIXz8DClyA8Cs68Hwb/AkLt8q7m2GXvO8iabXms3pbHGve2IbuAklLnc9miWSg928ccETC92scQZddUMUFWb4KkvgjKeSTZP8DH98OGT6FNT6e5q9vw2n0O0yQdOFTC+h355QFTFjL7DhQDzi66zvFR9E6MoXd7Z8uld2IsiXGR1smkqTUWJH6CdkKiKvzwsRMoezZDr5/D6CehVefafy7TpKkqW/fuZ3VWHmu27SsPmZ92F5ZP07JFOL3bl225xJCSFEv3ttHWN5g5LhYkfoJ+ZvuhA/C/F2HBH6G0GE69FU67A5rZUTkmuPYdOMS67ft8tl72sW57HgcOlQIQFiJ0bxt9RNNY78QY4qMjPK7c1HcWJH7qrIuUvCz4z8OwYhrEdnAOF069yA4XNnWqpFTZlFNQvs+lLGR25B0sn6ZdbMThnfru3y5touwcF1POgsRPnfe19eM3MOde2L4cOp0CZz8D7fvW3fMbU4HdBUVOqGQdDpeMnfkUuzv2I8ND6Nk+lpTEmPKA6ZUYS7Tt2G+SLEj8eNJpY2kJfP8v+PQx5yz5gdfAzx6EFq3rtg5jqnCwuISMnfmH97tk5bFmex57Cw9369KpdQtnn0tinLODPzGW5FbNbcd+I2dB4sfT3n/374HPJ8GiV5wuVn72oBMqofYrz9RPqsr2vAPlWy5lIbNpVwFlXxcxkWHlWy1lTWM92kUTGW479hsLCxI/9aIb+Z1rnOauTQugbR/ncOEup3tbkzHHoLComLXb9x3RPLZ2+z4Ki5zzhENDhG4JUT479Z2QSYixHfsNkQWJn3oRJOAcLrzmA5j7W8j9CVLOh1FPQMuOXldmzHEpLVV+2l14xAmVq7PyyMo9UD5Nm+iI8sORy7ZeuraJsuu21HMWJH7qTZCUObQfvv4LfPmc8/i0O5xDhsObe1uXMbVkb2HREee7rNmWx/od+RSVOIclNwsLoWe7mPJ9LmU79uOaWw8R9YUFiZ96FyRl9m6B//wOVs2EuE4w+gnofZ4dLmwapUMlpWzIzi/f71LWPLaroKh8mg4tm5efqZ/i7uBPbtXc+hvzgAWJn3obJGU2fQlz7oOdq6DLGTDmaWiX4nVVxgSdqpK976BPVzDOVszG7Hzco5KJjgijV3tny6Vn+xi6JkTRLSGatjERduRYEFmQ+Kn3QQJQUgxLpsBnT8DBfXDS9TD8Aee6KMY0MfuLSvhhx74jTqhcu20f+w4Wl08THRFG14QouraJomtCtHs/mi5tomjezI4eqykLEj8NIkjKFO6G+U/C4tcgsiWMeAjSr4QQ+2CYpk1V2ZZ7gI3ZBWzMyWdjdgEbsp2/W/fuP2LaDi2bl2+5lAVM14Qo69jyGFiQ+GlQQVJm+wqnuevH/0L7NBj7DJww1OuqjKmX9heVsCnncMBszM5nY04BG7MLyPfZimkeHkqXNlFOuCRE080Nmy5toqxrfj8WJH4aZJCAc7jwqvfgk99B3lZIHe/03xXXofp5jTHl+2AysssC5nDYZO4pLN8PA9A+NtINmMNbMN0Soklq2bxJ9kFmQeKnwQZJmaIC+Goy/PfPThPX6XfB0FsgPNLryoxpsA4Wl/DjrkI2ZuezwaeZbGN2PnkHDm/FRISFHN6KcQOmbJ9MbGTjPVzZgsRPgw+SMns2wycPOic1tuoMo5+CnmPtcGFjapGqsqugyK+JzAmbn3YXll+9EpyTLbv5NJOVhU1yq+YN/oRLCxI/jSZIymyY71xMK3stdPsZjJkECT29rsqYRq+ouJSfdhceETBOc1kBu33OhwkPFU6IP3xEmW/YtGzRzMNXEDgLEj+NLkgASg7Bt6/C/KfgUAEM/iWceR9ExnldmTFN0p6CIjbmOFsuvlszP+4q4FDJ4e/Z1lHN3IBxm8jaRNGtbTSdWrcgvB5txViQ+GmUQVKmIMfpqv67f0JUGxjxMPS/DELqzz+kMU1ZcUkpmXv2OyGzs+CIsMnJP3yxsbAQoVPrFkcETNm+mPioZtUftlxSDPk7nAvs5W11/pYUwWm3H1fdFiR+GnWQlMn63jlceMtCSEp3DhfueJLXVRljqpC7/5Bz2HJ5E5kTNpt2FVBUXFo+XXwkDIw/SN+YQk5snscJ4Xtox25iD+0kNC/LCY387aClRz5BVFu4Z/1x1WZB4qdJBAk4hwuvmO4cLpy/HfpdCiMfgZj2XldmjKnMoQOwzw0Dd2uiNHcrB3ZtoXjvVsLytxFZtIsQjvyuLtAItmk8e8ISONC8HcQm0ax1R2LbnkC75K60at8ZadH6uA/GsSDx02SCpMzBffDlH+GbFyG0GZxxDwy5EcLsuhDG1KmD+bBv2+GmpvK/PvcLdx09X2QcxHaA2CT3dvh+YWR7NhXFkZErbMgpLN+a2ZRTwP5DJeWLiIkIo1diDNN+OfS4zuY/liCxUzkbo4gYZ0tkwBXOtU/mPezsQxkzCU4c5XV1xjR8qnAwr/JwKLt/IPfoeVvEHw6H5JP8gqIDxCRCRHSlT90C6OPefJWWOle29D0f5mBxaZ10CWNbJE3B+v84hwvvyoAeo2HMUxDfzeuqjKmfVJ1LZFe1FZGXBUX5R88b3e6oLYgj7sckNpjrDlnTlp8mHyQAxUWw6O/w+dNQfACG3uQ0eUXEeF2ZMXWntBQKc6reisjLcj4jviTECYGKwqHsfnR7CGsY54gEwoLEjwWJj3074NNHYembzq+nkY9C2iV2uLBp+EpLjj789aiQ2Aalh46cLyQMYpJ8gsGvqSk2yfmshDatPQEWJH4sSCqQuRjm3AtblzjttGOfgQ7pXldlTOUO5MLONZVvTezbDlpy5DyhEVU3NcV2gKgE+yFVAQsSPxYklSgthWVvw7xHoCAbBlzunNAYneB1ZcY4DuTCujnO5ag3fOacYFcmvMXRWw7+WxM1OPy1qbOjtkxgQkJgwGXQ+1xY8Az872+w+t9w5v0w+AYIbbw9m5p6bP9eJzxWv384PGKT4aRfQNczIS7ZCYrIOAuJesK2SMxh2T/A3AcgYx606ekc3dV9hNdVmabANzwyPnX2Y8QmQ5/zIeV86DDQmp/qmG2RmOOTcCJcNgN+mOscLvzGhdDzHBj9JLTu4nV1prGpLDxO/qWFRwNjQWKOJAI9x0C34c6Z8QuehRdPhlN+DaffCc2ivK7QNGRl4VG2z8PCo1Gwpi1TtbwsZ2f88necQyRHPQ6pF1nbtAnc/r2w7iNY9f7h8IjrCCnjoM8FTnjY/1O9Y0dt+bEgqQU//c85XHjbMug0FMY+DYn9vK7K1FcWHg1evdlHIiJjgD8DocCrqjrJb3wE8E9gILALuERVN7vjHgCuA0qAW1V1rohEAguACLf2Gar6cDBfg3F1GgK/mA/fv+Gc0Pj3YTDwavjZ7yAq3uvqTH1QWXic/EsLj0YuaEEiIqHAi8BZQCbwrYjMUtXVPpNdB+xR1e4iMhF4GrhERFKAiTj9kiUB80TkROAg8DNVzReRcOArEZmjqv8L1uswPkJCYeBVzq/KzyfBopdh1Xsw/EEYdG2TO/PX4BMeM51LQFt4NEnB/OQPBjJUdSOAiEwFxgG+QTIOeMS9PwN4QZyuKscBU1X1ILBJRDKAwar6DVDWU1q4e2v8bXP1TfOWMHaSEypz7oM598CSKU7vwl2HeV2dCbb9e2DtR+55HhYeJrhB0gHY4vM4Ezi5smlUtVhEcoF4d/j//ObtAOVbOkuA7sCLqrqwoicXkRuAGwA6depU09diKtK2N1z5b1g7G+b+Bv55HrTvC0kDnP0niQOgXR8Ij/S6UlNTVYbHhU73OhYeTVYwg6Si/yr/rYfKpql0XlUtAfqLSEtgpoikqurKoyZWfRl4GZyd7cdSuDkGIs6Z8d1HwqJXnLbxNR841z8BkFAncBL7Q1J/52+7PtCshbd1m+pVGB6dYMivIOUCCw9TLphBkgl09HmcDGRVMk2miIQBccDuQOZV1b0i8jkwBjgqSEwdC28Op97q3FQhdwtkLYVtS50jvX74GJa+4UwroZDQ0wmVxH5OwLTva+eo1Adl4bFqJmz83MLDBCSYQfIt0ENEugBbcXae/5/fNLOAq4BvgPHAZ6qqIjILeEtEnsPZ2d4DWCQiCcAhN0SaAyNxdtCb+kQEWnZybinnOcNUnZ5as9xg2bbU6Ypl2VvuPCHQ5kS3Saz/4XCx66UE3/49sPZD52grCw9zHIIWJO4+j1uAuTiH/76mqqtE5DFgsarOAv4B/Mvdmb4bJ2xwp5uGs2O+GLhZVUtEJBF43d1PEgJMU9XZwXoNphaJOJ3txSVD7587w1Sdrr+3LT289bJpgXPyozMTxHc/3CSW2A8S05zO+kzNVBUefS6AJAsPEzg7IdHUP/t2HG4SKwuYvK2Hx7fu5oZLv8MB07yld/U2FEeEx3woLXbCo884Cw9zlHpzQqIxxyWmHcSMhhNHHx6Wn+02iX3vhMuWRbDy3cPjW3U+cod+Yj/nWhRNXeHuw+d5bPz8cHgMucnpWdfCw9QCCxLTMEQnQI+Rzq1MwS53y6Vs6+V75wijMi07HblDP3FA0zgLv6LwaGnhYYLHgsQ0XFHxzvVSfK+ZUrjb3XJZdnjfy5pZh8fHdTxyh35iP4huW/e117bC3U6z1er3LTxMnbMgMY1Li9ZOF/jdhh8etn8vbF9+5OHIa32O0YhJOrJJLKk/xLSv+9qPVZXhcYFzYqiFh6kDFiSm8WveErqc4dzKHMjzCRd362XdHMrPmY1u79Mk5m69xCR6/8VcFh6rZsKmLw6Hx9Cbnet5WHgYD1iQmKYpMhY6n+bcyhzcB9tXHHm0WMZ/QEud8VEJRzaJJfZ3DmcO9he3hYep5yxIjCkTEQMnnOLcyhQVwPaVPue6LHO6gdESZ3yLeL8d+v2dL/mafrEX7naa31a97xMeJ1h4mHrJgsSYqjSLgk4nO7cyRYWwY9XhI8aylsHXzztf9gDNWx29Q79Vl+q/+KsKjz4XOMuz8DD1kAWJMceqWQvoeJJzK3PogF+4LHWueV96yBkfGeeGS1nADHDC5cBeCw/T4FmQGFMbwiMheaBzK1N8EHauPvJosYV/h5IiZ3xELBwq9AmPW5xDdS08TANjQWJMsIRFOFseSQMODysuguw1h/e3RMY6V5y08DANmAWJMXUprNnhJi5jGokQrwswxhjTsFmQGGOMqRELEmOMMTViQWKMMaZGLEiMMcbUiAWJMcaYGrEgMcYYUyMWJMYYY2pEVNXrGoJORLKBH49z9jZATi2WU1usrmNjdR0bq+vYNMa6TlDVhEAmbBJBUhMislhVB3ldhz+r69hYXcfG6jo2Tb0ua9oyxhhTIxYkxhhjasSCpHove11AJayuY2N1HRur69g06bpsH4kxxpgasS0SY4wxNWJBYowxpkYsSFwiMkZE1olIhojcX8H4CBF5xx2/UEQ615O6rhaRbBFZ6t6ur4OaXhORnSKyspLxIiLPuzUvF5H0YNcUYF1nikiuz7p6qI7q6igi80VkjYisEpHbKpimztdZgHXV+ToTkUgRWSQiy9y6Hq1gmjr/PAZYV51/Hn2eO1REvheR2RWMC+76UtUmfwNCgQ1AV6AZsAxI8ZvmJuAl9/5E4J16UtfVwAt1vL7OANKBlZWMPxuYAwgwBFhYT+o6E5jtwf9XIpDu3o8BfqjgfazzdRZgXXW+ztx1EO3eDwcWAkP8pvHi8xhIXXX+efR57juBtyp6v4K9vmyLxDEYyFDVjapaBEwFxvlNMw543b0/AxghEvSLbAdSV51T1QXA7iomGQf8Ux3/A1qKSGI9qMsTqrpNVb9z7+8D1gAd/Car83UWYF11zl0H+e7DcPfmf1RQnX8eA6zLEyKSDJwDvFrJJEFdXxYkjg7AFp/HmRz9gSqfRlWLgVwgvh7UBXCR2xwyQ0Q6BrmmQARatxeGuk0Tc0SkT10/udukMADn16wvT9dZFXWBB+vMbaZZCuwE/qOqla6vOvw8BlIXePN5nAzcC5RWMj6o68uCxFFRMvv/0ghkmtoWyHN+AHRW1TRgHod/dXjJi3UViO9w+g/qB/wFeL8un1xEooF3gdtVNc9/dAWz1Mk6q6YuT9aZqpaoan8gGRgsIql+k3iyvgKoq84/jyLyc2Cnqi6parIKhtXa+rIgcWQCvr8ckoGsyqYRkTAgjuA3o1Rbl6ruUtWD7sNXgIFBrikQgazPOqeqeWVNE6r6ERAuIm3q4rlFJBzny/pNVX2vgkk8WWfV1eXlOnOfcy/wOTDGb5QXn8dq6/Lo83gqcJ6IbMZp/v6ZiLzhN01Q15cFieNboIeIdBGRZjg7o2b5TTMLuMq9Px74TN09V17W5deOfh5OO7fXZgFXukciDQFyVXWb10WJSPuydmERGYzz/7+rDp5XgH8Aa1T1uUomq/N1FkhdXqwzEUkQkZbu/ebASGCt32R1/nkMpC4vPo+q+oCqJqtqZ5zviM9U9XK/yYK6vsJqa0ENmaoWi8gtwFycI6VeU9VVIvIYsFhVZ+F84P4lIhk4ST6xntR1q4icBxS7dV0d7LpE5G2co3naiEgm8DDOjkdU9SXgI5yjkDKAQuCaYNcUYF3jgRtFpBjYD0ysgx8D4PxivAJY4bavA/wG6ORTmxfrLJC6vFhnicDrIhKKE1zTVHW215/HAOuq889jZepyfVkXKcYYY2rEmraMMcbUiAWJMcaYGrEgMcYYUyMWJMYYY2rEgsQYY0yNWJAYUwtEpMSnx9elUkFPzTVYdmeppEdjY+oDO4/EmNqx3+06w5gmx7ZIjAkiEdksIk+717FYJCLd3eEniMinbud+n4pIJ3d4OxGZ6XaSuExETnEXFSoir4hzHYxP3DOrjakXLEiMqR3N/Zq2LvEZl6eqg4EXcHppxb3/T7dzvzeB593hzwNfuJ0kpgOr3OE9gBdVtQ+wF7goyK/HmIDZme3G1AIRyVfV6AqGbwZ+pqob3Q4St6tqvIjkAImqesgdvk1V24hINpDs0/FfWRfv/1HVHu7j+4BwVX0i+K/MmOrZFokxwaeV3K9smooc9Llfgu3fNPWIBYkxwXeJz99v3Ptfc7jjvMuAr9z7nwI3QvlFlGLrqkhjjpf9qjGmdjT36UEX4GNVLTsEOEJEFuL8cLvUHXYr8JqI3ANkc7i339uAl0XkOpwtjxsBz7vgN6Yqto/EmCBy95EMUtUcr2sxJlisacsYY0yN2BaJMcaYGrEtEmOMMTViQWKMMaZGLEiMMcbUiAWJMcaYGrEgMcYYUyP/H5l7Cxm91pszAAAAAElFTkSuQmCC
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Load-Model-State">Load Model State<a class="anchor-link" href="#Load-Model-State">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[10]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">model</span><span class="o">.</span><span class="n">load_state_dict</span><span class="p">(</span><span class="n">torch</span><span class="o">.</span><span class="n">load</span><span class="p">(</span><span class="s1">&#39;model.pt&#39;</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[10]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>IncompatibleKeys(missing_keys=[], unexpected_keys=[])</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Test">Test<a class="anchor-link" href="#Test">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[11]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># track test loss</span>
<span class="n">test_loss</span> <span class="o">=</span> <span class="mf">0.0</span>
<span class="n">class_correct</span> <span class="o">=</span> <span class="nb">list</span><span class="p">(</span><span class="mf">0.</span> <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="mi">10</span><span class="p">))</span>
<span class="n">class_total</span> <span class="o">=</span> <span class="nb">list</span><span class="p">(</span><span class="mf">0.</span> <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="mi">10</span><span class="p">))</span>
<span class="n">classes</span> <span class="o">=</span> <span class="p">[</span><span class="s2">&quot;1&quot;</span><span class="p">,</span><span class="s2">&quot;2&quot;</span><span class="p">,</span><span class="s2">&quot;3&quot;</span><span class="p">,</span><span class="s2">&quot;4&quot;</span><span class="p">,</span><span class="s2">&quot;5&quot;</span><span class="p">,</span><span class="s2">&quot;6&quot;</span><span class="p">,</span><span class="s2">&quot;7&quot;</span><span class="p">,</span><span class="s2">&quot;8&quot;</span><span class="p">,</span><span class="s2">&quot;9&quot;</span><span class="p">,</span><span class="s2">&quot;0&quot;</span><span class="p">]</span>
<span class="n">model</span><span class="o">.</span><span class="n">eval</span><span class="p">()</span>
<span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
  <span class="c1"># iterate over test data</span>
  <span class="k">for</span> <span class="n">data</span><span class="p">,</span> <span class="n">target</span> <span class="ow">in</span> <span class="n">test_loader</span><span class="p">:</span>
      <span class="c1"># move tensors to GPU if CUDA is available</span>
      <span class="k">if</span> <span class="n">train_on_gpu</span><span class="p">:</span>
          <span class="n">data</span><span class="p">,</span> <span class="n">target</span> <span class="o">=</span> <span class="n">data</span><span class="o">.</span><span class="n">cuda</span><span class="p">(),</span> <span class="n">target</span><span class="o">.</span><span class="n">cuda</span><span class="p">()</span>
      <span class="c1"># forward pass: compute predicted outputs by passing inputs to the model</span>
      <span class="n">output</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">data</span><span class="p">)</span>
      <span class="c1"># calculate the batch loss</span>
      <span class="n">loss</span> <span class="o">=</span> <span class="n">criterion</span><span class="p">(</span><span class="n">output</span><span class="p">,</span> <span class="n">target</span><span class="p">)</span>
      <span class="c1"># update test loss </span>
      <span class="n">test_loss</span> <span class="o">+=</span> <span class="n">loss</span><span class="o">.</span><span class="n">item</span><span class="p">()</span><span class="o">*</span><span class="n">data</span><span class="o">.</span><span class="n">size</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
      
      
      <span class="n">ps</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">exp</span><span class="p">(</span><span class="n">output</span><span class="p">)</span> <span class="c1"># logSoftMax Ps -&gt; Ps</span>
      
      <span class="c1"># convert output probabilities to predicted class</span>
      <span class="n">_</span><span class="p">,</span> <span class="n">pred</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">max</span><span class="p">(</span><span class="n">ps</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>    
      <span class="c1"># compare predictions to true label</span>
      <span class="n">correct_tensor</span> <span class="o">=</span> <span class="n">pred</span><span class="o">.</span><span class="n">eq</span><span class="p">(</span><span class="n">target</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">view_as</span><span class="p">(</span><span class="n">pred</span><span class="p">))</span>
      <span class="n">correct</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">squeeze</span><span class="p">(</span><span class="n">correct_tensor</span><span class="o">.</span><span class="n">numpy</span><span class="p">())</span> <span class="k">if</span> <span class="ow">not</span> <span class="n">train_on_gpu</span> <span class="k">else</span> <span class="n">np</span><span class="o">.</span><span class="n">squeeze</span><span class="p">(</span><span class="n">correct_tensor</span><span class="o">.</span><span class="n">cpu</span><span class="p">()</span><span class="o">.</span><span class="n">numpy</span><span class="p">())</span>
      <span class="c1"># calculate test accuracy for each object class</span>
      <span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="n">batch_size</span><span class="p">):</span>
          <span class="n">label</span> <span class="o">=</span> <span class="n">target</span><span class="o">.</span><span class="n">data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span>
          <span class="n">class_correct</span><span class="p">[</span><span class="n">label</span><span class="p">]</span> <span class="o">+=</span> <span class="n">correct</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">.</span><span class="n">item</span><span class="p">()</span>
          <span class="n">class_total</span><span class="p">[</span><span class="n">label</span><span class="p">]</span> <span class="o">+=</span> <span class="mi">1</span>

<span class="c1"># average test loss</span>
<span class="n">test_loss</span> <span class="o">=</span> <span class="n">test_loss</span><span class="o">/</span><span class="nb">len</span><span class="p">(</span><span class="n">test_loader</span><span class="o">.</span><span class="n">dataset</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Test Loss: </span><span class="si">{:.6f}</span><span class="se">\n</span><span class="s1">&#39;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="n">test_loss</span><span class="p">))</span>

<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="nb">range</span><span class="p">(</span><span class="mi">10</span><span class="p">):</span>
    <span class="k">if</span> <span class="n">class_total</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Test Accuracy of </span><span class="si">%5s</span><span class="s1">: </span><span class="si">%2d%%</span><span class="s1"> (</span><span class="si">%2d</span><span class="s1">/</span><span class="si">%2d</span><span class="s1">)&#39;</span> <span class="o">%</span> <span class="p">(</span>
            <span class="n">classes</span><span class="p">[</span><span class="n">i</span><span class="p">],</span> <span class="mi">100</span> <span class="o">*</span> <span class="n">class_correct</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">/</span> <span class="n">class_total</span><span class="p">[</span><span class="n">i</span><span class="p">],</span>
            <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">class_correct</span><span class="p">[</span><span class="n">i</span><span class="p">]),</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">class_total</span><span class="p">[</span><span class="n">i</span><span class="p">])))</span>
    <span class="k">else</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Test Accuracy of </span><span class="si">%5s</span><span class="s1">: N/A (no training examples)&#39;</span> <span class="o">%</span> <span class="p">(</span><span class="n">classes</span><span class="p">[</span><span class="n">i</span><span class="p">]))</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;</span><span class="se">\n</span><span class="s1">Test Accuracy (Overall): </span><span class="si">%2d%%</span><span class="s1"> (</span><span class="si">%2d</span><span class="s1">/</span><span class="si">%2d</span><span class="s1">)&#39;</span> <span class="o">%</span> <span class="p">(</span>
    <span class="mf">100.</span> <span class="o">*</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">class_correct</span><span class="p">)</span> <span class="o">/</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">class_total</span><span class="p">),</span>
    <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">class_correct</span><span class="p">),</span> <span class="n">np</span><span class="o">.</span><span class="n">sum</span><span class="p">(</span><span class="n">class_total</span><span class="p">)))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Test Loss: 0.041858

Test Accuracy of     1: 99% (974/980)
Test Accuracy of     2: 99% (1129/1135)
Test Accuracy of     3: 97% (1006/1032)
Test Accuracy of     4: 99% (1003/1010)
Test Accuracy of     5: 98% (970/982)
Test Accuracy of     6: 98% (877/892)
Test Accuracy of     7: 98% (945/958)
Test Accuracy of     8: 97% (1004/1028)
Test Accuracy of     9: 98% (962/974)
Test Accuracy of     0: 97% (984/1009)

Test Accuracy (Overall): 98% (9854/10000)
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Check-Test-Result">Check Test Result<a class="anchor-link" href="#Check-Test-Result">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[12]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># obtain one batch of test images</span>
<span class="n">dataiter</span> <span class="o">=</span> <span class="nb">iter</span><span class="p">(</span><span class="n">test_loader</span><span class="p">)</span>
<span class="n">images</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">dataiter</span><span class="o">.</span><span class="n">next</span><span class="p">()</span>

<span class="c1"># get sample outputs</span>
<span class="n">output</span> <span class="o">=</span> <span class="n">model</span><span class="p">(</span><span class="n">images</span><span class="p">)</span>
<span class="c1"># convert output probabilities to predicted class</span>
<span class="n">_</span><span class="p">,</span> <span class="n">preds</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">max</span><span class="p">(</span><span class="n">output</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="c1"># prep images for display</span>
<span class="n">images</span> <span class="o">=</span> <span class="n">images</span><span class="o">.</span><span class="n">numpy</span><span class="p">()</span>

<span class="c1"># plot the images in the batch, along with predicted and true labels</span>
<span class="n">fig</span> <span class="o">=</span> <span class="n">plt</span><span class="o">.</span><span class="n">figure</span><span class="p">(</span><span class="n">figsize</span><span class="o">=</span><span class="p">(</span><span class="mi">25</span><span class="p">,</span> <span class="mi">4</span><span class="p">))</span>
<span class="k">for</span> <span class="n">idx</span> <span class="ow">in</span> <span class="n">np</span><span class="o">.</span><span class="n">arange</span><span class="p">(</span><span class="mi">20</span><span class="p">):</span>
    <span class="n">ax</span> <span class="o">=</span> <span class="n">fig</span><span class="o">.</span><span class="n">add_subplot</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">20</span><span class="o">/</span><span class="mi">2</span><span class="p">,</span> <span class="n">idx</span><span class="o">+</span><span class="mi">1</span><span class="p">,</span> <span class="n">xticks</span><span class="o">=</span><span class="p">[],</span> <span class="n">yticks</span><span class="o">=</span><span class="p">[])</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">imshow</span><span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">squeeze</span><span class="p">(</span><span class="n">images</span><span class="p">[</span><span class="n">idx</span><span class="p">]),</span> <span class="n">cmap</span><span class="o">=</span><span class="s1">&#39;gray&#39;</span><span class="p">)</span>
    <span class="n">ax</span><span class="o">.</span><span class="n">set_title</span><span class="p">(</span><span class="s2">&quot;</span><span class="si">{}</span><span class="s2"> (</span><span class="si">{}</span><span class="s2">)&quot;</span><span class="o">.</span><span class="n">format</span><span class="p">(</span><span class="nb">str</span><span class="p">(</span><span class="n">preds</span><span class="p">[</span><span class="n">idx</span><span class="p">]</span><span class="o">.</span><span class="n">item</span><span class="p">()),</span> <span class="nb">str</span><span class="p">(</span><span class="n">labels</span><span class="p">[</span><span class="n">idx</span><span class="p">]</span><span class="o">.</span><span class="n">item</span><span class="p">())),</span>
                 <span class="n">color</span><span class="o">=</span><span class="p">(</span><span class="s2">&quot;green&quot;</span> <span class="k">if</span> <span class="n">preds</span><span class="p">[</span><span class="n">idx</span><span class="p">]</span><span class="o">==</span><span class="n">labels</span><span class="p">[</span><span class="n">idx</span><span class="p">]</span> <span class="k">else</span> <span class="s2">&quot;red&quot;</span><span class="p">))</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAABXUAAAD7CAYAAAAl6XdWAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADl0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uIDMuMC4zLCBodHRwOi8vbWF0cGxvdGxpYi5vcmcvnQurowAAIABJREFUeJzs3Xn8VdP+x/H3bqCoNCgKhbohY8p4pYFriIhCZLjm+XYNEcXpVHJN4Uck1zxkSJEprqFI5igaRG4lQimlSdP+/XFq3bVWZ5/O9/Q95/vd5/t6Ph4e97O+n73OXt1Wa++zv3t/dhCGoQAAAAAAAAAA8VCprAcAAAAAAAAAAMgeF3UBAAAAAAAAIEa4qAsAAAAAAAAAMcJFXQAAAAAAAACIES7qAgAAAAAAAECMcFEXAAAAAAAAAGKkQl3UDZJB/SAZfBMkg2pZbLtNkAymBslg80KMDeUX8wa5YN4gF0EyaBEkg8+y3Pa4IBk8k+8xofxj3qCkOEYhF6w1yAXrDXLBeoNcVMT1pkpZD2BTBMlgifej6pLuCxPh5RFdekl6JEyEK9b1nyypiZWvJun1MBF2ChPhL0EyeFfSBZLuKeWho4ys+wd7n6TDJdWV9J2k68NE+HqGbv68uV3S8ZK2lfSjpIFhInxckpg3xStIBpdJ+rukPSUNCxPh3zfSxZ83J0v6p6R9JH0SJsJ26zdk3hSvIBnUlfSQpCMkzZd0XZgIn87Qpb+k27PpHybCUUEyGBgkg73CRDgpX38GlJ0gGfxF0leShoeJ8PQMmzrzJlN/5k1x4hiFTcFag5IIksFukgZLaiVpnqSeYSIcmaGLv95sp9T3sTaSlkkaECbCIRLrTTELksEYSQdKWr3uRz+GiXCXDF38c+LI/qw3xYv1ZuNifadumAhrrP9P0jaSlkt6Pt226y7mnSXpSav/7lb/mpJme/2fknRhvsaPMlFF0g+S2kraStINkp4LksGO6TZON28kLZXUaV3/syTdHSSDg60886Y4/SRpgKSHN7ZhxLxZIOkuSf+K6Ma8KU6DJa1U6hjVXdL9QTLYPd2GQTJoKKm9pBdL0H+YUiciKE6DJX2aaYOIebOx/syb4sMxCpuCtQZZCZJBFUkvSXpFqRtkLpD0ZJAMmkdsn269eVLSf5U6tzlG0sAgGbS38qw3xesy6xpO5AXdDOtNpv6sN0WG9SY7sb6o6+kq6VdJ70fkD5D0e5gI50TkD5XUQNIL1s8+lrRzkAyapO+CuAkT4dIwEfYNE+HMMBGuDRPhK0r9I28V0WWDeRMmwkSYCKet6/+xUnPuIKsP86YIhYlwRJgIX5T0Wxabp5s3b4WJ8Dmlvninw7wpMkEy2FJSF0k3hIlwSZgIx0kaJemMiC5/kzTB+s1yNv3HKHWCgiITJINukn6X9PZGNnXmTZb9x4h5U1Q4RiFXrDUooV0lNZJ0Z5gI14SJ8B1JHyj63MZZb4JkUENSO0k3hYlwVZgIJ0oaLukcqw/rDdKuNxsxRqw3xYb1JgvFdFH3LEmPh4kwjMjvKembjfQfHibCpet/ECbC1Uo9nr93qY0S5UqQDLaR1FzS5IhNMs6bIBlUl7Sf3Z95A218vdkA86YoNZe0JkyE062fTZSU9k5dbThvsuk/VdKOQTKoVQrjRTmx7u+zn6Srsth8g/Umi/7Mm4qNYxQksdYgJ0HEz/aI2N6fN4H3vxv0Z70pajcHyWB+kAw+CJJBuwzbRR2nMvVnvSk+rDdZKIqLukEyaKzU4/SPZdistqQ/IvpvodSdvo+mSf+xri+KTJAMqip1u/1jYSKcFrFZ5LxZZ4hSF1ne8H7OvKnYNjZvojBviksNSYu8ny1SqtxPOv68yab/+u2ZN8Wlv6SHwkT4QxbbpltvNtafeVOxcYzCeqw1KKlpSj0d2zNIBlWDZHCEUt/Dt4jY3pk3YSL8Q6k77W4IkkG1IBnsq9RTSX5/1pvic62knSVtJ2mopJeDZNA0Ytt0683G+rPeFB/WmyzE+kVpljMljQsT4X8zbLNQ0V+kT1SqltjYNLmaSj1ShCISJINKkp5QqlblZRk2jZw3QTK4Tanf8rRPc4c486Ziy7TeZMK8KS5LJPl3C9RS9MUUf95k03/99sybIhEkg32Ueplnyyy7OPMmy/7Mm4qNYxRYa5CTMBGuCpJBZ6VeKnStpM8kPSfpz4gu6dab7krVYf5B0vdK3WTTwtuG9abIrCtbuN5jQTI4VVJHpX9B1QbzJov+rDdFhvUmO8V0UTfqxQ7rTZJ0RUQubemGdYWZmyl1JyaKRJAMAqXeJr+NpI5hIlyVYfO08yZIBklJR0tqGybCxV6OeYNM601azJuiNF1SlSAZ/CVMhN+u+9neii73Mkmp41FJ+u8maaa/DiHW2knaUdLsIBlIqTu2KwfJoEWYCPdNs70/b7Lpz7yp2DhGQWKtQY7CRDhJqbvlJElBMhiv6CdmN1hvwkQ4S9KxVv+nJX1itVlvKoZQ6R+vlzZcb7Lpz3pThFhvNi72F3WDZHCwUrfgP7+RTT+RVDtIBtuFifBHq//2Sr1Z8aI0ffZXamGYVVrjRblwv1KL/uFhIly+kW03mDdBMrhO0mmSDg0TYboXkjBvitC6Bb+KpMpKfWmpJmn1ujo8vnTzprKkqus+o9K6/musXyowb4pMmAiXBslghKR+QTI4T9I+ko6XdHBEl/9IujtIBtXCRLgiy/5tJb2evz8FysBQSc9Y7auVunByccT2zrzJsj/zpshwjEIOWGuQkyAZ7KXUL54rSbpEUkOlL2MopV9vdpM0R6m77U6WdIRS383WY70pMkEyqK3US6zGSlot6RSlXlT/z4guznqTZX/WmyLEerNxxVBT9yxJI9bVy4gUJsKVSv3ln+6lzpD0YZgIZ6Tp1l2pmqkoEuveanihUhdHfg6SwZJ1/3VPt33EvBkoqbGkb63+11t55k1x6iNpuaReSs2H5et+toGIeXPGuj73S2qzLn7QyjNvitMlkqorVQ9qmKSLw0SY9k7dMBH+IukdpS7cZtv/VEkP5GHcKCNhIlwWJsKf1/+nVBmOFWEinBexvTNvsuzPvCk+HKNQIqw12ARnSJqr1LnJYZL+FibCtI9DR6w3Ryr1GPRCpW6sOsqbN6w3xaeqpAGS5kmaL+lySZ3DRJj2pZ1pzomz6c96U5xYbzYiCDcoBVq8gmRQX9L7klpu7A7NIBk0UOo3QS3X/TYaFRTzBrlg3iAXQTJoodQjRfunqdXtb9tJ0hlhIjy5IINDucW8QUlxjEIuWGuQC9Yb5IL1BrmoiOtNhbqoCwAAAAAAAABxVwzlFwAAAAAAAACgwuCiLgAAAAAAAADECBd1AQAAAAAAACBGuKgLAAAAAAAAADFSpSQbB0HAW9XKj/lhGNYv60Fkg3lTfoRhGJT1GLLBnClXWGuQC+YNcsG8QS6YN8gF8wa5YN6gxPgOjhxkvdZwp258zSrrAQCoEFhrkAvmDXLBvEEumDfIBfMGuWDeACiErNcaLuoCAAAAAAAAQIxwURcAAAAAAAAAYoSLugAAAAAAAAAQI1zUBQAAAAAAAIAY4aIuAAAAAAAAAMQIF3UBAAAAAAAAIEa4qAsAAAAAAAAAMcJFXQAAAAAAAACIES7qAgAAAAAAAECMVCnrAQCFdPXVVzvt6tWrm3ivvfZycl27do38nPvvv99pf/jhhyZ+4oknNmWIAAAAAAAAQEbcqQsAAAAAAAAAMcJFXQAAAAAAAACIEcovoOg9++yzJs5UUsG3du3ayNyFF17otA8//HATjx071snNnj07632i4mjevLmJp02b5uR69Ohh4nvuuadgY0JhbLnllk77tttuM7G/tnz++edO+6STTjLxrFmz8jA6AAAAIF7q1KnjtBs3bpxVP/98+oorrjDx119/7eSmT59u4okTJ5Z0iEBecKcuAAAAAAAAAMQIF3UBAAAAAAAAIEa4qAsAAAAAAAAAMUJNXRQdu4aulH0dXb+u6RtvvGHinXfe2cl16tTJaTdt2tTE3bt3d3I333xzVvtHxdKyZUsT+/Wb58yZU+jhoIAaNmzotM8//3wT+3OhVatWTvvYY4818eDBg/MwOpSlfffd12mPGDHCxDvuuGPe93/EEUc47alTp5r4hx9+yPv+Ub7Y5zqjRo1ycpdddpmJhwwZ4uTWrFmT34EhZw0aNDDxc8895+TGjx9v4qFDhzq5mTNn5nVcvq222sppH3rooSYePXq0k1u1alVBxgSg7B1zzDFO+7jjjjNxu3btnFyzZs2y+ky7Tq4kNWnSxMSbb755ZL/KlStn9flAvnGnLgAAAAAAAADECBd1AQAAAAAAACBGKL+AotC6dWsTn3DCCZHbTZ482Wnbj2zMnz/fyS1ZssTEm222mZP76KOPnPbee+9t4nr16mUxYlR0++yzj4mXLl3q5EaOHFno4SDP6tevb+LHHnusDEeC8uzII4902pke+8sHv7TQOeecY+Ju3boVdCwoPP/85b777ovc9t577zXxww8/7OSWL19eugNDzurUqeO07fNgv8TBL7/8YuJCl1uQ3PF8/vnnTs4+hvplib777rv8DgwZ1apVy8R+ybk99tjDxIcffriTo2wG1rPLGErSpZdeamK7RJkkVa9e3WkHQbDJ+2/evPkmfwZQlrhTFwAAAAAAAABihIu6AAAAAAAAABAjXNQFAAAAAAAAgBgp85q6Xbt2ddp23ZSffvrJya1YscLETz31lJP7+eefTUxtpYqnYcOGJvZr69j1w/x6hXPnzs3q86+66iqn3aJFi8htX3311aw+ExWLXVdMki677DITP/HEE4UeDvLsH//4h9Pu3Lmziffff/+cP/fQQw81caVK7u9lJ06caOL33nsv532gsKpU+d+pWMeOHctwJBvWsbzyyitNvOWWWzo5vxY44s9eXyRp++23j9x22LBhJrbPz1H2tt56axM/++yzTq5u3bom9msmX3755fkd2Eb06dPHxDvttJOTu/DCC03M97yy1b17d6d90003mXiHHXaI7GfX3pWk3377rXQHhtjyjzU9evTI+z6nTZtmYv+dO4ifZs2amdg+Bkobvm+pXbt2Jl67dq2TGzJkiIk/+OADJ1eejz3cqQsAAAAAAAAAMcJFXQAAAAAAAACIkTIvv3Drrbc67R133DGrfvZjOJL0xx9/mLgsbqGfM2eOif0/02effVbo4VQ4L7/8sont2+8ld24sWLAgp8/v1q2b065atWpOn4OKa9ddd3Xa9qPM/uORiL8777zTafuP9+TqxBNPTBtL0qxZs0x8yimnODn/sXqUH+3btzfxQQcd5OT884l8q1OnjtO2Sw1tscUWTo7yC/G3+eabO+3evXtn3dcuGxSGYamNCZtu3333NbH9mKmvX79+BRhNtN13391p26XORo4c6eQ4Typb9uPxd911l5OrV6+eiTOtBffcc4/TtsuQSbl/R0P54T/2bpdR8B9lHz16tIn//PNPJ7do0SIT++cafimoN99808Rff/21k/v4449N/MUXXzi55cuXR+4D5ZNdytBfP+zvRP48LIkDDjjAxKtXr3Zy33zzjYnHjRvn5Oy5vnLlypz3nyvu1AUAAAAAAACAGOGiLgAAAAAAAADECBd1AQAAAAAAACBGyrym7vnnn++099prLxNPnTrVye22224mtutFSW7NqAMPPNDJ/fDDDybeYYcdsh6bX0dj3rx5Jm7YsGFkv9mzZzttauoWll1XclP07NnTxM2bN8+4rV2zx46B9a655hqnbc9T1oji8Nprr5m4UqXS+Z3pb7/95rSXLFli4iZNmji5nXbaycSffPKJk6tcuXKpjAebzq4JJknDhg0z8YwZM5zcwIEDCzKm9Y4//viC7g9la88993TarVq1itzWPyd+/fXX8zImlFyDBg2cdpcuXSK3Pffcc01sf68pFLuO7ltvvRW5nV9T134/Bgrv6quvNnHdunVz+gy/1v9RRx3ltG+66SYT+/V3y6JGJbJj17i169tK0t57723iE044IfIzPvroI6dtX+eZOXOmk2vcuLHTtt9rVFrvr0DZsa8FXnrppU7OXkNq1aoV+Rk//vij037//fed9n//+18T+9/P7XeQ7L///k7OXvs6duzo5CZOnGjiIUOGRI4tX7hTFwAAAAAAAABihIu6AAAAAAAAABAjZV5+4e23387Yto0ePToyV6dOHRPvs88+Ts6+jXq//fbLemwrVqxw2tOnTzexXxrCvh3bf3wS8XDsscc67X79+pl4s802c3K//vqr077uuutMvGzZsjyMDnGz4447Ou3WrVs7bXs9Wbp0aSGGhFLWtm1bp73LLruY2H8ELNtHwvxHdvxH2RYtWmTiDh06OLnevXtHfu7FF19s4vvvvz+rsSA/+vTp47TtRxf9x1Htchv5Yp+/+HOaRxmLW6bH9H3+WoTy44477nDap59+uont70CS9PzzzxdkTFHatGlj4m222cbJPfrooyZ+8sknCzUkpOGXdzr77LMjt500aZKJf/nlFyd3+OGHR/bbaqutnLZd4uGpp55ycj///HP0YFFQ/nfip59+2sR2uQXJLSGVqdyKzy+5YPPLXCLeHnjgAadtl+nYeuutI/v51wy/+uorE19//fVOzr+mZzv44IOdtv196eGHH3Zy9jVGf60bPHiwiV944QUnV4hSR9ypCwAAAAAAAAAxwkVdAAAAAAAAAIgRLuoCAAAAAAAAQIyUeU3d0rJw4UITv/vuu5HbZarZuzF27TG7hq/k1vF49tlnc94Hyo5f89SvGWTz/47Hjh2blzEhvvzalL5C1NdB6bNrJT/zzDNOLlPtJ9usWbOctl17KZlMOrlMNbr9z7ngggtMXL9+fSd36623mrhatWpO7t577zXxqlWrIveH3HXt2tXEHTt2dHLfffediT/77LOCjWk9uxazX0N3zJgxJv79998LNSQUyKGHHpoxv3LlShNnqtmNshWGodO2/x3/9NNPTs7+O82X6tWrm9ivbXjJJZeY2B/3Oeeck9+BIWv++2lq1qxp4vfff9/J2ee7/vnFqaeeamJ/LjRt2tRpb7vttiZ+6aWXnNzRRx9t4gULFmQcO0pfjRo1TGy/R0Zy30kzf/58J3f77bebmHfOVFz+unDNNdeY+LzzznNyQRCY2P+ubL8T5LbbbnNyub6fpl69ek67cuXKJu7bt6+Ts9/v5dcdL2vcqQsAAAAAAAAAMcJFXQAAAAAAAACIkaIpv5APDRo0cNr33XefiStVcq+H9+vXz8Q8FhIfL774oomPOOKIyO0ef/xxp92nT5+8jQnFYc8998yYtx+HR3xUqfK/w2a25RYkt0RLt27dnJz/uFq2/PILN998s4kHDRrk5LbYYgsT+3Nv1KhRJp4xY0ZOY0FmJ510kontvwvJPbcoBLuEiCR1797dxGvWrHFyAwYMMDGlOYrDwQcfnDZOx36c8csvv8zbmJA/xxxzjNN+8803TeyXVLEfbS0Jv9xUu3btTHzggQdG9hs+fHhO+0P+bb755k7bLpVx5513RvZbsWKF037kkUdMbB8HJWnnnXeO/Bz/Uf1ClA1BtM6dO5u4V69eTm727NkmbtOmjZNbtGhRfgeGWLCPCZLUs2dPE9vlFiTpxx9/NLFd+lSSPvnkk5z2b5dUkKQddtjBxP41ntdee83EfrlVmz/uJ554wsRlUa6MO3UBAAAAAAAAIEa4qAsAAAAAAAAAMcJFXQAAAAAAAACIEWrqZnDppZc67fr165t44cKFTu6bb74pyJiwaRo2bOi07Xpyfv0ou86lXVdQkpYsWZKH0SHu7NpxZ599tpP74osvnPZ//vOfgowJZeOzzz5z2uecc46Jc62huzF2bVy7Tqok7bfffnnZJ9LbaqutnHamupK51rHM1QUXXOC07drQU6dOdXLvvvtuQcaEwinJWlDouYnc3H333U67ffv2Jm7UqJGTO/TQQ03s1wQ87rjjctq//zl2/VXf999/b+Lrr78+p/0h/0499dTInF+n2X4/SSatW7fOev8fffSR0+Z7V9nKVH/d/n4zZ86cQgwHMePXtPXf32BbvXq1iQ844AAn17VrVxPvuuuukZ+xfPlyp73bbrtFtv3vZNtss03k59p++eUXp13W76DgTl0AAAAAAAAAiBEu6gIAAAAAAABAjFB+wfPXv/7VxL169YrcrnPnzk7766+/ztuYUHpeeOEFp12vXr3IbZ988kkTz5gxI29jQvE4/PDDTVy3bl0nN3r0aKe9YsWKgowJ+VOpUvTvRf1HhgrBfgTWH1umsfbt29fEZ5xxRqmPqyLyy/lst912Jh42bFihh+No2rRpZI5zmeKX6RHo33//3WlTfiEePv/8c6e91157mXifffZxckcddZSJe/bs6eTmzZtn4sceeyzr/T/xxBNOe+LEiZHbjh8/3sScW5df/nHKLs3hl3CxH4Pec889ndwJJ5xg4jp16jg5f72x8+eff76Ts+fYlClTMo4dpc9+7N1nrymJRMLJvfTSSyb+8ssvS39giIV33nnHadulvezvzpLUuHFjE//f//2fk8tU2scu6eCXe8gkU7mFtWvXOu2RI0ea+B//+IeTmzt3btb7zAfu1AUAAAAAAACAGOGiLgAAAAAAAADECBd1AQAAAAAAACBGqKnr6dixo4mrVq3q5N5++20Tf/jhhwUbEzaNXQdq3333jdxuzJgxTtuvCwRszN57721iv+7P8OHDCz0c5MFFF11kYr/WUlnr1KmTiVu2bOnk7LH647Zr6qJ0/PHHH07briVn17uU3PrbCxYsyMt4GjRoYOJMtfHGjRuXl/2j7BxyyCFO+7TTTovcdtGiRU57zpw5eRkT8mvhwoUmtmsX+u1rr722VPa38847O227vrtfR/Pqq68ulX0iv9566y2nba8Nft1cu8ZtppqX/mdeeumlTvuVV14x8V/+8hcnZ9evtM/DUBj169c3sX8Oab9D4MYbb3Ryffr0MfGQIUOc3EcffWRiu46qJH333Xcmnjx5csax7b777ib2r89wDCsfli9f7rTtWtu1a9d2cvY7rex3XUnSb7/9ZuLZs2c7OXse2t/HJWn//fcv4YhThg4d6rSvv/56E/s1wcsad+oCAAAAAAAAQIxwURcAAAAAAAAAYoSLugAAAAAAAAAQIxW+pm716tWd9lFHHWXilStXOjm7xuqqVavyOzDkrF69ek7brn/i10m2+XW/lixZUroDQ9HZdtttnXabNm1M/M033zi5kSNHFmRMyC+7bm1ZsOuatWjRwsnZa10m8+bNc9ocz0qfXz9sxowZJu7SpYuTe/XVV008aNCgnPa3xx57OG2/xuWOO+5o4kw1D8tbnWhsOv+cqFKl6Ps5/vOf/+R7OChCfh1Ne43x6/b6xx+UT35995NPPtnE/jsittpqq8jPueeee0zsz4UVK1Y47REjRpjYrqspSUceeaSJmzZt6uTs4yvy4/bbbzfxlVdemXU/+3hzySWXODm/XRr89cV+X063bt1KfX/YdH5tWv/ffi4ef/xxp52ppq7/Dgx7fj/66KNObs2aNZs8tnzhTl0AAAAAAAAAiBEu6gIAAAAAAABAjFT48gs9e/Z02i1btjTx6NGjndz48eMLMiZsmquuuspp77fffpHbvvjiiya2y2sA2fj73//utBs0aGDi119/vcCjQUXQu3dvE1966aVZ95s5c6aJzzrrLCc3e/bsTR4XMrOPL0EQOLljjjnGxMOGDcvp8+fPn++0/RILW2+9dVaf4z9qhvjr2rVrZM5/7PGBBx7I93BQBE466SSnfeaZZzpt+3HW3377rSBjQn699dZbJvbXlNNOO83E/ppil+bwyy34+vfvb+LddtvNyR133HFpP1Pa8JwGpc9+JP7ZZ591ck8//bSJq1RxLy3tsMMOJs5U+qe02CXKJHeu9unTx8kNGDAg7+NB4VxzzTUmLkmpjYsuushp53oeXta4UxcAAAAAAAAAYoSLugAAAAAAAAAQI1zUBQAAAAAAAIAYqXA1de3adZJ0ww03OO3FixebuF+/fgUZE0rXlVdemfW2l112mYmXLFmSj+GgiDVp0iQyt3DhwgKOBMXqtddec9q77LJLTp8zZcoUE48bN26TxoSSmzZtmolPPvlkJ7fPPvuYuFmzZjl9/vDhwzPmH3vsMRN37949crvly5fntH+UL9tvv72J7XqXvjlz5jjtzz77LG9jQvE4+uijM+ZfeeUVE0+YMCHfw0GB2fV107VzZR9//Lqtdk3d9u3bO7m6deuaeMGCBaUyFrjWrFljYv840bx588h+hx12mImrVq3q5Pr27WviTO+/2RT2OwxatWqVl32gbJx33nlO266Z7Nd29k2ePNnEI0aMKN2BlRHu1AUAAAAAAACAGOGiLgAAAAAAAADESIUov1CvXj0T/9///Z+Tq1y5stO2H3X96KOP8jswlDn7kZ1Vq1bl/DmLFi2K/Bz7cZOtttoq8jNq167ttLMtI2E/EiNJ1157rYmXLVuW1WcgN8cee2xk7uWXXy7gSFAo9qNclSpF/1400+OpQ4cOddqNGjWK3Nbfx9q1azc2xLQ6deqUUz/k35dffpk2Lk3ff/99VtvtscceTvvrr7/Ox3CQZwcffLCJM61TL774YiGGgyLjH9+WLl3qtO+4445CDgdF6LnnnnPadvmFU045xcnZpfQonVi+vP3225E5u/SUX35h9erVJn7kkUec3IMPPui0//nPf5o4U7khxN/+++9vYv84U6NGjch+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J7VruC9ZsiTvY5kzZ07W2/7xxx8m9uc04unrr79OG6djv59ku+22c3L2+c25557r5GrVqmVi/30CN954Y/aDRSS73nqmmqc++zhl176VpAceeCCrzxg2bJjTvuSSSyK3/ctf/pL12FA+1KxZ02kfdthhJvZrIvvvEikNVatWddr297fVq1eX+v7yhTt1AQAAAAAAACBGuKgLAAAAAAAAADFS7sovnH766Sa2SzFI0gsvvGDi8ePHF2xMKP/sxzu22WYbJzd06NCsPsMv92GXP+jTp0/Gvj/99JOJn3jiCSd33333mTjTY2ijRo1y2h07djRxw4YNnRzlF0rXgw8+6LRPOukkEy9dutTJ2Y+A5VpuQXIf97juuuucnP1I7NixY52c30Zh1atXz8T7779/1v38dSHf/P3dcsstBd0/gE1nl1zw1367ZNOECROcnP2o7Lhx4yI///zzz3farVq1ctonnniiif3H4e31z96fJC1btixyn8i/pk2bRuYKfSw48sgjnXb16tUjt/UftUXFsmLFChPPmDHDydnz1i+/YJftKEmZPWTvs88+i8zZ5V6qVavm5O69914T+4+5t23btpRG9z/29QBJ+uabb0z8n//8x8nZZT1Rdlq0aOG07dIrH3/8sZPzS9vlqnbt2ibebbfdnJw/T+KCO3UBAAAAAAAAIEa4qAsAAAAAAAAAMcJFXQAAAAAAAACIkXJXU7dbt24m9mud3H333YUeDmKiZcuWkblvv/02q8/w6+ZeeOGFJvZryb3zzjtO+4orrjDx5MmTs9qfL9txovS1bt3aadt/30uWLHFyU6ZMyWkffi2p/v37m7hNmzaR++/Xr19O+0N+2DUnd9xxx8jt3n//faf96quv5mtIJVanTh2nbdfsnjt3bqGHAyDCLrvskjaWpBEjRpjYrgNfEv47B7beemunbb/nonPnzk7uk08+MbF/XLTHM23atJzGhuxtscUWTvuEE06I3NZ+B0S+bLbZZiYeOHBgZM4/v/r666/zOzDE1vHHHx+Zq1mzpom7du3q5G699da8jakiefHFF03s1zW1vxP777Wx6yT734Pywa41L0nPPvusif1a7/a7c1566SUnR134wjnkkEMic/l6j8wpp5xiYvtdKZL03nvv5WWf+cadugAAAAAAAAAQI1zUBQAAAAAAAIAYKXflF2z+I1vjxo0r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
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
