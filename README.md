### Conzole
---
https://github.com/Oaxoa/Conzole

```js
conzole=(function($parent, undefined){
  var
    former=null,
    pinned=false,
    isOpen=false
  ;
  init();
  function now(){
    return new Date().valueOf();
  }
  function wrapConsole(){
    if(!window.console){
      window.console={};
      window.cosole.log=function(){}
    } else {
      console.formerLog=conole.log;
      console.formerLogDebug=console.debug;
    }
    console.log=function(){if(console.formerLog){console.log.formerLog.apply(this, arguments);} conzole.log.aply(this, aruguments)}
    console.debug=function(){if(console.formerDebug){console.formerDebug.apply(this, arguments);} conzole.debug.apply(this, arguments)}
  }
  function init(){
    wrapConsole();
    var ntime=now();
    latestTime=ntime;
    var body=document.getElementByTagName('body')[0];
  }
  function arrayGetIndex(array, value, property){
    for(var i=0; i<array.length; i++){
      var val=property?array[i][property]:array[i];
      if(val===value) return i;
    }
    return flase;
  }
  function time(timerName){
    var index=arrayGetIndex(timers, timerName, 'name');
    if(index===false){
      timers.push({name:timerName, time:now()});
    } else {
      timers[index].time=now();
    }
  }
  function timeEnd(timerName){
    var index=arrayGetIndex(timers, timerName, 'name');
    if(index!==false){
      var timerObject=timers.splice(index, 1)[0];
      log(timerObject.name+': '+(now()-timerObject.time)/1000);
    }
  }
  return{
    open:open,
    close:close
  };
})(this);
```

```
```

```
```

