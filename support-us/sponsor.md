---
layout: subpage
title: Support Us
subtitle: Become a Sponsor
permalink: /support-us/sponsor/
---

Welcome! We're so glad to see you here. Your consideration of supporting our team means a lot to us, and we know you probably have some questions about sponsoring our team.

## How does your sponsorship help us?
We love what we do, and want to pursue everything we think up. In order to accomplish these goals, we need to purchase raw materials for machining practice and construction, electronics and computer hardware for advancements in control systems, LEGO and VEX robot sets to bring STEM education to our community, and so much more. With your monetary support, we can be enabled to achieve goals that we could have previously never even imagined.

Want even more team information? Check out [our team resources](/resources/). Also, you can download our sponsorship information packet!
<div>
<a href="/resources/2019SponsorshipInfoPacket.pdf">
<div class="button hover_animate" style="text-align: center;">
Sponsorship Information Packet (.pdf)
</div>
</a>
</div>
<br>

## Sponsorship Levels
All of our sponsors are inredibly important to us, and we like to express our gratitude to them for their instrumental help to our team. Our sponsorship levels and benefits are listed below.

<script>
function toggle(level) {
	var elements = document.getElementsByClassName("circle");

	{% for level in site.data.sponsor_levels %}
	$(document.getElementById("{{ level.level }}")).removeClass('expanded');
	{% endfor %}

	$(document.getElementById(level)).addClass('expanded');


	{% for level in site.data.sponsor_levels %}	
	$(document.getElementById("{{ level.level }}info")).css('display', "none");
	{% endfor %}

	$(document.getElementById(level + "info")).css('display', "table");
}

$( document ).ready(function() {
	toggle("Title");
});
</script>

<div class="levels">
	<div style="text-align: center;">
		<i>Click one of the sponsorship levels below to learn about the benefits.</i>
	</div>
	<table width="100%" border="0" cellpadding="0" cellspacing="0">
		<tr>
		{% for level in site.data.sponsor_levels %}
			<td width="172px" height="152px" align="center" class="circle hover_animate" id="{{ level.level }}" style="background: {{ level.color }};" onClick='toggle("{{ level.level }}")'>
				<div>
					{{ level.level }}
				</div>
			</td>
		{% endfor %}
		</tr>
	</table>

	{% for level in site.data.sponsor_levels %}
		<table id="{{ level.level }}info" style="display: none;" width="100%" border="0" cellpadding="10" cellspacing="0">
			<tr>
				<td style="width: 250px;" bgcolor="{{ level.color }}" align="center">
					<b><font color="white" size="40px">{{ level.level }}</font></b>
					<br>
					<font color="white">{{ level.money }}</font>
				</td>
				<td>
					<ul>
						{% for benefit in site.data.sponsor_benefits %}
							<text
							{% if benefit.id > level.id %} class="crossed" {% endif %}
							>
							<li>{{benefit.description}}</li>
							</text>
						{% endfor %}
					</ul>
				</td>
			</tr>
		</table>
	{% endfor %}
</div>

<table class="mobilelevels" width="100%" border="0" cellpadding="10" cellspacing="0">
	{% for level in site.data.sponsor_levels %}
  	<tr>
    	<td bgcolor="{{ level.color }}" align="center">
      	<b><font color="white" size="40px">{{ level.level }}</font></b>
      	<br>
      	<font color="white">{{ level.money }}</font>
    	</td>
	</tr>
	<tr>
    	<td>
      		<ul>
				{% for benefit in site.data.sponsor_benefits %}
				<text
					{% if benefit.id > level.id %} class="crossed" {% endif %}
				>
					<li>{{benefit.description}}</li>
				</text>
				{% endfor %}
			</ul>
    	</td>
  	</tr>
	{% endfor %}
</table>