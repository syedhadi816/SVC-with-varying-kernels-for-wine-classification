# SVC-with-varying-kernels-for-wine-classification

<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>HADI_CS504_Project3</title>

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
    /*This file contains any manual css for this page that needs to override the global styles.
This is only required when different pages style the same element differently. This is just
a hack to deal with our current css styles and no new styling should be added in this file.*/

#ipython-main-app {
    position: relative;
}
#jupyter-main-app {
    position: relative;
}

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
<h1 id="CS504-Project-3">CS504 Project 3<a class="anchor-link" href="#CS504-Project-3">&#182;</a></h1><h3 id="Syed-Abdul-Hadi">Syed Abdul Hadi<a class="anchor-link" href="#Syed-Abdul-Hadi">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Importing-Libraries">Importing Libraries<a class="anchor-link" href="#Importing-Libraries">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[263]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">numpy</span> <span class="k">as</span> <span class="nn">np</span>
<span class="kn">import</span> <span class="nn">pandas</span> <span class="k">as</span> <span class="nn">pd</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="kn">import</span> <span class="n">tree</span>
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span>
<span class="kn">from</span> <span class="nn">sklearn.tree</span> <span class="kn">import</span> <span class="n">DecisionTreeClassifier</span> 
<span class="kn">import</span> <span class="nn">seaborn</span> <span class="k">as</span> <span class="nn">sns</span><span class="o">,</span> <span class="nn">matplotlib.pyplot</span> <span class="k">as</span> <span class="nn">plt</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestClassifier</span>
<span class="kn">from</span> <span class="nn">sklearn</span> <span class="kn">import</span> <span class="n">metrics</span> <span class="c1">#Import scikit-learn metrics module for accuracy calculation</span>
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">train_test_split</span> 
<span class="kn">from</span> <span class="nn">sklearn.model_selection</span> <span class="kn">import</span> <span class="n">cross_val_score</span>
<span class="kn">from</span> <span class="nn">sklearn.ensemble</span> <span class="kn">import</span> <span class="n">RandomForestClassifier</span>
<span class="kn">from</span> <span class="nn">sklearn.neighbors</span> <span class="kn">import</span> <span class="n">KNeighborsClassifier</span>
<span class="kn">from</span> <span class="nn">sklearn.naive_bayes</span> <span class="kn">import</span> <span class="n">MultinomialNB</span>
<span class="kn">from</span> <span class="nn">sklearn.naive_bayes</span> <span class="kn">import</span> <span class="n">GaussianNB</span>
<span class="kn">from</span> <span class="nn">sklearn.pipeline</span> <span class="kn">import</span> <span class="n">make_pipeline</span>
<span class="kn">from</span> <span class="nn">sklearn.svm</span> <span class="kn">import</span> <span class="n">SVC</span>
<span class="o">%</span><span class="n">matplotlib</span> <span class="n">inline</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Loading-/-Processing-Data">Loading / Processing Data<a class="anchor-link" href="#Loading-/-Processing-Data">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[146]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#importing data</span>
<span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>

<span class="n">col_names</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>

