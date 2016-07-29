# SYNOPSIS
Minimalistic command line Google Play Store scraper for Android apps. Given a
search term, it returns a list of package names that match the search.

## For the Impatients

```
$ casperjs gplsc --price='free' --search='irc' --top=10
```

# REQUIREMENTS
* [CasperJS](http://casperjs.org/) >= 1.1.3 (which in turns requires [PhantomJS](http://phantomjs.org))

# INSALLATION
```
$ npm install -g phantomjs
$ npm install -g casperjs
$ git clone http://github.com/phretor/gplay-scraper.git
$ cd gplay-scraper
```

# USAGE

## Search Top 10 Free "irc" Apps
```
$ casperjs gplsc --price='free' --search='irc' --top=10
net.andchat
com.androirc
com.irccloud.android
org.yaaic
com.simpleirc
com.fusionx.lightirc
org.numixproject.hermes
com.glowing_bear
org.woltage.irssiconnectbot
xerodox.liteirc.free
```

## Search Top 10 Paid "pokemon go" Apps
```
$ casperjs gplsc --price='paid' --search='"pokemon" "go"' --top=10
thanrjones.pogoguide
none.batterygo.batterygo
com.skin1980.batterysaverpokemongopro
com.cristhianescobar.pokimap
com.shreeyaitsolution.pokemongopro
com.compass.keepalivepokemongo
com.ploutosassets.stayforpokemon
com.simonmobileapps.batterypokego
com.pandorica.lookout
com.pokemongomarimbaringtone
```

# COMMAND LINE OPTIONS
```
--search="<the search term>"
--price='free' (default) or 'paid'
--top=10 (default) or any positive integer number
```

# HOW DOES IT WORK?
Uses the powerful [PhantomJS](http://phantomjs.org/) headless to emulate a real
user, slowly scrolling down to trigger the AJAX loading, and scrolling a bit up
when needed to trigger it again (scrolling all the way to the bottom doesn't
always work).

The navigation logic is implemented in [CasperJS](http://casperjs.org).

# FUTURE PLANS
* add category filter
* add top charts
* release it as a NodeJS installable module
