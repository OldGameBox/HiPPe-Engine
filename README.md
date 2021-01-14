# HiPPe-Engine
#### HiPPe Engine is easy 2D game Engine made on Python using Pygame.

------

# Documentation:
####  

## Installation:
#### To code using HiPPe Engine you need to install __Python ( desirable v.3.9.1 )__ and __HiPPe Launcher__

1. Getting Started:
    * Let's install __Python__. Pick your version:
        * [Python for 64-bit](https://www.python.org/ftp/python/3.9.1/python-3.9.1-amd64.exe)
        * [Python for 32-bit](https://www.python.org/ftp/python/3.9.1/python-3.9.1-amd64.exe)
    * After install __python-3.9.1-amd64.exe__ open it and press `Add to PATH`. Then click Next and continue installation.
    * Now you need to install __HiPPe Launcher__.
        * [HiPPe Launcher](https://github.com/OldGameBox/HiPPe-Launcher/archive/main.zip)
    * You need to unzip archive. You can use built-in archivator or 7-Zip or PeaZip
        * [7-Zip 64-bit](https://www.7-zip.org/a/7z1900-x64.exe)
        * [7-Zip 32-bit](https://www.7-zip.org/a/7z1900.exe)
        * [PeaZip 64-bit](https://github.com/peazip/PeaZip/releases/download/7.7.0/peazip-7.7.0.WIN64.exe)
        * [PeaZip 32-bit](https://github.com/peazip/PeaZip/releases/download/7.7.0/peazip-7.7.0.WINDOWS.exe)
    * To unzip archive you need:
        1. Open folder where you installed archive.
        2. Press 'Right mouse button'.
        3. Press 'Extract'.
2. Creating Project:
    * Open __HiPPe Launcher.exe__
    * Press `Select` and pick where do you want to install project files
    * Press `Create Project` (you need to be connected to Internet)

## Coding
#### Let's start learning HiPPe Engine
------
Import HiPPe Engine in your project:
```python
import hippe
```
------
Hide console:
```python
hp.HideDebbuger()
```
------
Create window:
```python
hp.init(width,height,window_name,music)
```
* `width` - window width
* `height` - window height
* `window_anme` - name of window that you want to create
* `music` - turn on/off music in game

------
Set icon of window:
```python
hp.SetWindowIcon(path)
```
* `path` - icon path
------
Render cycle:
```python
while hp.Drawing():
```
* `hp.Drawing()` - if Rendering
------
FPS Limit:
```python
hp.FPSLimit(value)
```
* `value` - number of FPS
------
Get FPS (returns value) :
```python
hp.GetFPS()
```
------
Check if button `exit` pressed:
```python
hp.OnExit()
```
------
Clear Window:
```python
hp.Clear()
```
------
Get time of one frame rendering:
```python
hp.Delta()
```
------
Render Frame:
```python
hp.Render()
```
------
Stop game ( don't this use as usual, use `hp.Quit()` ):
```python
hp.Exit()
```
------
Stop rendering:
```python
hp.Quit()
```
------
Fill window in color ( you can use fill command or hp.Clear() ):
```python
hp.Fill(color)
```
* `color` - RGB color, exemple `hp.Fill((160,160,160))`
------
##Classes:
------
2D Vector:
```python
hp.Vector(x,y)
```
* `x` - X value
* `y` - Y value

__Attributes:__
* `x` - X value
* `Y` - Y value
Exemple:
```python
import hippe as hp

player = hp.Vector(0,0)

print("Player position: x=" + player.x + ", y=" + player.y)
```
------
2D Sprite:
```python
hp.Sprite(path,vector,scale,rotation)
```
* `path` - image path. __Image is centered!__
* `vector` - position vector (`hp.Vector')
* `scale` - scale (array)
* `rotation` - rotation in degrees

__Attributes:__
* `path` - image path
* `vector` - Sprite position
* `scale` - scale
* `rotation` - rotation in degrees

Exemple:
```python
import hippe as hp

player = hp.Sprite("data/player.png",hp.Vector(250,250),(1,1),50)

print("Player info: image="+player.path+", position: x="+player.position.x+" y="+player.position,y+", scale="+player.scale+", rotation="+player.rotation)
```
------
2D Collider Rect:
```python
hp.ColliderRect(Vector,width,height,scale,rotation)
```
* `Vector` - collider position
* `width` - collider width
* `height` - collider height
* `scale` - collider scale (array)
* `rotation` - __ not using at the moment __

__Attributes:__
* `position` - collider position
* `width` - collider width
* `height` - collider height
* `scale` - collider scale (array)
* `rotation` - __ not using at the moment __

Exemple:
```python
import hippe as hp

col = hp.Collider(hp.Vector(250,250),50,50,(1,1),0)

print("Collider info: position: x="+col.position.x+" y="+col.position,y+", scale="+col.scale+", width="+col.width+", height="+col.height)
```
------
2D Button:
```python
hp.Button(Vector,width,height,rotation,color,text,text_color,fontpath,fontsize,antialias)
```
* `Vector` - position
* `width` - width
* `height` - height
* `rotation` - text rotation
* `color` - button RGB color
* `text` - button text
* `text_color` - button text color
* `fontpath` - font path
* `fontsize` - font size
* `antialias` - antialias

__Attributes:__
* `position` - position
* `width` - width
* `height` - height
* `rotation` - text rotation
* `color` - button RGB color
* `text` - button text
* `text_color` - button text color
* `fontpath` - font path
* `fontsize` - font size
* `antialias` - antialias
------
## Rendering
------
Draw line:
```python
hp.Line(color,Vector_start,Vector_end,width)
```
* `color` - line color
* `Vector_start` - start point
* `Vector_end` - end point
* `width` - line width
------
Draw Sprite:
```python
hp.DrawSprite(Sprite)
```
* `Sprite` - sprite (`hp.Sprite()`)
------
Draw Rect:
```python
hp.DrawRect(Vector,width,height,color):
```
* `Vector` - start position
* `width` - rect width
* `height` - rect height
* `color` - rect RGB color (array)
------
Draw Collider:
```python
hp.DrawCollider(collider):
```
* `collider` - collider (`hp.ColliderRect()`)
------
Draw Button:
```python
hp.DrawButton(button)
```
* `button` - Button (`hp.Button()`)
------
Draw Text:
```python
hp.Text(text,Vector,color,rotation,fontpath,fontsize,antialias,center):
```
* `text` - text
* `Vector` - position
* `color` - text color
* `rotation` - rotation
* `fontpath` - font path
* `fontsize` - font size
* `antialias` - font antialias
* `center` - text centred/not centred
------
## Controls
------
Normalize Vector:
```python
hp.NormalizeVector(vector,speed,rotation):
```
* `vector` - Vector (`hp.Vector`)
* `speed` - speed
* `rotation` - totation
------
Check if keyboard button clicked:
```python
hp.ButtonDown(Button)
```
* `Button` - keyboard button
------
Check if 2D Button pressed:
```python
hp.ButtonClick(Button,mouse_button)
```
* `Button` - 2D button (`hp.Button()`)
* `mouse_button` - mouse button (1/2/3)
------
Check if collider collide with other colliders:
```python
hp.CollideWith(object,list)
```
* `object` - collider (`hp.ColliderRect()`)
* `list` - list of colliders (`hp.ColliderRect()`)
------
Smart Move:
```python
hp.SmartMove(player_vector,speed,wasd):
```
* `player_vector` - player Vector (`hp.Vector()`)
* `speed` - movement speed
* `wasd` - use `w/a/s/d` or `up/left/down/right` ( `False` - `up/left/down/right`, `True` - `w/a/s/d`)
------
## Files and Folders
------
Pick Folder:
```python
hp.GetFolder()
```
------
Pick File:
```python
hp.GetFile()
```
------
## Colors
------
* `hp.BLACK` - black
* `hp.WHITE` - white
* `hp.RED` - red
* `hp.GREEN` - green
* `hp.BLUE` - blue
* `hp.YELLOW` - yellow
* `hp.CYAN` - cyan
* `hp.PINK` - pink
* `hp.GRAY` - gray
------
## Keys
------
* `hp.K_UP` - UP
* `hp.K_DOWN` - DOWN
* `hp.K_LEFT` - LEFT
* `hp.K_RIGHT` - RIGHT
* `hp.K_W` - w
* `hp.K_D` - d
* `hp.K_A` - a
* `hp.K_S` - s
* `hp.K_Q` - q
* `hp.K_E` - e
* `hp.K_R` - r
* `hp.K_T` - t
* `hp.K_Y` - y
* `hp.K_U` - u
* `hp.K_I` - i
* `hp.K_O` - o
* `hp.K_P` - p
* `hp.K_F` - f
* `hp.K_G` - g
* `hp.K_H` - h
* `hp.K_J` - j
* `hp.K_K` - k
* `hp.K_L` - l
* `hp.K_Z` - z
* `hp.K_X` - x
* `hp.K_C` - c
* `hp.K_V` - v
* `hp.K_B` - b
* `hp.K_N` - n
* `hp.K_M` - m
* `hp.K_LSHIFT` - LSHIFT
* `hp.K_RSHIFT` - RSHIFT
* `hp.K_LCTRL` - LCTRL
* `hp.K_RCTRL` - RCTRL
* `hp.K_ESC` - ESCAPE
* `hp.K_LALT` - LALT
* `hp.K_RALT` - RALT
* `hp.K_ENTER` - RETURN
* `hp.K_1` - 1
* `hp.K_2` - 2
* `hp.K_3` - 3
* `hp.K_4` - 4
* `hp.K_5` - 5
* `hp.K_6` - 6
* `hp.K_7` - 7
* `hp.K_8` - 8
* `hp.K_9` - 9
* `hp.K_0` - 0
* `hp.K_F1` - F1
* `hp.K_F2` - F2
* `hp.K_F3` - F2
* `hp.K_F4` - F4
* `hp.K_F5` - F5
* `hp.K_F6` - F6
* `hp.K_F7` - F7
* `hp.K_F8` - F8
* `hp.K_F9` - F9
* `hp.K_F10` - F10
* `hp.K_F11` - F11
* `hp.K_F12` - F12
* `hp.K_PSR` - PRINTSCREEN
* `hp.K_SCROLL` - SCROLLOCK
* `hp.K_INSERT` - INSERT
* `hp.K_HOME` - HOME
* `hp.K_PAGEUP` - PAGEUP
* `hp.K_PAGEDOWN` - PAGEDOWN
* `hp.K_DELETE` - DELETE
* `hp.K_END` - END
* `hp.K_NUM` - NUMLOCK
------
# Thank you for reading this documentation!
### If __you__ found some problems write us!