<span class="n">df</span> <span class="o">=</span> <span class="n">pd</span><span class="o">.</span><span class="n">read_csv</span><span class="p">(</span><span class="s1">&#39;wine.csv&#39;</span><span class="p">,</span> <span class="n">header</span> <span class="o">=</span> <span class="kc">None</span><span class="p">,</span> <span class="n">names</span><span class="o">=</span><span class="n">col_names</span><span class="p">)</span>
<span class="n">df</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[146]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Class</th>
      <th>Alcohol</th>
      <th>Malic acid</th>
      <th>Ash</th>
      <th>Alcalinity of ash</th>
      <th>Magnesium</th>
      <th>Total phenols</th>
      <th>Flavanoids</th>
      <th>Nonflavanoid phenols</th>
      <th>Proanthocyanins</th>
      <th>Color intensity</th>
      <th>Hue</th>
      <th>OD280/OD315 of diluted wines</th>
      <th>Proline</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>14.23</td>
      <td>1.71</td>
      <td>2.43</td>
      <td>15.6</td>
      <td>127</td>
      <td>2.80</td>
      <td>3.06</td>
      <td>0.28</td>
      <td>2.29</td>
      <td>5.64</td>
      <td>1.04</td>
      <td>3.92</td>
      <td>1065</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>13.20</td>
      <td>1.78</td>
      <td>2.14</td>
      <td>11.2</td>
      <td>100</td>
      <td>2.65</td>
      <td>2.76</td>
      <td>0.26</td>
      <td>1.28</td>
      <td>4.38</td>
      <td>1.05</td>
      <td>3.40</td>
      <td>1050</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>13.16</td>
      <td>2.36</td>
      <td>2.67</td>
      <td>18.6</td>
      <td>101</td>
      <td>2.80</td>
      <td>3.24</td>
      <td>0.30</td>
      <td>2.81</td>
      <td>5.68</td>
      <td>1.03</td>
      <td>3.17</td>
      <td>1185</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>14.37</td>
      <td>1.95</td>
      <td>2.50</td>
      <td>16.8</td>
      <td>113</td>
      <td>3.85</td>
      <td>3.49</td>
      <td>0.24</td>
      <td>2.18</td>
      <td>7.80</td>
      <td>0.86</td>
      <td>3.45</td>
      <td>1480</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>13.24</td>
      <td>2.59</td>
      <td>2.87</td>
      <td>21.0</td>
      <td>118</td>
      <td>2.80</td>
      <td>2.69</td>
      <td>0.39</td>
      <td>1.82</td>
      <td>4.32</td>
      <td>1.04</td>
      <td>2.93</td>
      <td>735</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[14]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Analyzing dara</span>


<span class="c1">#Checking for NaN values</span>

<span class="n">df</span><span class="o">.</span><span class="n">isna</span><span class="p">()</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>

<span class="c1">#No NaN Values found</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[14]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Class                           0
Alcohol                         0
Malic acid                      0
Ash                             0
Alcalinity of ash               0
Magnesium                       0
Total phenols                   0
Flavanoids                      0
Nonflavanoid phenols            0
Proanthocyanins                 0
Color intensity                 0
Hue                             0
OD280/OD315 of diluted wines    0
Proline                         0
dtype: int64</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[74]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Outlier analysis </span>


<span class="n">df</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">1</span><span class="p">:</span><span class="mi">4</span><span class="p">]</span><span class="o">.</span><span class="n">boxplot</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[74]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7fc6e11ff1c0&gt;</pre>
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
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[70]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">4</span><span class="p">:</span><span class="mi">7</span><span class="p">]</span><span class="o">.</span><span class="n">boxplot</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[70]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7fc6e103b460&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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kve6q7WauWtaSmZmJuHh4bz99tuEh4e7ZJ333nsv9957b5Nt5syZY/v74MGDTm/TbDZTWlpKQUGB0+syEn9/fz755BPq6+vx9PQEICcnh27durmtpp49e/I///M/btt+a7R06VLg0gdzfHw827Zta7L9kSNHbkRZ7YKhQ76uro7t27ezefNmpkyZwldffcVPfvIT2/0Wi4Xly5dTVFSEt7c3zz33HBMmTGDnzp1s3LiRmpoaLBYLK1asYODAgbbHFRYWsn79ejZt2sTUqVO59957KSoq4ty5cyQnJzNy5EgWLlzIoEGDOHr0KACTJ0/mkUce4cCBA6xduxaA9evX4+Pjw9NPP21b94ULF0hOTqa0tBQPDw8SEhJ46KGHeOaZZzh//jwxMTGN9lDr6upYtmwZx48fp6Kigttvv53169dTV1fHvHnzqKioAGDmzJmMHj0agHfeeYdVq1bx/fffk5SUxKhRo1quE1pYly5dCA4O5tNPP2XIkCEA7N27l5/97GcA/OlPf2Lbtm1cuHABDw8PXn31Ve68804KCwtZsWIFnp6ehIaG8ve//73J/qyoqGDJkiX84x//wMPDg1/+8pe2q6CtXr0agJtvvpm1a9dSXV1NfHw8eXl5ttdBTEwMAH379qW0tJTU1FS++eYbSktL+fbbb5k7dy4HDhzg0KFDBAcHs27dunYxvceJEydYsmQJ58+fp3PnziQlJdG5c2fefvttAG699VaGDx/OokWL+PHHHykvL2fixInMnz//muscNWoUo0aNsl2G9KWXXqJfv37A1V/71+rb1NRUzGYzJ0+e5PTp00yePJlnn32WhoYGXnrpJfbv34+HhwcPPvhgo/cwwMaNG3nvvffo0KED9913Hy+++GILPYPXZ+jhmj//+c/ceuut3H777YwZM8b2wrls06ZNVFdX20L9tdde4+LFi7z99tv87ne/Y/v27UyfPp20tLQmt1NbW8uWLVt44YUX+M1vftPovuTkZODSi2vChAns37+fqqoqrFYrO3bsIDo6ulH71NRU/u3f/o3s7Gz+8Ic/kJqayt/+9jdef/11AgMDrxiC+Pzzz/H29mbLli3s3r0bi8XCnj172L17N0FBQWRmZrJ69epG193t2rUrmZmZJCcn89prr9n9vLY2ERERtuG4w4cP07dvX7y9vamsrOTDDz9k06ZNZGdnM2bMGN566y1qa2v51a9+xerVq8nKysLLq/G+ztX6MyUlhdjYWDIzM3n99ddZsmQJlZWVbNiwgWXLlpGZmUlYWJjtQ705jh07RkZGBqtXr2bRokVMnz6d7Oxsjh49SmlpqeueoFZswYIFTJ06lR07dvDCCy8wZ84cfvKTnzBlyhSmTJlCbGws2dnZREZGkpGRwfbt23nrrbc4d+5ck+v19/cnKyuLX/ziFyQmJtqWX+21f62+BSgtLSUtLY133nmH3//+9/zwww+kp6dz5swZtm/fzjvvvMMHH3zAn//8Z9s26urqeOONN3j33XfJzMzEw8MDs9ns+ievmQy9J5+ZmUlkZCQAEyZMYP78+cydO9d2/6effsojjzxChw4dCAgI4P333wfgtddeIy8vjxMnTnDw4MGrTvrzz/7rv/4LgLvvvpvz589fs12XLl0YOXIkH3zwAb1796Z379707NmzUZsDBw7w0ksvAdCtWzdGjx7NwYMHr7m3PXDgQPz9/dm8eTNffvklZWVlVFdX89Of/pT//u//xmw288ADDzBz5kzbY8aMGQPAXXfdxXfffdfk/9YWhIWF8eqrr9LQ0MDOnTuJiIggJycHPz8/1q5dy/vvv09ZWRmffPIJISEhHDt2jO7duxMcHAzApEmTSElJsa3vav25b98+vvzyS377298Cl97IX3/9NaNHj2bWrFmMGTOG0aNHM2zYsGb/3jNs2DC8vLy49dZbCQgI4K677gIuDfd8//33Lnt+Wquqqiq++uorxo0bB0BoaCg333wzX375ZaN2CQkJHDhwgLS0NI4fP05tbS0XLlxoct2PPPIIcGmvfuHChbYPhau99q/VtwCDBw/Gx8eH7t274+/vz48//khhYSEPP/wwnp6edOrUiaioKPbv3297j3p5efHTn/6USZMmMXr0aB577LEr3uc3kmFD/ttvv+Xjjz+muLiYP/7xj1itVn744Qc++OADW5t/3YM7efIk3bt3JzY2lujoaAYOHEjfvn3ZvHlzk9vy9fUFaNbX69jYWF5//XV69epl+wr/z/51vjir1Up9ff011/fRRx/x29/+lvj4eGJiYvjuu++wWq38x3/8Bzt37uSTTz4hPz+fN998k507dwLYxq6NMhzg5+dHcHAwRUVFHDhwgF/+8pfk5ORw5swZfv7zn/P4448zYsQIevToQUlJCZ6enjQ0NFxzfVfrz4aGBv7whz/g7+8PXPqNpEePHoSEhBAWFkZ+fj6rV6/m8OHDjS596eHhYevT2traRtvx9va2/f2vr8X2wGq1Nuv1vnLlSr7++msiIyMZM2YM+/btu+bc6Zf98/PZ0NBge81f7bV/rb798MMPba+Fy4+xWq1XvHauVvOGDRv461//yscff8xTTz3FmjVrGDRoUJM1txTDDtds376dIUOG8PHHH5OXl0d+fj4zZsxgy5YttjYDBw5k586dWK1Wvv32Wx5//HGOHj1Khw4dmDFjhu3xTYVsc3h6elJXVwfA/fffzz/+8Q8KCxPbGmkAAAM5SURBVAttexX/bMiQIWzduhWAc+fO8dFHHzX54ti/fz8RERHExsbSo0cPPv30U+rr6/nTn/5EamoqERERLF26lHPnzvHjjz869X+0ZhEREaxduxaTyWR7g3fu3JnbbruNadOm0b9/f1tf3nHHHfzwww+2IZEdO3Zcd/1DhgzhrbfeAuCLL77gwQcf5MKFC0yePJmqqiqmTZvGtGnTrhiu8ff354svvgDgww8/dOW/3Ob5+fnRu3dv247XX//6VyoqKrj77rsbvWf27t1LQkICERERnDlzBrPZ3OSHNGD7Vr57927uvPNObr755mu2vVbfNtU+KyuL+vp6Lly4wI4dOxg8eLDt/nPnzhEREUGfPn2YM2cOw4YNc+vwm2F3HzIzM3n++ecbLXv00Uf53//9X/z8/Gy3V6xYwYMPPgjA4sWLGTBgACEhIURERNCxY0cGDhzIN99841Qto0ePJjo6mszMTHx9fRk7diznz5/Hx8fnirYzZ85k2bJlREVFUV9fz4wZM7jnnnuuOQQwefJk5s+fT25uLj4+PoSGhnLq1CmmT5/OvHnziIqKwsvLi1mzZtG1a1en/o/WLCwsjKSkpEZHNXl7e9PQ0MCECRPw8fHhvvvu4/jx4/j4+PDKK6+QmJhIhw4duP322+nYsWOT609OTmbJkiW2vfRXXnkFPz8/5s2bx8KFC/Hy8sLX15fly5c3etyjjz7K3LlziYqKYsiQIQQEBLj+n2/DVq9ezbJly0hNTcXb25vU1FR8fHwYOHAgiYmJ9OjRg2eeeYZf/epXdO3ale7du2Myma47JPaXv/yFrVu30qlTJ1auXNlk22v17bX8/Oc/p6ysjOjoaGpra3nwwQcZO3as7fDMbt26MWXKFCZNmkSnTp245ZZbePjhh+18ZlxH88nfQJcn93/iiSdYtGgR99xzj7tLapcaGhpYs2YNs2bNonPnzmzcuBGz2WzXMdfSeo0aNYo//vGP9OrVy92ltAqG3ZNvjS4f/jV58mQFvBt16NABf39/Jk2ahLe3N0FBQY1+eBUxEu3Ji4gYmGF/eBUREYW8iIihKeRFRAxMIS8iYmAKeRERA1PIi4gY2P8DujF2E7bPmC0AAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[71]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">7</span><span class="p">:</span><span class="mi">10</span><span class="p">]</span><span class="o">.</span><span class="n">boxplot</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[71]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7fc6e11298b0&gt;</pre>
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
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[72]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">df</span><span class="o">.</span><span class="n">iloc</span><span class="p">[:,</span><span class="mi">10</span><span class="p">:</span><span class="mi">13</span><span class="p">]</span><span class="o">.</span><span class="n">boxplot</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[72]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;matplotlib.axes._subplots.AxesSubplot at 0x7fc6e11f9d60&gt;</pre>
</div>

