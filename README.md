

# VPX-VBS-Extractor
A utility for bulk extracting .VBS scripts from Visual Pinball X table files (.VPX)
.VBS files are saved in the same directory as the table files. The default behavior is to extract .VBS scripts from tables where a matching .VBS file does not already exist. Extraction is handled by Visual Pinball X, this utility just provides the means to extract .VBS files from a folder of table files.

### Usage
-o, --overwrite          (Default: false) Will overwrite existing .vbs files if true, will skip the table file if
                           false.

  -w, --timeout            (Default: 60) Number of seconds to wait for VPX to exit before continuing to the next table.

  -t, --pathToTables       Required. The path to the vpx tables, e.g. C:\VisualPinball\Tables

  -p, --pathToVPinballX    Required. The path to VPinballX.exe, e.g. C:\VisualPinball\VPinballX.exe

  -s, --testMode           (Default: false) If true, stops after extracting the first script. Useful to tune timeout
                           length.

  --help                   Display this help screen.

  --version                Display version information.
  
### Output
The console will write CREATE, SKIP, or TIMEOUT to based on the result of the 

e.g.

CREATE: Freddy A Nightmare On Elm Street (Gottlieb 1994).vbs

SKIP: Script already exists for Avengers LE (Stern 2012).vpx

TIMEOUT: Hurricane (Williams 1991).vbs - Unsure if script was extracted correctly.

### Examples

 - Standard Usage  
VPX-VBS-Extractor.exe --pathToTables "D:\vPinball\VisualPinball\Tables" -pathToVPinballX "D:\vPinball\VisualPinball\VPinballX.exe" 

 - Test Mode  
 VPX-VBS-Extractor.exe --pathToTables "D:\vPinball\VisualPinball\Tables" -pathToVPinballX "D:\vPinball\VisualPinball\VPinballX.exe" -s
 
 - Slow Computer - Increase timeout before starting the next extraction (120 seconds)  
 VPX-VBS-Extractor.exe --pathToTables "D:\vPinball\VisualPinball\Tables" -pathToVPinballX "D:\vPinball\VisualPinball\VPinballX.exe" -w 120
 
 - Overwrite existing .VBS files  
  VPX-VBS-Extractor.exe --pathToTables "D:\vPinball\VisualPinball\Tables" -pathToVPinballX "D:\vPinball\VisualPinball\VPinballX.exe" -o
