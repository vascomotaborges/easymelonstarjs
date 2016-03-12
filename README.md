#melonjs-easystar

MelonJS plugin implementing the A* algorithm.

Uses EasyStar.js for path calculations (included).

Requires MelonJS v3.x

License: MIT

##Usage

- Add melonjs-easystar.js to your plugins directory and include it on your game page:
```javascript
<script type="text/javascript" src="lib/plugins/pathfinding/easystar.js"></script>
```
- Register it in your game.js `onload` function:
```javascript
me.plugin.register.defer(this, me.pathfinding.EasyStar, "easystar");
```
- Set the grid:
```javascript
var grid = [[0,0,1,0,0],
            [0,0,1,0,0],
            [0,0,1,0,0],
            [0,0,1,0,0],
            [0,0,0,0,0]];
me.plugins.easystar.setGrid(grid);
```
- Calculate path (async) from `posx, posy` to `goalx, goaly` and execute `callBackFunction(path)` after calculation, where `path` is the calculated path:
```javascript
me.plugins.easystar.setAcceptableTiles([0]);
me.plugins.easystar.findPath(posx, posy, goalx, goaly, callBackFunction(path));
me.plugins.easystar.calculate();
```
- Some other methods can be used. Check EasyStar.js documentation [here](https://github.com/prettymuchbryce/easystarjs/blob/master/README.md#api). Use `me.plugins.easystar` instead of only `easystar`, obviously.

##TODO List

- Use collision layer grid data directly.
- Use object layer data for collisions.
- Implement A* speedup such as RSR or JPS.
- Include example.