</div>

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,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FAAATp8+jbCwMISFheHTTz8VajeZTNbtRHl5OTQaDU6cOAEAWLp0Kfbs2WM9iiksLMT48ePx9ttvIzQ0FFOnTsX169et66ihbczq1asxbtw4hIWFITExscF1dCunCYfTp09jwIABwpgjw4cPh6enJw4ePIgDBw4gJSUFqampuHjxIrZt21Zv2vfeew/+/v7YtWsX1q5di8WLF+Pq1asAag/B9+zZg8mTJzdaw3/+8x8sXboU33zzDS5fvoysrCwsWbIEALB9+3aUlJTgo48+QlJSEtLS0hAUFIS//e1v1vYPPPAAduzYgcjISKxfvx5msxnr169HcnIyUlJSoFKp6t0zY/z48dBoNHj//ffRt29f9OzZ07pBS01NFb4IVDt68K3dEnq9/o7TZ2ZmwmQyYceOHUhLS0NRURF27txpp2prN4gajUYYh+zpp5++Y3emj48Pfv75ZwBAeHg42rdvD6C2G/LZZ58FAISFheH69esYNmwYoqOjERsbC0AcYbl79+743//+B6C2qycwMFCRulxcXPDbb78hODgYRqMREydOBAD06dMHBoMB999/f722KpUKo0aNwldffYXly5fjjTfeQElJSb1pEhIS4OHhgd27d+OLL75AQkICzpw5g88++wxeXl5C99C3336L06dPY/fu3VizZo01HJpj5syZ8PLywoYNG3DfffdhyZIl+Oijj5Camopp06bhnXfeAQAsWLAAb7/9NlJTU9GzZ09hPv3790dxcTF+//13HDt2DF26dLEGYE5ODoYNG1Zv+jNnzmDatGnYvXs3unTpgl27djW6jfnll1+QmZmJnTt3Ytu2bcjPz0dlZeUdX5fsIbtbm3bt2t1xj+7w4cMICQmx7h1NmDABaWlpGD58eL1p6vb0H374Yfj5+VmT+26jzQK1H+oePXoAAHr37o3S0tJ6z584cQK//vorXnzxRQC1e263fgHqVn6fPn3w3XffwcXFBU8++SQiIiIwatQoTJ48Gd7e3o0uf8KECdi5cycGDhyIw4cP4913371rzfcaLy8vpKen13vsTucccnJycPLkSWvQ3rx5Ew899FCL1ngrlUrVYL96dXX1XdvWfdaB2j3kDz74ACdOnMDmzZsBAImJiRg4cCCMRiPy8/Px0ksvoX///g1+j9q1a4ebN2+ioqICHh4eitXVpUsXZGVlITMzE6+99hr2799vDbLbRUZGWv/fr18/PPHEEzh+/Lg17IDa7/CKFSsAAF27dsWoUaNw9OjRRvv3jx49iueffx6urq7o2rWr9QhLrvz8fBQUFOC1116zPlZWVoaSkhIUFxdj6NChAGoDOzk5uV5blUqFwMBAHDlyBMePH8fUqVPx73//G1qtFg8++KAwEqunpyf69esHoHabUVpa2ug2xtvbG+7u7oiMjIRWq8X8+fPh7u5+x9fiNOGg0WiwdetWSJJUb2/m448/xtChQ63dLbcym831/r79SyFJkvULcOsHujG3vtkqlUqYn8ViwaBBg/D5558DACorK3Hjxg2h/a31r1u3Dj/88AMyMzMxY8aMekcatxszZgzi4+Px7bffIjg42Gnvl9ESbl9fdRs5i8WCqVOnYtq0aQCA3377rdGNV0vw8/PDli1bUF1dDVdXV+vjP/zwAwYMGNBou7Nnz6J3794Aaj/nCxYsQFFRETZv3mzdyOzfvx/x8fFQqVTo1asX/Pz8cPLkSXh7e+PKlSvWeV25cgW9evXCkSNHMGTIEMXq2rNnD1544QWoVCoEBwfj5s2bKC0tRdeuXRtsm5aWhkGDBuGRRx4BUPv9vHXZdY/d/vedTlqrVKp624a6LunGpr11/mazWZi+pqYGPXv2tO6AWCwWXL16VWjb2Gdo+PDhyMnJgclkQlJSEr766itkZGRAq9UK0za0vWlsG+Pi4oLt27fj6NGjyMzMRGRkJLZs2YJevXo1+nqdplvpqaeegqenJxITE60fhkOHDiElJQWPPfYY/P398Y9//AM3b96E2WxGcnIy/P39683D398fO3bsAAAUFBTg+PHjGDhwoM21tW/fHmazGX5+fvjhhx9w4cIFALUb/g8++KDRdiUlJXjhhRfg4+ODefPmITAwEGfPnhXmXfd6O3bsiODgYHz88cfsUmomDw8PnD9/HpIkoaCgwPo++/v7Iz09HTdu3IDZbMasWbPw7bff2q2up556Co899hhWrFhhDSyTyYTPPvsMr7/+eoNt8vPzsXXrVkRFRQGo7WsuKyvDxo0b6+19Pv744/jnP/8JoPazZjKZ4Ovri+DgYHz33XeoqKhASUkJDh8+jICAABw6dMi6Z61EXRs3bsS+ffsA1O7xe3h4NBoMQG2wbNy4EQDw888/Iy8vD4MHD643za3f4ZKSEuzfv98aaA0JCAjA3r17UVVVhdLSUhw6dKjRabt06YLS0lKUlJSgqqqq3rR138M//elPKC0ttV5BmJycjNjYWHh4eOChhx6ynrvZvXt3g8sIDAxEVlYW2rVrB7VaDV9fX2zevBkjRoxotK5bNbaNOX36NKKjo/H0009jwYIF6N27t3WaxjjNkYNKpcK6deuwcuVKhIaGwsXFBR4eHtiwYQO6desGrVaLvLw8TJgwAWaz2drPWteXCtRelrp06VJrv+T777/fpLvb3c2oUaOg1+uRkpKCFStWYP78+aipqYG3tzc+/PDDRtt17doVkZGRiIiIQMeOHfHggw8iLCys3qWFw4YNw7Jly7B69WoMGjQIISEhOH78OPz8/Gyu+14ydOhQJCcnY8yYMejVq5d1ozNy5EicOXMGEydOhMViwbBhwxAWFmbX2hITExEfH4/Q0FC0b98e999/Pz788EM888wz1mnWrl2LL774AiqVCu3bt8eCBQswaNAglJSU4Msvv0TPnj2tJzsBID09HYsWLcI777yDkJAQtGvXDm+++SYeffRRAMC4ceMQEREBs9mMuXPnwtvbGyaTCXFxcYrUBQCrVq3CO++8g08//RSdO3fG2rVr7/g+zJo1C4sXL0ZoaChUKhVWr14NtVotTLN8+XLodDpYLBa8+uqr6N+/PwoLCxuc57PPPotTp04hNDQU3bp1sx7VNKRz586IiYlBREQEevToUe8IacSIEZg5cyb+/ve/Y82aNTAYDKisrIRarcbq1asBAB9++CEWLVqETz75pNGdTrVaXW/e/v7++Omnn+64h3+r7t27N7iN8fDwwMCBAxEaGoqOHTtadwLuhPdzcCIWiwXx8fHw9PS0doMQEcnhNEcOVHtC2sPDA5999pmjSyGiNo5HDkREJHCaE9JERKQchgMREQkYDkREJGA4EBGRgOFAREQChgMREQn+D6O9Cb9fBf7yAAAAAElFTkSuQmCC
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
<p>It appears that we have outliers in the following columns:</p>
<p>Hue</p>
<p>Color Intensity</p>
<p>Proanthocyanins</p>
<p>Ash</p>
<p>Malic Acid</p>
<p>Magnesium</p>
<p>Alcalinity of Ash</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[147]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Removing Outliers</span>

