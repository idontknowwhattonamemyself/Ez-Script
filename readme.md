# Ez-Script
## Starting out
First we need to initialize the library
```lua
local lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/idontknowwhattonamemyself/Ez-Script/Lua/Main"))
```
Congratulations, you just got one step closer to being a pro.

Next, lets try making a simple loop
```lua
ezscript.loop(function()
print("Hello World")
-- this is where you put your code
end, --the stuff to run (this is essential)
"My First Loop", -- this is the name of your loop (if you want to stop it later then this is essential)
0, -- This is the delay between the loop running (it will automatically default to 0)
)
```


Well done, now let's stop the loop

```lua
wait(1) -- not essential but we are going to make the loop wait before stopping
ezscript.breakloop(
    "My First Loop" -- the name of the loop you want to stop (specified earlier) WARNING: will break all loops with this name
)
```
Now, lets notify the user that they are cool

```lua
ezscript.notify(
    "Hello User", -- title (string)
    "You are very cool!", --description/content (string)
    3, --duration (int)
    "rbxassetid://assetid", -- image (string)
)
```
## Advanced
Now that you have learned the ropes, lets move on to some more advanced stuff, for example you want to teleport the player to another part 
```lua
local randomplayer = ezscript.getrandomplayer()
if ezscript.hascharacter(randomplayer) then
ezscript.teleporttopart(
    randomplayer.Character.HumanoidRootPart --part you want to teleport to
)
end
```

Now, lets say that a game automatically changes your walkspeed if it has been changed, to bypass that we can lock the walkspeed property
```lua
local hum = ezscript.gethumanoid()
if hum then
ezscript.lockproperty(
hum, -- Object
"WalkSpeed", --Property Name
50 -- Amount
)
end
```
Now, Lets Try saving some data
```lua
ezscript.savevalue(
    "Super Important Data", -- name of data (to access later)
    "Top Secret!" -- Data To Save
)
```
Now, lets read the data we just stored
```lua
local data = ezscript.loadvalue(
    "Super Important Data" -- name of previously stored data
)
print(data)
```
Lets see how long it takes to print "hi" (in seconds) using stopwatches
```lua
ezscript.stopwatch(
    "hi"
)
print("hi")
print(ezscript.getstopwatch("hi")) --unrounded
print(math.round(ezscript.getstopwatch("hi"))) -- rounded
ezscript.stopstopwatch("hi")
```
### Thanks For Reading and Have Fun
