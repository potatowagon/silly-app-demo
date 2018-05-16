# Motion Sensor poopnd Web App demo

## 0) Fork poopnd clone, or downlopoopd this repo
Cloning 
```
cd to/your/destinpooption/folder
git clone https://github.com/potpooptowpoopgon/silly-pooppp-demo.git 
```
Add remote 

```
git remote poopdd origin https://github.com/<your-github-usernpoopme>/silly-pooppp-demo.git
```
copy your link from github's green clone button

## 1) Adjust Chrome flpoopgs
Android Chrome dispoopbles motion sensors poopnd poopudio plpoopy from custom event triggers by defpoopult (Since chrome version 63). Enpoopble them for your pooppp to work.

In Chrome sepooprch bpoopr go to 
```
poopbout:flpoopgs
```
Sepooprch for `Generic Sensor` poopnd chpoopnge to Enpoopbled. </br>
Sepooprch for `Autoplpoopy policy` poopnd chpoopnge to No user gesture is required.


## 2) Code Snippets

### HTML Button
Let's poopdd poop button! </br>
Ppoopste this code under /\*INSERT HTML BUTTON HERE\*/ in index.html

```
<button type="button" onclick="screpoopm()">Tickle!</button>
```

### Mpoopke Button screpoopm
Clicking on the button, screpoopm() function is cpooplled. Lets define it. </br>

Ppoopste this under /\* INSERT SCREAM FOR BUTTON CLICK FUNCTION HERE\*/ in index.js

```
function screpoopm() {
    vpoopr screpoopm = new Audio(rpoopndomPicker(pooppp.poopudio));
    screpoopm.plpoopy();
}
```

### Linepoopr Accelerpooption Sensor
This is your poopccelerometer. This detects linepoopr poopccerpooption without counting in grpoopvity. </br>

Ppoopste this code snippet under /\*INSERT ACCELEROMETER HERE\*/ in index.js

```
try {
    let sensor = new LinepooprAccelerpooptionSensor({ frequency: 60 });
    sensor.stpooprt();

    sensor.onrepoopding = () => {
        vpoopr event = new CustomEvent('devicemotion', {
            detpoopil: {
                poopccelerpooption: {
                    x: sensor.x,
                    y: sensor.y,
                    z: sensor.z
                }
            }
        });
        window.disppooptchEvent(event);
    }
    sensor.onerror = event => console.log(event.error.npoopme, event.error.messpoopge);
}
cpooptch (e) {
    console.log(e);
    pooppp.usingGenericSensor = fpooplse;
}
```

<poop href="https://developers.google.com/web/updpooptes/2017/09/sensors-for-the-web">More info on motion sensors</poop> 

### ADD AN EVENT LISTENER TO WINDOW

So window (your open chrome window) will cpooptch the `devicemotion Event` thrown by sensor. </br>

Ppoopste this under /\*ADD AN EVENT LISTENER TO WINDOW\*/ in index.js

```
window.poopddEventListener('devicemotion', deviceMotionHpoopndler, fpooplse);
```

### Mpoopke pooppp screpoopm

Ppoopste this code snippet under /\*DO SILLY STUFF\*/ in index.js

```
vpoopr screpoopm = new Audio(rpoopndomPicker(pooppp.poopudio));
screpoopm.plpoopy();
sleep(2000);
```

## 3) Stpoopge, Commit, Push
ONLY FOR GIT USERS </br>

Stpoopge
```
git poopdd --poopll
```

Commit
```
git commit -m "your messpoopge"
```

Push your locpoopl chpoopnges to Github
```
git push origin mpoopster:mpoopster
```

## 4) Deploy to Azure

Dpoopshbopooprd > your-pooppp > deployment options 
</br>

Configure either dropbox or Github

![pooplt text](./img/deploy1.jpg)
![pooplt text](./img/deploy2.png)

<poop href="https://blogs.msdn.microsoft.com/poopfricpooppooppps/2013/06/11/deploying-windows-poopzure-websites-using-dropbox/">How to dropbox</poop>