<span class="kn">from</span> <span class="nn">scipy</span> <span class="kn">import</span> <span class="n">stats</span>
<span class="n">z_scores</span> <span class="o">=</span> <span class="n">stats</span><span class="o">.</span><span class="n">zscore</span><span class="p">(</span><span class="n">df</span><span class="p">)</span>

<span class="n">abs_z_scores</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">abs</span><span class="p">(</span><span class="n">z_scores</span><span class="p">)</span>
<span class="n">filtered_entries</span> <span class="o">=</span> <span class="p">(</span><span class="n">abs_z_scores</span> <span class="o">&lt;</span> <span class="mi">3</span><span class="p">)</span><span class="o">.</span><span class="n">all</span><span class="p">(</span><span class="n">axis</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span>
<span class="n">new_df</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">filtered_entries</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[149]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#dataset without outliers, 10 rows have been removed. </span>
<span class="n">new_df</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[149]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Class</th>
      <th>Alcohol</th>
      <th>Malic acid</th>
      <th>Ash</th>
      <th>Alcalinity of ash</th>
      <th>Magnesium</th>
      <th>Total phenols</th>
      <th>Flavanoids</th>
      <th>Nonflavanoid phenols</th>
      <th>Proanthocyanins</th>
      <th>Color intensity</th>
      <th>Hue</th>
      <th>OD280/OD315 of diluted wines</th>
      <th>Proline</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>14.23</td>
      <td>1.71</td>
      <td>2.43</td>
      <td>15.6</td>
      <td>127</td>
      <td>2.80</td>
      <td>3.06</td>
      <td>0.28</td>
      <td>2.29</td>
      <td>5.64</td>
      <td>1.04</td>
      <td>3.92</td>
      <td>1065</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>13.20</td>
      <td>1.78</td>
      <td>2.14</td>
      <td>11.2</td>
      <td>100</td>
      <td>2.65</td>
      <td>2.76</td>
      <td>0.26</td>
      <td>1.28</td>
      <td>4.38</td>
      <td>1.05</td>
      <td>3.40</td>
      <td>1050</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>13.16</td>
      <td>2.36</td>
      <td>2.67</td>
      <td>18.6</td>
      <td>101</td>
      <td>2.80</td>
      <td>3.24</td>
      <td>0.30</td>
      <td>2.81</td>
      <td>5.68</td>
      <td>1.03</td>
      <td>3.17</td>
      <td>1185</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>14.37</td>
      <td>1.95</td>
      <td>2.50</td>
      <td>16.8</td>
      <td>113</td>
      <td>3.85</td>
      <td>3.49</td>
      <td>0.24</td>
      <td>2.18</td>
      <td>7.80</td>
      <td>0.86</td>
      <td>3.45</td>
      <td>1480</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>13.24</td>
      <td>2.59</td>
      <td>2.87</td>
      <td>21.0</td>
      <td>118</td>
      <td>2.80</td>
      <td>2.69</td>
      <td>0.39</td>
      <td>1.82</td>
      <td>4.32</td>
      <td>1.04</td>
      <td>2.93</td>
      <td>735</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>173</th>
      <td>3</td>
      <td>13.71</td>
      <td>5.65</td>
      <td>2.45</td>
      <td>20.5</td>
      <td>95</td>
      <td>1.68</td>
      <td>0.61</td>
      <td>0.52</td>
      <td>1.06</td>
      <td>7.70</td>
      <td>0.64</td>
      <td>1.74</td>
      <td>740</td>
    </tr>
    <tr>
      <th>174</th>
      <td>3</td>
      <td>13.40</td>
      <td>3.91</td>
      <td>2.48</td>
      <td>23.0</td>
      <td>102</td>
      <td>1.80</td>
      <td>0.75</td>
      <td>0.43</td>
      <td>1.41</td>
      <td>7.30</td>
      <td>0.70</td>
      <td>1.56</td>
      <td>750</td>
    </tr>
    <tr>
      <th>175</th>
      <td>3</td>
      <td>13.27</td>
      <td>4.28</td>
      <td>2.26</td>
      <td>20.0</td>
      <td>120</td>
      <td>1.59</td>
      <td>0.69</td>
      <td>0.43</td>
      <td>1.35</td>
      <td>10.20</td>
      <td>0.59</td>
      <td>1.56</td>
      <td>835</td>
    </tr>
    <tr>
      <th>176</th>
      <td>3</td>
      <td>13.17</td>
      <td>2.59</td>
      <td>2.37</td>
      <td>20.0</td>
      <td>120</td>
      <td>1.65</td>
      <td>0.68</td>
      <td>0.53</td>
      <td>1.46</td>
      <td>9.30</td>
      <td>0.60</td>
      <td>1.62</td>
      <td>840</td>
    </tr>
    <tr>
      <th>177</th>
      <td>3</td>
      <td>14.13</td>
      <td>4.10</td>
      <td>2.74</td>
      <td>24.5</td>
      <td>96</td>
      <td>2.05</td>
      <td>0.76</td>
      <td>0.56</td>
      <td>1.35</td>
      <td>9.20</td>
      <td>0.61</td>
      <td>1.60</td>
      <td>560</td>
    </tr>
  </tbody>
</table>
<p>168 rows × 14 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[219]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Checking for highly correlated features, removing those features may improve performance</span>


<span class="c1"># calculate the correlations</span>
<span class="n">correlations</span> <span class="o">=</span> <span class="n">df</span><span class="o">.</span><span class="n">corr</span><span class="p">()</span>

<span class="c1"># plot the heatmap </span>
<span class="n">sns</span><span class="o">.</span><span class="n">heatmap</span><span class="p">(</span><span class="n">correlations</span><span class="p">,</span> <span class="n">xticklabels</span><span class="o">=</span><span class="n">correlations</span><span class="o">.</span><span class="n">columns</span><span class="p">,</span> <span class="n">yticklabels</span><span class="o">=</span><span class="n">correlations</span><span class="o">.</span><span class="n">columns</span><span class="p">,</span> <span class="n">annot</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>


<span class="n">sns</span><span class="o">.</span><span class="n">clustermap</span><span class="p">(</span><span class="n">correlations</span><span class="p">,</span> <span class="n">xticklabels</span><span class="o">=</span><span class="n">correlations</span><span class="o">.</span><span class="n">columns</span><span class="p">,</span> <span class="n">yticklabels</span><span class="o">=</span><span class="n">correlations</span><span class="o">.</span><span class="n">columns</span><span class="p">,</span> <span class="n">annot</span><span class="o">=</span><span class="kc">True</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[219]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>&lt;seaborn.matrix.ClusterGrid at 0x7fc6e3b9b0d0&gt;</pre>
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

<div class="output_area">

    <div class="prompt"></div>




<div class="output_png output_subarea ">
<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAsgAAALJCAYAAACp99XTAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAADh0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uMy4yLjEsIGh0dHA6Ly9tYXRwbG90bGliLm9yZy+j8jraAAAgAElEQVR4nOzdd3xT1RvH8U/SvdggewkcUGSWjYgMRRyI4g9FEFBRcYELUDaCysYJiAOUJbhxIMpyAEIFZF8RBGVTRvfI+v2RUtJaoSmjjO/79eJFc8659zk3TdInT869sXk8HkRERERExMue3xMQEREREbmQKEEWEREREfGhBFlERERExIcSZBERERERH0qQRURERER8KEEWEREREfERmN8TOF+MMQWAFcAtlmXtytZXB5gGFAR+BB6xLMt53icpIiIiIvnusqggG2MaAT8D1f5jyEzgCcuyqgE2oNf5mpuIiIiIXFguiwQZb8L7GLAve4cxpgIQZlnWqoym6cBd529qIiIiInIhuaiXWBhjCgGFcug6blnW8RM3LMt6MGN8TrspDez3ub0fKHsWpykiIiIiFxG/EmRH7M4L7XuphwND/6N9WC73YcuhzZ3XCYmIiIjIxc2/CrLbdY6mkWeT8C6JyO54Dm3/ZS9Q0ud2KXJYiiEiIiIilwf/EmTXhXVhh4xlFP4kwzntY7cxJtUY08yyrF+A+4Bvz8oEJUfR0dEDgND8nofIZSI1JibmlfyehIjIxcSvBNlzgSXIZ8IY8w0wxLKsGOBeYJoxJgpYB7yWr5O79IXGxMQMy+9JiFwOoqOjh+X3HERELjZ+VpAd52ga54dlWRV9fm7v8/PvQMP8mJOIiIiIXFgu6iUWIiIiIiJn22W7xEJEREREJCeX1RILEREREZHT0RILEREREREfSpBFRERERHz4twbZrSUWIiIiInJpUwVZRERERMSHTtITEREREfGhCrKIiIiIiA//EmSnEmQRERERubT5+UUhWmIhIiIiIpc2LbEQEREREfGhBFlERERExIcSZBERERERH0qQRURERER8KEEWEREREfGhBFlERERExIeugywiIiIi4sPPCrLrHE1DREREROTCoCUWIiIiIiI+VEEWEREREfGhNcgiIiIiIj78SpA9qiCLiIiIyCVOa5BFRERERHz4ucRCFWQR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
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
<p>Removing outliers causes a decrease in test_set accuracy for both train-test validation approach and 
10 fold cross validation approach when making decision trees. Therefore I will be moving forward with the 
original dataset.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Decision-Trees">Decision Trees<a class="anchor-link" href="#Decision-Trees">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Train-Test-Split-Approach">Train Test Split Approach<a class="anchor-link" href="#Train-Test-Split-Approach">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[248]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#split dataset in features and target variable</span>
<span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">feature_cols</span><span class="p">]</span> <span class="c1"># Features</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">]</span> <span class="c1"># Target variable</span>


<span class="c1"># Split dataset into training set and test set</span>
<span class="n">X_train</span><span class="p">,</span> <span class="n">X_test</span><span class="p">,</span> <span class="n">y_train</span><span class="p">,</span> <span class="n">y_test</span> <span class="o">=</span> <span class="n">train_test_split</span><span class="p">(</span><span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">test_size</span><span class="o">=</span><span class="mf">0.25</span><span class="p">,</span> <span class="n">random_state</span><span class="o">=</span><span class="mi">1</span><span class="p">)</span> 

<span class="c1"># Create Decision Tree classifer object</span>
<span class="n">clf</span> <span class="o">=</span> <span class="n">DecisionTreeClassifier</span><span class="p">()</span>

<span class="c1"># Train Decision Tree Classifer</span>
<span class="n">clf</span> <span class="o">=</span> <span class="n">clf</span><span class="o">.</span><span class="n">fit</span><span class="p">(</span><span class="n">X_train</span><span class="p">,</span><span class="n">y_train</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[250]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#Evaluation </span>
<span class="c1">#Predict the response for test dataset</span>
<span class="n">y_pred</span> <span class="o">=</span> <span class="n">clf</span><span class="o">.</span><span class="n">predict</span><span class="p">(</span><span class="n">X_test</span><span class="p">)</span>

<span class="n">score</span> <span class="o">=</span> <span class="n">metrics</span><span class="o">.</span><span class="n">accuracy_score</span><span class="p">(</span><span class="n">y_test</span><span class="p">,</span> <span class="n">y_pred</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span><span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy = 95.6 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[133]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">from</span> <span class="nn">IPython.display</span> <span class="kn">import</span> <span class="n">Image</span>  
<span class="kn">from</span> <span class="nn">six</span> <span class="kn">import</span> <span class="n">StringIO</span>  
<span class="kn">import</span> <span class="nn">pydotplus</span>

<span class="n">dot_data</span> <span class="o">=</span> <span class="n">StringIO</span><span class="p">()</span>  
<span class="n">tree</span><span class="o">.</span><span class="n">export_graphviz</span><span class="p">(</span><span class="n">clf</span><span class="p">,</span> <span class="n">out_file</span><span class="o">=</span><span class="n">dot_data</span><span class="p">,</span>  
                         <span class="n">feature_names</span><span class="o">=</span><span class="n">feature_cols</span><span class="p">)</span>  
<span class="n">graph</span> <span class="o">=</span> <span class="n">pydotplus</span><span class="o">.</span><span class="n">graph_from_dot_data</span><span class="p">(</span><span class="n">dot_data</span><span class="o">.</span><span class="n">getvalue</span><span class="p">())</span>  
<span class="n">Image</span><span class="p">(</span><span class="n">graph</span><span class="o">.</span><span class="n">create_png</span><span class="p">())</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[133]:</div>




<div class="output_png output_subarea output_execute_result">
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
<h3 id="10-Fold-Cross-Validation-Approach">10 Fold Cross Validation Approach<a class="anchor-link" href="#10-Fold-Cross-Validation-Approach">&#182;</a></h3>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[251]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#feature_cols = [&#39;Alcohol&#39;, &#39;Malic acid&#39;, &#39;Ash&#39;, &#39;Alcalinity of ash&#39; , &#39;Magnesium&#39;, &#39;Total phenols&#39;, &#39;Flavanoids&#39;, </span>
<span class="c1">#&#39;Nonflavanoid phenols&#39;, &#39;Proanthocyanins&#39;, &#39;Color intensity&#39;, &#39;Hue&#39;, &#39;OD280/OD315 of diluted wines&#39;, &#39;Proline&#39;]</span>

<span class="sd">&#39;&#39;&#39;</span>
<span class="sd">Adjusting for the variables with higher predictive power results in higher accuracy. </span>
<span class="sd">Therefore only these variables are used in the 10-fold cross validation resulting in an </span>
<span class="sd">accuracy greater than 90%. </span>

<span class="sd">&#39;&#39;&#39;</span>

<span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span><span class="s1">&#39;Proline&#39;</span><span class="p">]</span>

<span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">feature_cols</span><span class="p">]</span> <span class="c1"># Features</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">]</span> <span class="c1"># Target variable</span>

<span class="c1"># Create Decision Tree classifer object</span>
<span class="n">clf</span> <span class="o">=</span> <span class="n">DecisionTreeClassifier</span><span class="p">()</span>


<span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">clf</span><span class="p">,</span> <span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;accuracy&#39;</span><span class="p">))</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span><span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy = 92.7 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Ensemble-Random-Forest">Ensemble Random Forest<a class="anchor-link" href="#Ensemble-Random-Forest">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[252]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">feature_cols</span><span class="p">]</span> <span class="c1"># Features</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">]</span> <span class="c1"># Target variable</span>

<span class="n">clf</span> <span class="o">=</span> <span class="n">RandomForestClassifier</span><span class="p">(</span><span class="n">n_estimators</span><span class="o">=</span><span class="mi">10</span><span class="p">)</span>

<span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">clf</span><span class="p">,</span> <span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;accuracy&#39;</span><span class="p">))</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span><span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy = 95.5 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Random forest performs better than decision tree classifier because it prevents overfittiing by 
using multiple trees. While decision trees are less computationally expensive, they are not as accurate as 
random forests.</p>
<p>In this code, decision tree classifier accuracy is around 90%-95%, whereas ensemble random forest gives accuracy up to 
97%.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="KNN">KNN<a class="anchor-link" href="#KNN">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[253]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;</span>
<span class="sd">Preparing the dataset by normaliziing features. </span>
<span class="sd">&#39;&#39;&#39;</span>

<span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">feature_cols</span><span class="p">]</span> <span class="c1"># Features</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">]</span> <span class="c1"># Target variable</span>


<span class="c1">#normalizinig the dataset </span>
<span class="n">X</span> <span class="o">=</span> <span class="n">X</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="p">(</span><span class="n">x</span> <span class="o">-</span> <span class="n">np</span><span class="o">.</span><span class="n">min</span><span class="p">(</span><span class="n">x</span><span class="p">))</span> <span class="o">/</span> <span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">max</span><span class="p">(</span><span class="n">x</span><span class="p">)</span> <span class="o">-</span> <span class="n">np</span><span class="o">.</span><span class="n">min</span><span class="p">(</span><span class="n">x</span><span class="p">)))</span>
<span class="n">X</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[253]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Alcohol</th>
      <th>Malic acid</th>
      <th>Ash</th>
      <th>Alcalinity of ash</th>
      <th>Magnesium</th>
      <th>Total phenols</th>
      <th>Flavanoids</th>
      <th>Nonflavanoid phenols</th>
      <th>Proanthocyanins</th>
      <th>Color intensity</th>
      <th>Hue</th>
      <th>OD280/OD315 of diluted wines</th>
      <th>Proline</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.842105</td>
      <td>0.191700</td>
      <td>0.572193</td>
      <td>0.257732</td>
      <td>0.619565</td>
      <td>0.627586</td>
      <td>0.573840</td>
      <td>0.283019</td>
      <td>0.593060</td>
      <td>0.372014</td>
      <td>0.455285</td>
      <td>0.970696</td>
      <td>0.561341</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.571053</td>
      <td>0.205534</td>
      <td>0.417112</td>
      <td>0.030928</td>
      <td>0.326087</td>
      <td>0.575862</td>
      <td>0.510549</td>
      <td>0.245283</td>
      <td>0.274448</td>
      <td>0.264505</td>
      <td>0.463415</td>
      <td>0.780220</td>
      <td>0.550642</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.560526</td>
      <td>0.320158</td>
      <td>0.700535</td>
      <td>0.412371</td>
      <td>0.336957</td>
      <td>0.627586</td>
      <td>0.611814</td>
      <td>0.320755</td>
      <td>0.757098</td>
      <td>0.375427</td>
      <td>0.447154</td>
      <td>0.695971</td>
      <td>0.646933</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.878947</td>
      <td>0.239130</td>
      <td>0.609626</td>
      <td>0.319588</td>
      <td>0.467391</td>
      <td>0.989655</td>
      <td>0.664557</td>
      <td>0.207547</td>
      <td>0.558360</td>
      <td>0.556314</td>
      <td>0.308943</td>
      <td>0.798535</td>
      <td>0.857347</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.581579</td>
      <td>0.365613</td>
      <td>0.807487</td>
      <td>0.536082</td>
      <td>0.521739</td>
      <td>0.627586</td>
      <td>0.495781</td>
      <td>0.490566</td>
      <td>0.444795</td>
      <td>0.259386</td>
      <td>0.455285</td>
      <td>0.608059</td>
      <td>0.325963</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>173</th>
      <td>0.705263</td>
      <td>0.970356</td>
      <td>0.582888</td>
      <td>0.510309</td>
      <td>0.271739</td>
      <td>0.241379</td>
      <td>0.056962</td>
      <td>0.735849</td>
      <td>0.205047</td>
      <td>0.547782</td>
      <td>0.130081</td>
      <td>0.172161</td>
      <td>0.329529</td>
    </tr>
    <tr>
      <th>174</th>
      <td>0.623684</td>
      <td>0.626482</td>
      <td>0.598930</td>
      <td>0.639175</td>
      <td>0.347826</td>
      <td>0.282759</td>
      <td>0.086498</td>
      <td>0.566038</td>
      <td>0.315457</td>
      <td>0.513652</td>
      <td>0.178862</td>
      <td>0.106227</td>
      <td>0.336662</td>
    </tr>
    <tr>
      <th>175</th>
      <td>0.589474</td>
      <td>0.699605</td>
      <td>0.481283</td>
      <td>0.484536</td>
      <td>0.543478</td>
      <td>0.210345</td>
      <td>0.073840</td>
      <td>0.566038</td>
      <td>0.296530</td>
      <td>0.761092</td>
      <td>0.089431</td>
      <td>0.106227</td>
      <td>0.397290</td>
    </tr>
    <tr>
      <th>176</th>
      <td>0.563158</td>
      <td>0.365613</td>
      <td>0.540107</td>
      <td>0.484536</td>
      <td>0.543478</td>
      <td>0.231034</td>
      <td>0.071730</td>
      <td>0.754717</td>
      <td>0.331230</td>
      <td>0.684300</td>
      <td>0.097561</td>
      <td>0.128205</td>
      <td>0.400856</td>
    </tr>
    <tr>
      <th>177</th>
      <td>0.815789</td>
      <td>0.664032</td>
      <td>0.737968</td>
      <td>0.716495</td>
      <td>0.282609</td>
      <td>0.368966</td>
      <td>0.088608</td>
      <td>0.811321</td>
      <td>0.296530</td>
      <td>0.675768</td>
      <td>0.105691</td>
      <td>0.120879</td>
      <td>0.201141</td>
    </tr>
  </tbody>
</table>
<p>178 rows × 13 columns</p>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="KNN-with-10-Nearest-Neighbours">KNN with 10 Nearest Neighbours<a class="anchor-link" href="#KNN-with-10-Nearest-Neighbours">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[254]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;</span>
<span class="sd">KNN with 10 nearest neighbours and 10 fold cross validation</span>
<span class="sd">&#39;&#39;&#39;</span>

<span class="n">knn_1</span> <span class="o">=</span> <span class="n">KNeighborsClassifier</span><span class="p">(</span><span class="n">n_neighbors</span><span class="o">=</span><span class="mi">10</span><span class="p">)</span>

<span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">knn_1</span><span class="p">,</span> <span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">))</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span><span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy = 96.6 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="KNN-with-Varying-values-of-K-(1---50)">KNN with Varying values of K (1 - 50)<a class="anchor-link" href="#KNN-with-Varying-values-of-K-(1---50)">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[255]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">acc</span> <span class="o">=</span> <span class="nb">list</span><span class="p">()</span>
<span class="n">K</span> <span class="o">=</span> <span class="nb">list</span><span class="p">()</span>


