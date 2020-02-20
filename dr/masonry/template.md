# Table of Contents  
[Introduction](#Introduction)  
[Preview](#Preview)  
[HTML](#HTML)  
[CSS](#CSS)  


# Template

## Introduction

This template display events in a month view tabs.

## Preview

![alt text](https://github.com/SyracuseWorld/capture-render/blob/master/dr/masonry/preview.gif "Démo")


## HTML
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/masonry/3.2.2/masonry.pkgd.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery.imagesloaded/3.0.4/jquery.imagesloaded.min.js"></script>
<div class="wrap">
 <div class="gallery-art">
 <div class="grid-sizer"></div>

 #foreach($result in $results)
 <div class="item activate-slide-art" data-id="$velocityCount">
 <img alt="$!result.LargeThumbnail" src="$!result.LargeThumbnail">
 <div class="item-info">
 <button type="button" data-toggle="modal" data-target="#full-view-image"><i class="fas fa-search"></i>
 <div class="item-desc" title="$!result.Title_idx">
 #if("$!result.Title_idx" != "")<h3 class="item-title">$!result.Title_idx</h3>#end
 #if("$$!result.Author_idx" != "")<h4 class="item-author">$!result.Author_idx</h4>#end
 #if("$!result.ContentDescription_idx" != "")
 <p class="item-description">$!result.ContentDescription_idx</p>#end</div></button></div>
 </div>
 #end
 </div>
</div>


<div class="modal fade" id="full-view-image" tabindex="-1" role="dialog" aria-labelledby="full-view-image-title" aria-hidden="true">
 <div class="modal-dialog modal-dialog-centered" role="document">
 <div class="modal-content">
 <div class="modal-header row">
 <div class="modal-title col-md-11" id="full-view-image-title">
 #if("$!result.Title_idx" != "")<h3 class="item-title">$!result.Title_idx</h3>#end
 #if("$$!result.Author_idx" != "")<h4 class="item-author">$!result.Author_idx</h4>#end
 </div>
 <button type="button" class="close col-md-1" data-dismiss="modal" aria-label="Fermer la fenêtre">
 <span aria-hidden="true"><i class="fas fa-times"></i></span>
 </button>
 </div>
 <div class="modal-body">
 <div id="gallery-slide" class="carousel slide" data-interval="false">
 <!-- Indicators -->
 <ol class="carousel-indicators">
 #foreach($result in $results) #if($velocityCount == 1)
 <li data-target="#gallery-slide" data-slide-to="item-$velocityCount" class="active"></li>

 #else
 <li data-target="#gallery-slide" data-slide-to="item-$velocityCount" class=""></li>
 #end #end
 </ol>

 <!-- Wrapper for slides -->
 <div class="carousel-inner" role="listbox">
 #foreach($result in $results) #if($velocityCount == 1)
 <div class="item active">
 <img alt="$!result.LargeThumbnail" src="$!result.LargeThumbnail">
 <div class="carousel-caption">
 #if("$!result.Title_idx" != "")<h3 class="item-title">$!result.Title_idx</h3>#end
 #if("$$!result.Author_idx" != "")<h4 class="item-author">$!result.Author_idx</h4>#end
 #if("$!result.ContentDescription_idx" != "")
 <p class="item-description">$!result.ContentDescription_idx</p>#end
 #if("$!result.Parent_exact" != "")<p class="item-description">Appartient à <a class="linktype-link" href="/doc/SYRACUSE/$!result.Parent_id_exact" target="_blank">$!result.Parent_exact</a></p>#end
 <a class="btn btn-default friendlyUrl" href="$!result.FriendlyUrl" role="button">Plus d'infos</a>
 </div>
 </div>
 #else
 <div class="item">
 <img alt="$!result.LargeThumbnail" src="$!result.LargeThumbnail">
 <div class="carousel-caption">
 #if("$!result.Title_idx" != "")<h3 class="item-title">$!result.Title_idx</h3>#end
 #if("$$!result.Author_idx" != "")<h4 class="item-author">$!result.Author_idx</h4>#end
 #if("$!result.ContentDescription_idx" != "")
 <p class="item-description">$!result.ContentDescription_idx</p>#end
 #if("$!result.Parent_exact" != "")<p class="item-description">Appartient à <a class="linktype-link" href="/doc/SYRACUSE/$!result.Parent_id_exact" target="_blank">$!result.Parent_exact</a></p>#end
 <a class="btn btn-default friendlyUrl" href="$!result.FriendlyUrl" role="button">Plus d'infos</a>

 </div>
 </div>
 #end #end
 </div>

 <!-- Left and right controls -->
 <a class="left carousel-control" href="#gallery-slide" role="button" data-slide="prev">
 <span class="fas fa-chevron-left" aria-hidden="true"></span>
 <span class="sr-only">Previous</span>
 </a>
 <a class="right carousel-control" href="#gallery-slide" role="button" data-slide="next">
 <span class="fas fa-chevron-right" aria-hidden="true"></span>
 <span class="sr-only">Next</span>
 </a>
 </div>
 </div>

 <div class="modal-footer">

 </div>
 </div>
 </div>

```

## CSS
```css
.expert-render-mode .wrap {
 padding: 15px;
 overflow: hidden;
 border-bottom: none;
}

.expert-render-mode .gallery {
 width: 100%;
}

.expert-render-mode .grid-sizer,
.expert-render-mode .item {
 width: calc(19% - 5px);
}

.expert-render-mode .item {
 float: left;
 margin-bottom: 10px;
 margin-left: 10px;
 box-shadow: 0px 2px 5px rgba(0,0,0,0.3);
}
.expert-render-mode + .panel-footer {
 border-top: none;
 }
.expert-render-mode .item:last-of-type,
.item:nth-last-of-type(2) {
 margin-bottom: 0;
}

.expert-render-mode .item img {
 display: block;
 width: 100%;
}

.expert-render-mode .item-info {
 position: absolute;
 top: 0;
 right: 0;
 bottom: 0;
 left: 0;
 padding: 10px;
 background: rgba(255, 255, 255, 0.8);
 text-align: center;
 display: none;
}

.expert-render-mode .item:hover .item-info {
 display: block;
}

.expert-render-mode .item h3.item-title,
.expert-render-mode .item h4.item-author,
.expert-render-mode .item p.item-description,
.expert-render-mode .modal-header {
 color: initial;
 border: none;
}

.expert-render-mode .item h3.item-title {
 font-size: 1.2rem;
 margin: 10px 0;
 font-weight: normal;
 line-height: 1.6;
}

.expert-render-mode .item h4.item-author {
 font-size: 1.2rem;
}

.expert-render-mode .item p.item-description {
 font-size: 1.2rem;
}

.expert-render-mode .item button {
 background: transparent;
 border: transparent;
 width: 100%;
 max-width: 100%;
 position: absolute;
 top: 0;
 bottom: 0;
 left: 0;
 right: 0;
}
.expert-render-mode .item i.fas.fa-search {
 font-size: 2rem;
 padding: 0;
}



.expert-render-mode .modal {
 overflow-y: hidden;
}

.expert-render-mode .modal-dialog {
 width: 100%;
 height: 100%;
 padding: 0;
}

.expert-render-mode .modal-content {
 height: 100%;
 position: relative;
 background: #fff;
 border-radius: 0;
}

.expert-render-mode .modal-header {
 height: 30px;
}

.expert-render-mode .modal-header button.close i {
 float: right;
}

.expert-render-mode .modal-body {
 height: calc(100% - 30px);
 padding: 0;
}
.expert-render-mode .modal-footer {
 display: none;
}
.expert-render-mode ol.carousel-indicators {
 display: none;
}

.expert-render-mode .carousel,
.expert-render-mode .carousel .rsOverflow,
.expert-render-mode .carousel .rsSlide {
 background: transparent;
 height: 100%;
}

.expert-render-mode .carousel-control {
 background: transparent;
 background-image: none;
 color: #999;
 text-shadow: none;
 width: 6vw;
 height: calc(100% - 110px);
}

.expert-render-mode .carousel-control :hover {
 opacity: 1;
}

.expert-render-mode .carousel-inner {
 height: 100%;
}

.expert-render-mode .carousel-inner>.item {
 width: 100%;
 height: 100%;
 margin: 0;
 padding: 10px;
 box-shadow: none;
}

.expert-render-mode .carousel-inner>.item>img,
.expert-render-mode .carousel-inner>.item>a>img {
 width: auto;
 vertical-align: middle;
 max-height: calc(100% - 108px);
 margin: 0 auto;
}


.expert-render-mode .carousel-caption {
 right: 0;
 left: 0;
 bottom: 0;
 padding: 20px;
 z-index: 10;
 color: #ffffff;
 text-align: left;
 text-shadow: none;
}
.expert-render-mode .carousel-caption .item-title,
.expert-render-mode .carousel-caption .item-author,
.expert-render-mode .carousel-caption .item-description {
 float: left;
 width: 70%;
}

.expert-render-mode .carousel-caption .btn {
 float: right;
}

.expert-render-mode .carousel-control .fa-chevron-left,
.expert-render-mode .carousel-control .fa-chevron-right {
 position: absolute;
 top: 50%;
 font-size: 3.5rem;
}
@media (max-width: 374px){
 .item-desc {
 display: none;
}
 .expert-render-mode .grid-sizer,
.expert-render-mode .item {
 width: calc(49% - 5px);
}
.expert-render-mode .item {
 margin: 0;
 }
}
@media (max-width: 767px){
 .item-desc {
 display: none;
}
 .expert-render-mode .grid-sizer,
.expert-render-mode .item {
 width: calc(44% - 5px);
}
@media (max-width: 599px){
 .expert-render-mode .grid-sizer,
.expert-render-mode .item {
 width: 100%;
 margin-bottom: 5px;
}
}

```

# JavaScript 

``` JavaScript
$(function() {
 var $container = $('.gallery-art');
 $container.imagesLoaded(function() {
 $container.masonry({
 itemSelector: '.item',
 columnWidth: '.grid-sizer',
 gutter: 10
 });
 });
 $(document.body).on("click", ".activate-slide-art",
 function() {
 var $this = $(this);
 $("#full-view-image").carousel($this.data("id") - 1);
  $('#gallery-slide').carousel('pause')
 });
 });
```
