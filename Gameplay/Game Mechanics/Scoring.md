| WARNING: The Scoring is subject to a complete change, informations are valid now but won't stay valid, this page will stay updated |
| --- |

# Scoring in Delta Dash

To calculate the score, the game takes into account three major factors: **Hit Judgement**, **Combo**, and **Mod Multiplier**.

## Hit Judgement
Hit Judgements give a certain amount of points that are multiplied by the current combo. For example, a perfect hit gives 100 points, a good hit gives 50 points, and a meh hit gives 10 points.

## Combo
Combo is calculated by adding 1 to the current combo every time a note is hit, and resetting the combo to 0 if a note is missed. Each point earned from a hit judgement is then multiplied by the current combo.

## Mod Multiplier
Mod Multiplier is a value that determines how much each hit judgement is worth. Some mods increase the mod multiplier, while others decrease it. This value is used to adjust the score based on the challenge or relief offered by the mod.

## Accuracy
The game register each individual hit judgement and calculate the accuracy based on it.

Each hit judgment has a value that is used to calculate the accuracy. The values are as follows:

| Hit Judgment | Value |
|--------------|-------|
| Perfect      | 100   |
| Good         | 66    |
| Meh          | 33    |
| Miss         | 0     |

The accuracy is calculated by adding the value of each hit judgement and dividing it by the total number of hit judgements. For example, if a player hits 10 notes with a perfect hit, 5 notes with a good hit, 2 notes with a meh hit, and 3 notes with a miss, the accuracy would be calculated as follows:

`(100 * 10 + 66 * 5 + 33 * 2 + 0 * 3) / 20` = 82.5%

## Rank Letter
The rank letter is calculated based on the accuracy. and has a Tolerance using mods.

When using mods that harden your gameplay, the game tolerate having a few misses, in consideration of needing an higher accuracy.

Having miss will highly impact your rank.

But in a NoMod Context, Accuracy gaps are like theses:

| Accuracy | Rank Letter Without Miss | Rank Letter With Miss |
|----------|--------------------------|-----------------------|
| = 100%     | SS                       |                     |
| > 90%      | S                        | A                   |
| > 80%      | A                        | B                    |
| > 70%      | B                        | C                    |
| < 70%      | C                        | D                    |