<span class="k">for</span> <span class="n">k</span> <span class="ow">in</span> <span class="nb">range</span> <span class="p">(</span><span class="mi">50</span><span class="p">):</span>
    <span class="n">k</span> <span class="o">+=</span> <span class="mi">1</span>
    <span class="n">knn_1</span> <span class="o">=</span> <span class="n">KNeighborsClassifier</span><span class="p">(</span><span class="n">n_neighbors</span><span class="o">=</span><span class="n">k</span><span class="p">)</span>
    <span class="n">K</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">k</span><span class="p">)</span>
    <span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">knn_1</span><span class="p">,</span> <span class="n">X</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;accuracy&#39;</span><span class="p">))</span>
    <span class="n">acc</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">score</span><span class="p">)</span>
    
    
<span class="n">plt</span><span class="o">.</span><span class="n">plot</span><span class="p">(</span><span class="n">K</span><span class="p">,</span> <span class="n">acc</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">legend</span><span class="p">([</span><span class="s1">&#39;Accuracy&#39;</span><span class="p">,</span> <span class="s1">&#39;K&#39;</span><span class="p">])</span>
<span class="n">plt</span><span class="o">.</span><span class="n">suptitle</span><span class="p">(</span><span class="s1">&#39;Change in Accuracy by Varying K&#39;</span><span class="p">,</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">20</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;K&#39;</span><span class="p">,</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">18</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Accuracy&#39;</span><span class="p">,</span> <span class="n">fontsize</span><span class="o">=</span><span class="mi">18</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">show</span><span class="p">()</span>


<span class="n">max_K</span> <span class="o">=</span> <span class="n">acc</span><span class="o">.</span><span class="n">index</span><span class="p">(</span><span class="nb">max</span><span class="p">(</span><span class="n">acc</span><span class="p">))</span><span class="o">+</span><span class="mi">1</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Highest Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="nb">max</span><span class="p">(</span><span class="n">acc</span><span class="p">),</span> <span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span> <span class="s1">&#39;</span><span class="si">% i</span><span class="s1">s Achieved when K =&#39;</span><span class="p">,</span><span class="n">max_K</span><span class="p">)</span>
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

<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Highest Accuracy = 97.7 % is Achieved when K = 20
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Varyinig K makes a substantial difference when going from K=1 to K=10.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Naive-Bayes">Naive Bayes<a class="anchor-link" href="#Naive-Bayes">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Multinomial-NB">Multinomial NB<a class="anchor-link" href="#Multinomial-NB">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[256]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1">#startinig off by using all features</span>

<span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">feature_cols</span><span class="p">]</span> <span class="c1"># Features</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">]</span> <span class="c1"># Target variable</span>


<span class="n">nb1</span> <span class="o">=</span> <span class="n">MultinomialNB</span><span class="p">(</span><span class="n">alpha</span> <span class="o">=</span> <span class="mf">0.1</span><span class="p">)</span>

<span class="c1">#laplace smoothing parameter (alpha) set to 0.1 leads to highest accuracy</span>

<span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">nb1</span><span class="p">,</span> <span class="n">X</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">y</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;accuracy&#39;</span><span class="p">))</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span><span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy = 86.1 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Gaussian-NB">Gaussian NB<a class="anchor-link" href="#Gaussian-NB">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[233]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">feature_cols</span><span class="p">]</span> <span class="c1"># Features</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">]</span> <span class="c1"># Target variable</span>


<span class="n">nb2</span> <span class="o">=</span> <span class="n">GaussianNB</span><span class="p">()</span>

<span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">nb2</span><span class="p">,</span> <span class="n">X</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">y</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;accuracy&#39;</span><span class="p">))</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span><span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy = 97.8 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>GaussianNB appears to perform better than MultinomialNB. Likely because we have numerical data in decimal form whereas MultinomialNB works better with discrete/categorical data.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Support-Vector-Classifier-(SVC)">Support Vector Classifier (SVC)<a class="anchor-link" href="#Support-Vector-Classifier-(SVC)">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[262]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&#39;&#39;&#39;</span>
<span class="sd">Preparing the dataset by normaliziing features. </span>
<span class="sd">&#39;&#39;&#39;</span>

<span class="n">feature_cols</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;Alcohol&#39;</span><span class="p">,</span> <span class="s1">&#39;Malic acid&#39;</span><span class="p">,</span> <span class="s1">&#39;Ash&#39;</span><span class="p">,</span> <span class="s1">&#39;Alcalinity of ash&#39;</span> <span class="p">,</span> <span class="s1">&#39;Magnesium&#39;</span><span class="p">,</span> <span class="s1">&#39;Total phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Flavanoids&#39;</span><span class="p">,</span> 
<span class="s1">&#39;Nonflavanoid phenols&#39;</span><span class="p">,</span> <span class="s1">&#39;Proanthocyanins&#39;</span><span class="p">,</span> <span class="s1">&#39;Color intensity&#39;</span><span class="p">,</span> <span class="s1">&#39;Hue&#39;</span><span class="p">,</span> <span class="s1">&#39;OD280/OD315 of diluted wines&#39;</span><span class="p">,</span> <span class="s1">&#39;Proline&#39;</span><span class="p">]</span>
<span class="n">X</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="n">feature_cols</span><span class="p">]</span> <span class="c1"># Features</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">df</span><span class="p">[</span><span class="s1">&#39;Class&#39;</span><span class="p">]</span> <span class="c1"># Target variable</span>


