# Table of Contents  
[Introduction](#Introduction)  
[Preview](#Preview)  
[HTML](#HTML)  
[CSS](#CSS)  


# Template

## Introduction

This template display events in a month view tabs.

## Preview

![alt text](https://github.com/SyracuseWorld/capture-render/blob/master/agenda/a-venir-mosaique-tableau/template.png "Démo")


## HTML
```html

 <div class="events-cards-content">
 #foreach($result in $results)
<a href="$result.FriendlyUrl" title="En savoir plus sur $result.REOF_EvenTitle">
 <!--div class="event-card" style="background-image:url($result.ThumbMedium);
 background-repeat:no-repeat;
 background-size:cover;"-->
 <div class="event-card" style="background-image:url(/Ils/digitalCollection/DigitalCollectionThumbnailHandler.ashx?documentId=$result.DigitalReadyThumbnailIdentifier&fallback=http%3a%2f%2fwww.franceoperas.fr%2fui%2fskins%2fdefault%2fportal%2ffront%2fimages%2fGeneral%2fDocType%2fEVEN_LARGE.png&size=LARGE);
 background-repeat:no-repeat;
 background-size:cover;">
#if("$result.REOF_EvenIsPremiere"=="Oui") 
 <div class="event-card-premiere">Première</div>
#elseif("$result.REOF_ProdHistory"=="Nouvelle production") 
 <div class="event-card-new">$!result.REOF_ProdHistory</div>
#elseif("$result.REOF_ProdHistory"=="Création") 
 <div class="event-card-creation">$result.REOF_ProdHistory</div>
#end
 <div class="event-card-title troncate">$!result.REOF_EvenTitle.Substring(0,55,'...')</div>
#if("$!result.REOF_EvenOeuvreComp"!="") 
 <div class="event-card-comp">$!result.REOF_EvenOeuvreComp</div>
#end
 <div class="event-card-author">$!result.REOF_EvenProductionAuthor</div>
 <div class="event-card-location">$!result.REOF_EvenLocation</div>
 <div class="event-card-date">$result.REOF_EvenShortDate</div>
 <div class="event-card-hour">$!result.REOF_EvenWhenStart </div>
 <div class="event-card-type">$!result.REOF_EvenType </div> 
 </div>
</a> 
 #end
</div>

```

## CSS
```css
.event-card {
 float:left;
 margin: 5px 5px;
 width:245px;
height:430px;
 padding: 10px;
 position:relative;
 color:white;
 background-color:#000;
 line-height: 1em; 
 transition: transform .2s 
}

.event-card:hover {
 transform: scale(1.05);
}
.event-card-new {
 font-size:12px;
 position:absolute;
 top:0px;
 right:0px;
 height:20px;
 background-color:#ed220b;
 border:none;
 margin:0;
 padding-top:5px;
 padding-right:5px;
 padding-left:5px;
 text-align:right;
}
.event-card-creation {
 font-size:12px;
 position:absolute;
 top:0px;
 right:0px;
 height:20px;
 background-color:#60d836;
 border:none;
 margin:0;
 padding-top:5px;
 padding-right:5px;
 padding-left:5px;
 text-align:right;
}

.event-card-premiere {
 font-size:12px;
 position:absolute;
 top:0px;
 right:0px;
 height:20px;
 background-color:#ff9300;
 border:none;
 margin:0;
 padding-top:5px;
 padding-right:5px;
 padding-left:5px;
 text-align:right;
}

.event-card-title {
 font-size:23px;
 position:absolute;
 top:35px;
 line-height:1em;
 font-weight:bold;
}
.event-card-comp {
 font-size:23px;
 position:absolute;
 top:118px;
 line-height:1em;
 font-weight:bold;
}

.event-card-author {
 font-size:18px;
 line-height:1em;
 position:absolute;
 top:155px;
}
.event-card-location {
 font-size:18px;
 line-height:1em;
 position:absolute;
 top:190px;
}
.event-card-date {
 font-size:32px;
 position:absolute;
 top:260px; 
 font-weight:bold;
}
.event-card-hour {
 font-size:24px;
 position:absolute;
 top:295px; 
}

.events-cards-content {
 /*width:850px;*/
}

.event-card-type {
 bottom:12px;
 position:absolute;
 font-size:12px
}


```
