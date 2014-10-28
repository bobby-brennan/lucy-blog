lucy-blog
=========
```js
exports.run = function(dirs, config, next) {
  if (!config.icon) {
    return next();
  }
  var icon = config.icon;
  var iconPath = icon.indexOf('/') === 0 ? icon : dirs.destDir + '/' + icon;
  makeDirs(dirs.destDir, function() {
    runAllConverts(iconPath, config.splash_background);
    next();
  });
}
```
