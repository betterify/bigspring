---
layout: blog
title: Google Script in Hugo
date: 2021-05-11T07:05:45.634+00:00
author: Avadhoot Dandekar
image: https://lh3.googleusercontent.com/pw/ACtC-3cOx9_Z1woEV1vSCJCCpkQQ9-iY39f1GAYrKzpJ1qyzx2JC4ZSZasKlzHEafR40Lvw0DnJ8nwVwcY2pmqXJP69Wyf6Ls3mgIzlfzHRAf-SKIniJ8mZ-GbEQJ6wToC4yRgOBPNJBSs_WLF9GwMvYBix57g=w800-h500-no
type: featured
tags: ["Hugo","Jamstack"]
# meta description
description: "This is meta description"
# post draft
draft: false
---

{{< rawhtml >}}
<div>
<style>
#f2dj__table table {
    font-size: 12pt;
    font-weight:bold;
}
#f2dj__table th {
    background: orange;
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


   // Apply a number formatter to the 2nd column.
   // var table = new google.visualization.Table(document.getElementById('f1dj__table'));

   // var formatter = new google.visualization.ArrowFormat();
    // formatter.format(data, 3); // Apply formatter to 4th column

    // table.draw(data, {allowHtml: true, showRowNumber: true});

     var table = new google.visualization.Table(document.getElementById('f2dj__table'));

     var formatter = new google.visualization.ColorFormat();
     formatter.addRange(-20000, -0, 'white', '#e74c3c');
     formatter.addRange(0, 20000, 'white', '#27ae60');
     formatter.format(data, 3); // Apply formatter to second column

   //var formatter = new google.visualization.ColorFormat();
   //formatter.addRange(-20000, -0, 'white', '#e74c3c');
   //formatter.addRange(0, 20000, 'white', '#e74c3c');
   //formatter.format(data, 8); // Apply formatter to second column

   //var formatter = new google.visualization.ColorFormat();
   //formatter.addRange(-20000, -0, 'white', '#2980b9');
   //formatter.addRange(0, 20000, 'white', '#2980b9');
   //formatter.format(data, 8); // Apply formatter to second column

     table.draw(data, {allowHtml: true, showRowNumber: true, width:'100%', height:'100%' });
}     

google.setOnLoadCallback(f2dj_getData)
</script>
<div id="f2dj__table">
</div>
<!-- END: f1dj Google Spreadsheet/viz api table insert --></div>
{{< /rawhtml >}}