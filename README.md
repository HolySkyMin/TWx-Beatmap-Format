# TWx Beatmap Format

This repository is to set the standard of the TWx Beatmap Format(TWx in short).

**Latest format version:** 2

## Format Specifications

### Intro

TWx is based on JSON format. It is hard to parse TXT based beatmap format (like BMS), but you can read JSON format using common well-known APIs in every languages. So it gets easier to use TWx to construct your game.

TWx is now accustomed to line-based rhythm games; in other words, the 1-dimension rhythm games. If your rhythm game has linear input line (no matter what the shape of line is), then you can use TWx in almost any situations.

### Structure

Simply say, TWx looks like this:

    {
        "version":2,
        "metadata":
        [
            "level":4,
            "artist":"TWx",
            "mapper":"thiEFcat",
            "density":30
        ],
        "notes":
        [
            {
                "ID":1,
                "Size":0,
                "Color":[255,255,255,255],
                "Mode":0,
                "Flick":0,
                "Time":1.0,
                "Speed":1.0,
                "StartLine":2.0,
                "EndLine":5.0,
                "PrevIDs":[0]
            },
            ...
        ]
    }

### Essential variables

Essential variables are variables which is necessary to run your games. If one value goes wrong, whole game will not be run.

**ID** *int*  
Determines a note's ID.

**Size** *int*  
Determines a note's size.

    0       Small
    1       Large
    2       Special

**Color** *byte[4]*  
Determines a note's color.

**Mode** *int*  
Determines a notes type. Currently determined types are listed below:  

    0       Tap
    1       Hold
    2       Slide
    3       Damage
    4       Hidden
    
Type number 10 and above are allocated to system.

**Flick** *int*  
Determines the flick direction of a note.

    0       None
    1       Left
    2       Right
    3       Up
    4       Down
    
**Time** *float*  
Determines the reaching time of a note.

**Speed** *float*  
Determines the speed of a note. **Please do not set this value to 0 or minus.**

**StartLine** *float*  
Determines the start point of a note.

**EndLine** *float*  
Determines the end point of a note. Note is being hitted at the line of this value.

**PrevIDs** *int[]*  
indicates what note is linked before this note.  

### Optional variables

Optional variables contain extra information of notes, information of the song, and others.

#### Metadata

Metadata usually contains the information of the song or the beatmap itself.

**level** *int*  
Determines the level of this beatmap.  
You can define your level freely. Guideline is written below:

    1       Easy
    2       Normal
    3       Hard
    4       Expert
    
**artist** *string*  
Value about the name of the artist. 'Artist' includes the singer or the unit/group.

**mapper** *string*  
Value about the name of the 'mapper'. Mapper is the creator of this beatmap.

**density** *int*  
Determines the level of the beatmap.

**bpm** *int[]*  
Array of the song's BPM. This is needed when you want to open TWx file in the editor.

**bpmQueue** *int[]*  
Array of the block number. This is needed when you want to open TWx file in the editor.

**beats** *int[]*  
Array of the song's beat. This is needed when you want to open TWx file in the editor.

**beatsQueue** *int[]*  
Array of the block number. This is needed when you want to open TWx file in the editor.

#### Notes

**YPos** *int*  
This value is simillar to 'Tick'. A block is divided in 192 positions. This is needed when you want to open TWx file in the editor.

-------------------------

Discussions are welcomed.
