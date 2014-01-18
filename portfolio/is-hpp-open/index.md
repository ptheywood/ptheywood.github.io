---
layout: portfolio-item
title: is-hpp-open | Portfolio
---

## is-hpp-open ([Live Site](http://peethwd.net/is-hpp-open/))

Is-hpp-open is an object oriented PHP application making use of the [Rainchasers API](http://ranichasers.com) to predict if the artificial white water course [HPP](http://www.nwscnotts.com/) in Nottingham would be open or not based on river level data provided by the api.

The Rainchasers API collects river level information from the UK Environment agencies public guages and presents detailed information about sections of river, including grading, location, calibrated levels and much more. This is accessible via a public JSON API. is-hpp-open makes use of the JSON API just to access the raw level data from the [colwick guage](http://www.environment-agency.gov.uk/homeandleisure/floods/riverlevels/120752.aspx?stationId=2102) on the River Trent.

The raw data is compared to a set level (2.00m at the time of writing) and a vague string is output of if the course would be open or not. 


{% highlight php %}
<?php
    // Require main class.
    require_once("IsHppOpen/IsHppOpen.php");
    // Register the autoloader if required.
    \IsHppOpen\IsHppOpen::registerAutoloader();

    // Instanciate
    $isHppOpen = new \IsHppOpen\IsHppOpen();

    $stringResponse = $isHppOpen->check(true);
    echo $stringResponse;
{% endhighlight %}

The source is available on [github](http://github.com/peethwd/is-hpp-open) with more detailed instructions for use.
