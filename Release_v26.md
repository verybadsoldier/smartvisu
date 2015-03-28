# What is new in release v2.6 #

News & improvements:
  * New: dynamic icons -- svg-icons for continuous values
  * New: config splitted in lib/defaults.php and config.php (individual)
  * New: .js files are now minified. Based on google closure
  * improved devive.rtr now with more modes depending on the driver
  * update vendor/plot.highcharts 3.0.2
  * update vendor/jquery 2.0.3 (IE 6, 7, 8 are no longer supported)
  * update vendor/jquery.mobile 1.3.2



## dynamic icons ##

Dynamic icons are based on svg-images. They are directly rendered in the browser and are the fastest way to show dynamic changes.

<img src='http://smartvisu.googlecode.com/svn/wiki/v2.6/di_svg1.png' title='dynamic icon - value 1' width='600'>
<br>
<img src='http://smartvisu.googlecode.com/svn/wiki/v2.6/di_svg2.png' title='dynamic icon - value 2' width='600'>