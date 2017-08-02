plexRename
==========

*Easily and quickly normalize TV show episode files to Plex's preferred naming convention.*

Based on the requirements specified in Plex's [media preparation documentation](https://support.plex.tv/hc/en-us/articles/200220687-Naming-Series-Season-Based-TV-Shows).

Dependencies
------------

Python 3 or newer is required, older python versions are unsupported.

Input Requirements
------------------

Based on the assumptions made by this script, mixing files and directories is not supported (you must either provide only directories or only files).

### Files

If files are provided ("Episode\ *", individually, what have you), they are all assumed to be from a single season show (So "Episode 1.m4v" would be named "Some_Show_Title - s01e01.m4v"). If your show has more than one season, group them into separate directories by season before hand and provide the directories as the input.

The provided files are expected to already have some kind of sequential numbering. This could be numbering from a previous naming convention (e.g. "atla_1x01.m4v"), or some generic sequencer like "Episode 1.m4v", "Episode 2.m4v", etc. Whatever the case, the last provided numerical value in the file name will be used as the episode number. __Take caution if your preexisting naming convention has episode titles following the episode number__; if that title happened to have a number in it, that number would be taken as the episode number instead.

This script assumes all provided files are single episodes only, multi-episode file detection is not currently supported, and they're be treated as a single episode during the rename process instead of two (or more). To handle multi-episode files will require either a different script or a manual fix.

`Optional_Info` fetching (the episode title) is not supported, so the renamed files will not include the episode title. The files will be named generically ("Cowboy Bebop s01e01.m4v", etc.) 

### Directories

If directories are provided, they are assumed to be separate seasons of the same show and all files at the first depth of that directory are episodes belonging to that season.

The season directories, like the episode files, can be named *mostly* whatever you want, as long as the last provided number of the directory name represents the season number (for example, "Season 2", "s2", "s_02", etc. are all suitable because the season number would be correctly read as '2').

------------------

This script is untested in Windows, works in macOS, and will almost certainly work for most Linux distros.