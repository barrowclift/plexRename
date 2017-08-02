plexRename
==========

*Easily and quickly normalize TV show episode files to Plex's preferred naming convention.*

Based on the requirements specified in Plex's [media preparation documentation](https://support.plex.tv/hc/en-us/articles/200220687-Naming-Series-Season-Based-TV-Shows).

Dependencies
------------

Python 3 or newer is required, older python versions are unsupported.

Input Requirements
------------------

The provided files are expected to already have some kind of sequential numbering. This could be numbering from a previous naming convention (e.g. "atla_1x01.m4v"), or some generic sequencer like "Episode 1.m4v", "Episode 2.m4v", etc. Whatever the case, the last provided numerical value in the file name will be used as the episode number. __Take caution if your preexisting naming convention has episode titles following the episode number__; if that title happened to have a number in it, that number would be taken as the episode number instead.

This script assumes all provided files are single episodes only, multi-episode file detection is not currently supported, and they're be treated as a single episode during the rename process instead of two (or more). To handle multi-episode files will require either a different script or a manual fix.

`Optional_Info` fetching (the episode title) is not supported, so the renamed files will not include the episode title. The files will be named generically ("Cowboy Bebop s01e01.m4v", etc.) 

------------------

This script is untested in Windows, works in macOS, and will almost certainly work for most Linux distros.
