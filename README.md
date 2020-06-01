# DoomBuilderRealm667Bestiary
Addon pack of Doom monsters for use in Doom Builder (All Realm667 Doom monsters)

Have you ever wanted to use all the monsters from the Realm 667 bestiary, but were bogged down by technical issues and unable to load them up in Doom Builder? Fear not! I have taken it upon myself to add them to an easily distributable pk3 archive with the conflicts resolved. All you have to do is load the configuration into Doom Builder and start editing!

# Installation
1) Download files
2) Run the self extracting archive exe file
3) Copy the config file into your "Includes" folder (probably C:\Program Files (x86)\Doom Builder 2\Configurations\Includes)
4) Edit your Doom2.cfg (in the "Configurations" folder) with Notepad or other plain text editor

Find this section
```
// THING TYPES
thingtypes
{
 include("Includes\\Doom_things.cfg");
 include("Includes\\Doom2_things.cfg");
}
```

And make it look like this
```
// THING TYPES
thingtypes
{
 include("Includes\\Doom_things.cfg");
 include("Includes\\Doom2_things.cfg");
 include("Includes\\Doom2_decorate_monsters.cfg");
}
```
5) In Doom Builder, under Tools -> Game Configurations -> Doom 2 -> Resources. Select Add Resource from PK3 file and specify the pk3 file location.

# Distributing your wad
When you distribute your wad file, you'll also need to make sure to distribue the pk3 file along with it, otherwise they will not be able to load the monsters.

# Problems?
Open an Issue in Github and I'll see what I can do about it. Please include the error message you are getting.

# Technical Information About What I Did
For each wad
1) I renamed any "OLDCODE" text document into "DECORATE"
2) I either used the existing ID number, or I assigned a new ID number if none was found
3) In cases where an ID conflict was found, I renamed the ID to a new number
4) In some edge cases, I had to edit the ZSCRIPT file for name conflicts (e.g. lots of things use the Hades Sphere)
5) I wrote a script to take my INFO file of manually transcribed information and converted it into code that Doom Builder can understand
6) I made sure it loaded with no errors, although there are still a lot of warnings.
I haven't tested this a whole lot, but it worked in GZDoom.
