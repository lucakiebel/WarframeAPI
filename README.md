# Warframe.js
A JavaScript API Wrapper for Warframe's WorldState Data

# Installation

To install the Browser version simply add the JS file to your HTML by using the CDN Link or add `app.js` to your project:

#### CDN:
``<script src="https://git.sk-cdn.net/lucakiebel/Warframe.js/master/app.min.js"></script>``

#### From your Project:

``<script src="app.js"></script>``

#### NodeJS

To install the NodeJS Version, use `npm` like so:

```bash
$ npm i --save warframe.js
```


# Usage

For the NodeJS version, first `require` the module:

```javascript
const Warframe = require("warframe.js")
```

After loading in the Script initialize the `Warframe` class, like so:

```javascript
const WF = new Warframe(options);
```

Where `options` is an Object with the following structure:

```javascript
options = {
    platform: "pc"||"ps4"||"xb1"
}
```


Once initalized, you can use the newly created `WF` Object to access the getters, here is a table of those:


| Name                                  | Description                                              | Return Value      |
|---------------------------------------|----------------------------------------------------------|-------------------|
| Warframe.prototype.alerts             | The alerts and all data associated with them             | Promise           |
| Warframe.prototype.cycleCetus         | Current Day- or Nighttime on Cetus                       | Promise           |
| Warframe.prototype.cycleEarth         | Current Day- or Nighttime on Earth                       | Promise           |
| Warframe.prototype.conclaveChallenges | The active Conclave Challenges                           | Promise           |
| Warframe.prototype.dailyDeals         | Darvo's "Daily Deals"                                    | Promise           |
| Warframe.prototype.darkSectors        | The Dark Sectors and what Alliance/Clan has it           | Promise           |
| Warframe.prototype.events             | TBD                                                      | TBD               |
| Warframe.prototype.fissures           | Current Fissure Missions                                 | Promise           |
| Warframe.prototype.heartbeat          | Get a Heartbeat from the API                             | "Success" / Error |
| Warframe.prototype.invasions          | Current Invasion Missions / Infestation Outbreaks        | Promise           |
| Warframe.prototype.news               | News from the News Console (Updates, Prime Access, etc.) | Promise           |
| Warframe.prototype.simaris            | Simaris' current or last target                          | Promise           |
| Warframe.prototype.sorties            | The daily Sorties, Nodes and Conditions                  | Promise           |
| Warframe.prototype.syndicateMissions  | Current Missions of the Syndicates + Cetus Syndicates    | Promise           |
| Warframe.prototype.voidTrader         | When and where Baro will come, and what he carries       | Promise           |


## Examples

#### NodeJS:

```javascript
const Warframe = require("warframe.js");
let options = {platform: "pc"};

const WF = new Warframe(options);

WF.alerts.then(alerts => console.log(alerts));
```

#### Browser:

```javascript
let options = {platform: "pc"};

const WF = new Warframe(options);

(async function(){
    let alerts = await WF.alerts;
    console.log(alerts);
})();
```

To see this in action head over to [tests/test.html](https://lucakiebel.github.io/Warframe.js/tests/test.html)
