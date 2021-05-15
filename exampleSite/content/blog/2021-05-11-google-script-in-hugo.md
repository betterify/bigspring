---
layout: blog
title: Google Script Embed in Hugo
date: 2021-05-11T07:05:45.634+00:00
author: Avadhoot Dandekar
image: https://lh3.googleusercontent.com/pw/ACtC-3cOx9_Z1woEV1vSCJCCpkQQ9-iY39f1GAYrKzpJ1qyzx2JC4ZSZasKlzHEafR40Lvw0DnJ8nwVwcY2pmqXJP69Wyf6Ls3mgIzlfzHRAf-SKIniJ8mZ-GbEQJ6wToC4yRgOBPNJBSs_WLF9GwMvYBix57g=w800-h500-no
type: featured
tags: ["Hugo","Google", "Script"]
# meta description
description: "This is meta description"
# post draft
draft: false
---

This post demonstrates the embedding of Google Script in Hugo site.
# Is it possible to embed Google Script in Hugo?

Is it a good idea to see whether Google Script can be embedded in a Hugo site? We all know that Hugo is the fastest framework to build static websites. In this post I am trying embed Google Script in the **Hugo** site!!

## Google Script Example

{{< rawhtml >}}
<style>
#f2dj__table table {
    font-size: 12pt;
    font-weight:bold;
}
#f2dj__table th {
    background: orange;
    font-size: 12pt;
    font-weight:bold;
    color: #fff;
}
</style>
<script src="https://www.google.com/jsapi" type="text/javascript"></script><script type="text/javascript">
var f2dj_sskey='1gOEU8Oo9rPznYHIEkSSOpH0CyUqnvOVeDQTpBo1ERv0'
var f2dj_sheet=752311914
var f2dj_authkey='CITwr80K'
//google.load('visualization', '1', {'packages':['table']});
google.charts.load('48', {packages:['table','controls']});
//https://spreadsheets.google.com/tq?tqx=out:csv&tq=select%20*&key=1M1HJRX36tQNkHOvmP6uCtVgehdMyNDP1JFiSy22GApk&gid=0
function f2dj_getData(){
  var q='select A,C,D,E'
  var url='https://spreadsheets.google.com/tq?tq='+encodeURIComponent(q)+'&key='+f2dj_sskey+'&authkey='+f2dj_authkey+'&gid='+f2dj_sheet;
  var query = new google.visualization.Query(url);
  query.send(f2dj_displayTable);
}
function f2dj_displayTable(response){
if (response.isError()) {
        alert('Error in query: ' + response.getMessage() + ' ' + response.getDetailedMessage());
        return;
      }        
     var data = response.getDataTable();
     visualization = new google.visualization.Table(document.getElementById('f2dj__table'));
     visualization.draw(data, null);   
     var table = new google.visualization.Table(document.getElementById('f2dj__table'));
     var formatter = new google.visualization.ColorFormat(); // Apply a number formatter to the 2nd column.
     formatter.addRange(-20000, -0, 'white', '#e74c3c');
     formatter.addRange(0, 20000, 'white', '#27ae60');
     formatter.format(data, 3); // Apply formatter to second column
     table.draw(data, {allowHtml: true, showRowNumber: true, width:'100%', height:'100%' });
}     
google.setOnLoadCallback(f2dj_getData)
</script>
<div id="f2dj__table">
</div>
<!-- END: f1dj Google Spreadsheet/viz api table insert -->
{{< /rawhtml >}}

## Jfiddle Shortcode Example

{{< jsfiddle "avadhoot/6uqxs5w3" >}}

## Google Script Shortcode Example

{{< gscript src="https://script.google.com/macros/s/AKfycbxrTUsBHBh4aYyy9jzKQHL9Ke1HDTV1jn1qceo9_FB3yxlFZzjfysWA/exec" >}}

{{< rawhtml >}}
<div class="accordion" id="accordionExample">
  <div class="card">
    <div class="card-header" id="headingOne">
      <h2 class="mb-0">
        <button class="btn btn-link" type="button" data-toggle="collapse" data-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
          Collapsible Group Item #1
        </button>
      </h2>
    </div>
    <div id="collapseOne" class="collapse show" aria-labelledby="headingOne" data-parent="#accordionExample">
      <div class="card-body">
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" id="headingTwo">
      <h2 class="mb-0">
        <button class="btn btn-link collapsed" type="button" data-toggle="collapse" data-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
          Collapsible Group Item #2
        </button>
      </h2>
    </div>
    <div id="collapseTwo" class="collapse" aria-labelledby="headingTwo" data-parent="#accordionExample">
      <div class="card-body">
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" id="headingThree">
      <h2 class="mb-0">
        <button class="btn btn-link collapsed" type="button" data-toggle="collapse" data-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
          Collapsible Group Item #3
        </button>
      </h2>
    </div>
    <div id="collapseThree" class="collapse" aria-labelledby="headingThree" data-parent="#accordionExample">
      <div class="card-body">
        Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven't heard of them accusamus labore sustainable VHS.
      </div>
    </div>
  </div>  
</div>
{{< /rawhtml >}}

{{< rawhtml >}}
<p class="codepen" data-height="350" data-theme-id="dark" data-default-tab="result" data-user="AvadhootDandekar" data-slug-hash="ZEeWJrX" data-preview="true" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 1px solid #CCC; margin: 1em 0; padding: 1em;" data-pen-title="BSE Sensex Analysis">
  <span>See the Pen <a href="https://codepen.io/AvadhootDandekar/pen/ZEeWJrX">
  BSE Sensex Analysis</a> by Avadhoot Dandekar (<a href="https://codepen.io/AvadhootDandekar">@AvadhootDandekar</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
{{< /rawhtml >}}