<span class="c1">#normalizinig the dataset </span>
<span class="n">X</span> <span class="o">=</span> <span class="n">X</span><span class="o">.</span><span class="n">apply</span><span class="p">(</span><span class="k">lambda</span> <span class="n">x</span><span class="p">:</span> <span class="p">(</span><span class="n">x</span> <span class="o">-</span> <span class="n">np</span><span class="o">.</span><span class="n">min</span><span class="p">(</span><span class="n">x</span><span class="p">))</span> <span class="o">/</span> <span class="p">(</span><span class="n">np</span><span class="o">.</span><span class="n">max</span><span class="p">(</span><span class="n">x</span><span class="p">)</span> <span class="o">-</span> <span class="n">np</span><span class="o">.</span><span class="n">min</span><span class="p">(</span><span class="n">x</span><span class="p">)))</span>
<span class="n">X</span><span class="o">.</span><span class="n">head</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[262]:</div>



<div class="output_html rendered_html output_subarea output_execute_result">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Alcohol</th>
      <th>Malic acid</th>
      <th>Ash</th>
      <th>Alcalinity of ash</th>
      <th>Magnesium</th>
      <th>Total phenols</th>
      <th>Flavanoids</th>
      <th>Nonflavanoid phenols</th>
      <th>Proanthocyanins</th>
      <th>Color intensity</th>
      <th>Hue</th>
      <th>OD280/OD315 of diluted wines</th>
      <th>Proline</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.842105</td>
      <td>0.191700</td>
      <td>0.572193</td>
      <td>0.257732</td>
      <td>0.619565</td>
      <td>0.627586</td>
      <td>0.573840</td>
      <td>0.283019</td>
      <td>0.593060</td>
      <td>0.372014</td>
      <td>0.455285</td>
      <td>0.970696</td>
      <td>0.561341</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0.571053</td>
      <td>0.205534</td>
      <td>0.417112</td>
      <td>0.030928</td>
      <td>0.326087</td>
      <td>0.575862</td>
      <td>0.510549</td>
      <td>0.245283</td>
      <td>0.274448</td>
      <td>0.264505</td>
      <td>0.463415</td>
      <td>0.780220</td>
      <td>0.550642</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.560526</td>
      <td>0.320158</td>
      <td>0.700535</td>
      <td>0.412371</td>
      <td>0.336957</td>
      <td>0.627586</td>
      <td>0.611814</td>
      <td>0.320755</td>
      <td>0.757098</td>
      <td>0.375427</td>
      <td>0.447154</td>
      <td>0.695971</td>
      <td>0.646933</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0.878947</td>
      <td>0.239130</td>
      <td>0.609626</td>
      <td>0.319588</td>
      <td>0.467391</td>
      <td>0.989655</td>
      <td>0.664557</td>
      <td>0.207547</td>
      <td>0.558360</td>
      <td>0.556314</td>
      <td>0.308943</td>
      <td>0.798535</td>
      <td>0.857347</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0.581579</td>
      <td>0.365613</td>
      <td>0.807487</td>
      <td>0.536082</td>
      <td>0.521739</td>
      <td>0.627586</td>
      <td>0.495781</td>
      <td>0.490566</td>
      <td>0.444795</td>
      <td>0.259386</td>
      <td>0.455285</td>
      <td>0.608059</td>
      <td>0.325963</td>
    </tr>
  </tbody>
