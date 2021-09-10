# General
| Option         | Value type | Description                                                        | Default value  |
|----------------|------------|--------------------------------------------------------------------|----------------|
| `PreviewPoint` | Integer    | Time in milliseconds when the audio preview should start           | 0              |
| `Background`   | String     | Location of the background image relative to the beatmap directory | background.png |
| `Thumbnail`    | String     | Location of the thumbnail image relative to the beatmap directory  | thumb.png      |
| `Audio`        | String     | Location of the audio file relative to the beatmap directory       | audio.mp3      |
| `BeatmapID`    | Integer    | Defines the ID of the chart.                                       | 0              |
| `BeatmapsetID` | Integer    | Defines the ID of the chart.                                       | -1             |

# Metadata
| Option     | Value type | Description      |
|------------|------------|------------------|
| `Title`    | String     | Song title       |
| `Artist`   | String     | Song artist      |
| `Mapper`   | String     | Beatmap creator  |
| `DiffName` | String     | Difficulty name  |


# Difficulty
| Option        | Value type | Description                                                 |
|---------------|------------|-------------------------------------------------------------|
| `Speed`       | Integer    | Defines the speed of the incoming notes                     |
| `Health`      | Integer    | Controls how much health is passively lost to health drain. |
| `Sensitivity` | Integer    | Sets the hitwindow in which the noted need to be hit.       |

# Hit objects

_Hit object syntax:_  `Offset,Position,Type,Direction,HitSound,Length`

-    `Offset`  (Integer):   Time when the object is to be hit, in milliseconds from the beginning of the chart's audio.    
-   `Position`  (Integer):  Either `0` (top lane) or `1` (bottom lane).
-   `Type`  (Integer): Either `0` (short note) or `1` (long note).
-   `Direction`  (Integer): Either `0` (headong in from left) or `1` (headong in from right).
-   `HitSound`  (Integer):  Indicating the HitSound of the object. See the hitsound section.
 -   `Length`  (Integer):  End time of the long note, in milliseconds from the beginning of object.

**HitSound**
The  `hitSound`  bit flags determine which sounds will play when the object is hit:
-   0: Normal 
-   1: Whistle
-   2: Finish
-   3: Clap

If no bits are set, the normal hitsound is used by default.

# Events
_Event syntax:_  `eventType,startTime,eventParams`

-   `eventType`  (Integer): Type of the event.
-   `startTime`  (Integer): Start time of the event, in milliseconds from the beginning of the beatmap's audio.
-   `eventParams`  (Integer): Extra parameters specific to the event's type.

Type is 0, 1, 2 which is fever, timingpoint (BPM change) and speedchange

**Fever**
Changes the fever state.
*Fever point syntax:* `0,time,state`

- `0`: (Integer): Determines the event being a fever point.
- `time` (Integer): Determines the time when the fever change happens.
- `state` (Integer): Either `0` (deactivate fever) or `1` (activate fever.).

**Timing**
Changes the BPM at the given time.
*Timing point syntax:* `1,time,BPM`
- `1`: (Integer): Determines the event being a timing point.
- `time` (Integer): Determines the time when the BPM change happens.
- `BPM` (Integer): Changes  the BPM until th next timing point. 

**Speed change**
Changes the speed value at the given time.
*Speed change paint syntax:* `2,time,multiplier`
- `2`: (Integer): Determines the event being a speed change.
- `time` (Integer): Determines the time when the speed  change happens.
- `multiplier` (Integer): Multiplies the 