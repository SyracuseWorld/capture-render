# Template

## Preview

![alt text](https://github.com/SyracuseWorld/capture-render/blob/master/agenda/programmation-par-mois/preview.png "Démo")


## HTML
```html

 <div class="container-fluid">

 <!-- Nav tabs -->
 <ul class="nav nav-tabs" role="tablist">
 <li role="presentation" class="active"><a href="#decembre" aria-controls="decembre" role="tab" data-toggle="tab">Déc</a></li>
 <li role="presentation"><a href="#janvier" aria-controls="janvier" role="tab" data-toggle="tab">Janv</a></li>
 <li role="presentation"><a href="#fevrier" aria-controls="fevrier" role="tab" data-toggle="tab">Févr</a></li>
 <li role="presentation"><a href="#mars" aria-controls="mars" role="tab" data-toggle="tab">Mars</a></li>
 <li role="presentation"><a href="#avril" aria-controls="avril" role="tab" data-toggle="tab">Avr</a></li>
 <li role="presentation"><a href="#mai" aria-controls="mai" role="tab" data-toggle="tab">Mai</a></li>
 <li role="presentation"><a href="#juin" aria-controls="juin" role="tab" data-toggle="tab">Juin</a></li>
 <li role="presentation"><a href="#juillet" aria-controls="juillet" role="tab" data-toggle="tab">Juil</a></li>
 <li role="presentation"><a href="#aout" aria-controls="aout" role="tab" data-toggle="tab">Août</a></li>
 <li role="presentation"><a href="#septembre" aria-controls="septembre" role="tab" data-toggle="tab">Sept</a></li>
 <li role="presentation"><a href="#octobre" aria-controls="octobre" role="tab" data-toggle="tab">Oct</a></li>
 <li role="presentation"><a href="#novembre" aria-controls="novembre" role="tab" data-toggle="tab">Nov</a></li>
 </ul>

 <!-- Tab panes -->
 <div class="tab-content">
 
 <div role="tabpanel" class="tab-pane active" id="decembre">

 #foreach($result in $results)
 #if($result.MonthYear_exact.Join(",").Contains("date|yyyyMM|Y|201912"))
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 <p class="event-topic"><i class="fas fa-tag"></i>$!result.SubjectTopic_exact</p>

 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $!result.DateStart au $!result.DateEnd</p>
 
 </div>
 </div>
 </a>
 #end
 #end
 </div>
 

 <div role="tabpanel" class="tab-pane" id="janvier">

 #foreach($result in $results)
 #if($result.MonthYear_exact.Join(",").Contains("date|yyyyMM|Y|202001"))
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
</div>
 </div>
 </a>
 #end
 #end
 </div>
 <div role="tabpanel" class="tab-pane" id="fevrier"> <div class="events next-events">

 #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202002")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end
 </div>
 <div role="tabpanel" class="tab-pane" id="mars"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202003")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="avril"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202004")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="mai"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202005")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="juin"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202006")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="juillet"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202007")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="aout"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202008")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="septembre"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202009")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="octobre"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202010")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 <div role="tabpanel" class="tab-pane" id="novembre"> #foreach($result in $results)
 #if($result.MonthYear_exact == "date|yyyyMM|Y|202011")
 <a href="$result.FriendlyUrl" title="En savoir plus sur $!result.Title">
 <div class="card col-sm-3">
 <img src="$!result.LargeThumbnail" class="card-img-top" alt="">
 <div class="card-body">
 <h5 class="card-title">$result.Title.Substring(0,40,'...')</h5>
 #if ($result.DateStart == $result.DateEnd)
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Du $result.DateStart au $result.DateEnd</p>
 #else
 <p class="card-text"><i class="fas fa-calendar-alt"></i>Le $result.DateStart</p>#end
 
 
 </div>
 </div>
 </a>
 #end
 #end</div>
 </div>

</div>
</div>

```

## CSS
```css
.expert-render-mode div.events {
 display: inline-block;
}
.expert-render-mode .card {
 height: 250px;
}
.expert-render-mode .card img {
 height: 150px; 
 width: 100%;
 object-fit: cover;
}
.expert-render-mode .card-body {
 padding: 10px 0;
}
.expert-render-mode .card-title {
 font-weight: bold;
 /* height: 3rem;*/
}
.expert-render-mode p {
 color: #666;
 font-size: 12px;
 margin: 5px 0;
}
.expert-render-mode p i {
 margin-right: 5px;
}

.expert-render-mode .nav.nav-tabs {
 margin-top: 0;
 border-bottom: transparent;
}
.expert-render-mode .nav-tabs > li {
 background-color: transparent;
 padding: 10px 14px;
}
.expert-render-mode .nav-tabs > li > a {
 font-size: 14px;
 padding: 0 0 10px 0;
 /*border-bottom: 2px solid #333;*/
 text-transform: normal;
 background-color: transparent;
}
.expert-render-mode .nav-tabs > li > a:hover {
 color: #4B494A;
}
.expert-render-mode .nav-tabs > li.active > a, .expert-render-mode .nav-tabs > li.active > a:hover, .expert-render-mode .nav-tabs > li.active > a:focus {
 background-color: transparent;
 border-color: transparent;
 border-bottom: 2px solid #e81b40;
 border-radius: 0;
 color: #e81b40;
}
.expert-render-mode .tab-content {
 background-color: transparent;
 color: #4B494A;
 font-size: 16px;
 padding: 20px 0 0;
}

```
