# What is new in release v2.0? #

The focus in this relase was to make smartVISU realtime.

The realtime-option is found on the config-screen. If you switch it on, the values will be polled and refreshed.
In this release, realtime is implemented in the 'offline'-driver and 'linknx'-driver. Because of some technical limitations, ist is based on a polling, with a refresh-rate of one secound.

In future releases other drivers will be implemented with the use of websockets.

<img src='http://smartvisu.googlecode.com/svn/wiki/v2.0/cf_knx.jpg' title='config: switch realtime on!' width='300'>


<h2>device.shutter</h2>
A new widget is added in v2.0. The new widget displays a shutter. It may be used for shutters with or without blades.<br>
If you have blades it tries to visualise the angle.<br>
<br>
You may easily bind two (or more) widgets together, if you are going to use the same groupaddress.<br>
<br>
The left widget is 'device.blind' and the right one 'device.shutter':<br>
<br>
<img src='http://smartvisu.googlecode.com/svn/wiki/v2.0/wt_shutter_1.jpg' title='widget: device.shutter' width='600'>

<img src='http://smartvisu.googlecode.com/svn/wiki/v2.0/wt_shutter_2.jpg' title='widget: device.shutter, no blades' width='600'>

<img src='http://smartvisu.googlecode.com/svn/wiki/v2.0/wt_shutter_3.jpg' title='widget: device.shutter, fully opened blades' width='600'>

<img src='http://smartvisu.googlecode.com/svn/wiki/v2.0/wt_shutter_4.jpg' title='widget: device.shutter, partly opened blades' width='600'>

Implement it like this:<br>
<pre><code>{{ device.blind('blind1', 'Blind', 'bath_blind_mov', 'bath_blind_stop', 'bath_blind_pos', 'bath_blind_adjust', 'bath_blind_angle') }}<br>
{{ device.shutter ('shutter1', 'Shutter 1', 'bath_blind_mov', 'bath_blind_stop', 'bath_blind_pos', '', 'bath_blind_angle', 'bath_blind_stored') }}<br>
</code></pre>

The full documentation of all parameters are in the inline 'docu' project.<br>
<br>
The widget was inspired by Jörg Gutowski.