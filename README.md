# ECCScan
Playstation 1 Error Correction Codes scanner and fixer

This tool will allow scanning a Playstation 1 game disc dump with mode 2 tracks, dumped in raw sector mode (2352 bytes per sector) and check if Error Detection Code and Error Correction codes match. 

Also, it allows fixing them so they match the data section of the sector. This allows some game translation patches to work in real hardware, as they only patch the data and don't patch the error correction codes, making the real hardware reject them as if the cd was scratched.

MODE PSX optical disc emulator can do this fixes on the fly, with the "Fix Disc ECC" Option, but the extra time needed to correct them can cause issues in slow media, so using this tool makes the image already correct, not requiring the on the fly correction. Also makes the image compatible with other ODE solutions.

**USAGE**
-
- To scan for errors:

	ECCScan _track_bin_file_
    
	For example: 
	`ECCScan "Imadoki no Vampire - Bloody Bride (Japan) [T-En by Bloody Bride Translation Project v1.01] [i].bin"`
	
    This will scan the game track dump and will report any EDC or ECC mistakes.
	If the bin file contains spaces, enclose it with double quotes.

- To fix errors:

	ECCScan -f _track_bin_file_
    
	For example: 
	`ECCScan -f "Imadoki no Vampire - Bloody Bride (Japan) [T-En by Bloody Bride Translation Project v1.01] [i].bin"`
	
    This will scan the game track dump and will report and fix any EDC or ECC mistakes **on the same file**.
	If the bin file contains spaces, enclose it with double quotes.

**Use this tool only on translations and patches, don't use it on original games. It's normal for some original games to have errors in the first couple of sectors. They are mastered that way, they don't affect working, and fixing them would make the dump not 1:1 with original**
