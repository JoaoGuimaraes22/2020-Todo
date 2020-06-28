# Part 7 | Part 8

## YSort

- Make the world a 2DNode;
- Add a YSort Node to the world;
- Putt everything as a child of the YSort node;

## Background Grass

- Create a "Sprite";
- Give it a Grass "Texture";
- Enable "Region";
- Go to your Grass image;
- Enable "Repeat" and reimport;
- Center your SpriteM
- Set it's position in "Transform", "Position";
- Set the region size in "Region", "Rect";

## TileMap

- Create a TileMap node, child of World, below the Sprite and on top of YSort;
- Set "Cell", "Size", to 16 x 16;
- On the TileSet Window, click "Add Texture(s) to TileSet";
- Select TileSet (ex. DirtTileSet.png);
- Select "New AutoTile";
- Select the tile region;
- Change "Snap Options", "Step", to 16 x 16;
- Change "Selected Tile", "Subtitle Size", to 16 x 16;
- Change "Selected Tile", "Autotile Bitmask Mode", to 3 x 3 (Minimal);
- Use Bitmasks to define when should Tiles be placed;
- Copy the Bitmask Pattern defined;

## CliffTileMap Collision

- Repeat everything from previus step, but now everything is 32 x 32;
- Click on "Collision" on TileSet;
- Make collison rectangles for every Tile part;

## Links

- <https://www.youtube.com/watch?v=v75IMavnRUs&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a&index=7> ;
- <https://www.youtube.com/watch?v=RPgTlxb7Bno&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a&index=8> ;