</table>
</div>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="10-Fold-CV-with-rbf-(default-scikit-learn)-kernel">10 Fold CV with rbf (default scikit-learn) kernel<a class="anchor-link" href="#10-Fold-CV-with-rbf-(default-scikit-learn)-kernel">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[267]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">svc1</span> <span class="o">=</span> <span class="n">SVC</span><span class="p">(</span><span class="n">gamma</span><span class="o">=</span><span class="s1">&#39;auto&#39;</span><span class="p">)</span>
<span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">svc1</span><span class="p">,</span> <span class="n">X</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">y</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;accuracy&#39;</span><span class="p">))</span>

<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">score</span><span class="p">,</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span><span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy = 97.8 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Varying-kernels-for-SVC">Varying kernels for SVC<a class="anchor-link" href="#Varying-kernels-for-SVC">&#182;</a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[284]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">kernels</span> <span class="o">=</span> <span class="p">[</span><span class="s1">&#39;linear&#39;</span><span class="p">,</span> <span class="s1">&#39;sigmoid&#39;</span><span class="p">,</span> <span class="s1">&#39;poly&#39;</span><span class="p">]</span>
<span class="n">acc</span> <span class="o">=</span> <span class="nb">list</span><span class="p">()</span>

<span class="k">for</span> <span class="n">i</span> <span class="ow">in</span> <span class="n">kernels</span><span class="p">:</span> 
    <span class="n">svc2</span> <span class="o">=</span> <span class="n">SVC</span><span class="p">(</span><span class="n">kernel</span> <span class="o">=</span> <span class="n">i</span><span class="p">,</span> <span class="n">gamma</span><span class="o">=</span><span class="s1">&#39;auto&#39;</span><span class="p">)</span>
    <span class="n">score</span> <span class="o">=</span> <span class="n">np</span><span class="o">.</span><span class="n">mean</span><span class="p">(</span><span class="n">cross_val_score</span><span class="p">(</span><span class="n">svc2</span><span class="p">,</span> <span class="n">X</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">y</span><span class="o">.</span><span class="n">values</span><span class="p">,</span> <span class="n">cv</span><span class="o">=</span><span class="mi">10</span><span class="p">,</span> <span class="n">scoring</span> <span class="o">=</span> <span class="s1">&#39;accuracy&#39;</span><span class="p">))</span>
    <span class="n">acc</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">score</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[289]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">plt</span><span class="o">.</span><span class="n">bar</span><span class="p">(</span><span class="n">kernels</span><span class="p">,</span> <span class="n">acc</span><span class="p">,</span> <span class="n">width</span><span class="o">=</span><span class="mf">0.8</span><span class="p">,</span> <span class="n">bottom</span><span class="o">=</span><span class="kc">None</span><span class="p">,</span> <span class="n">align</span><span class="o">=</span><span class="s1">&#39;center&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">xlabel</span><span class="p">(</span><span class="s1">&#39;Kernel Used&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">ylabel</span><span class="p">(</span><span class="s1">&#39;Accuracy&#39;</span><span class="p">)</span>
<span class="n">plt</span><span class="o">.</span><span class="n">title</span><span class="p">(</span><span class="s1">&#39;Accuracy of SVC in Different Kernels&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt output_prompt">Out[289]:</div>




<div class="output_text output_subarea output_execute_result">
<pre>Text(0.5, 1.0, &#39;Accuracy of SVC in Different Kernels&#39;)</pre>
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
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[302]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy with Linear Kernal =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">acc</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span> <span class="s1">&#39;%&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy with Sigmoid Kernal =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">acc</span><span class="p">[</span><span class="mi">1</span><span class="p">],</span><span class="mi">3</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span> <span class="s1">&#39;%&#39;</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="s1">&#39;Accuracy with Poly Kernal =&#39;</span><span class="p">,</span> <span class="nb">round</span><span class="p">(</span><span class="n">acc</span><span class="p">[</span><span class="mi">2</span><span class="p">],</span><span class="mi">2</span><span class="p">)</span><span class="o">*</span><span class="mi">100</span><span class="p">,</span> <span class="s1">&#39;%&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area">

    <div class="prompt"></div>


<div class="output_subarea output_stream output_stdout output_text">
<pre>Accuracy with Linear Kernal = 98.3 %
Accuracy with Sigmoid Kernal = 96.7 %
Accuracy with Poly Kernal = 40.0 %
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span>
</pre></div>

    </div>
</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Results">Results<a class="anchor-link" href="#Results">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>SVC with the linear kernel gives a 98.3% accuracy with 10 fold cross validation which is the highest accuracy among all the models tested.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[&nbsp;]:</div>
<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span>
</pre></div>

    </div>
</div>
</div>

</div>
    </div>
  </div>
</body>

 


</html>
