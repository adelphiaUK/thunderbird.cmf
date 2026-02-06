# thunderbird.cmf
    A script to copy Thunderbird msgFilterRules.dat file from a selected/master profile to some or all other profiles in Thunderbird. Optional switches: -debug, -verbose, -log &lt;log name>, -maintenance, -path &lt;alternate profile path> and -quick.

    The script opens and reads through the master Thunderbird profiles.ini file, typically located at %APPDATA%\Thunderbird\profiles.ini, and parses all the profile
    configurations found under group headings [Profile<n>] within the master profile file. n is a representative integer starting from 0 incremementing by 1 for each
    profile found.
    Once the profiles have been pasrsed and stored in an array, the user is presented with a menu listing all the profiles found for both ImapMail and Mail groups.
    The user can then select one profile as the source profile (from either ImapMail or Mail subgroups) which the script will use to copy to the other selected profiles.
    The msgFilterRules.dat file and a matching <profile name>.msf file must exist in the selected source folder. This will be simplified by greying out any profile in the
    profile listing menu which does not contain these two files .
    The profiles will be listed in an organised fasion where the user can scroll through them using the arrow keys (up/down only). A selection can be made by pressing [SPACE]
    or [RETURN/ENTER]. The selected profile will be clearly identified by changing colour to a black text on a deep green background in addition to being identified with an
    asterisk which will preceed the profile name. If an incorrect selection is made or if the user wishes to change the selection made, they can do so by pressing [Esc]
    which will clear the selection and allow the user to make a new selection.
    Once the user is satisfied with their selection, the user can then select one or more profiles (from either ImapMail, Mail or both groups) as target profiles to which
    thunderbird.cmf will copy the source msgFilterRules.dat file. These profiles can be in either or both of the profile groups (ImapMail/Mail) and can consist of one or
    many of the profiles shown in the list.
    Once the user is satisfied with and confirms their selection of target profiles, the user will be presented with a summary of the process which will follow and allows
    them to step back and make changes or to proceed with the copy process.
    The script will then copy the source msgFilterRules.dat file to each of the selected target profiles. During the copy process, the script will rename the current
    msgFilterRules.dat file in each of the target profile locations if one exists to msgFilterRules-[yyyy-MM-dd-XX].dat (XX will be a sequential number from 00 to 99).
    If more than 100 backup files are renamed in this fasion, the script will overwrite the oldest backup file with the new backup file.
    Unless the -quick switch is specified at launch, if either -debug or -verbose switch is specified, the script will output information to the console during the
    operation in addition to creating a log file which will be created in the subfolder of the script folder, logs, which will be named "thunderbird.cmf-[yyyy-MM-dd-HHmm].log"
    where [yyyy-MM-dd-HHmm] is the current year, month, date and time at the moment of script launch.
    The user has the option to override the naming of the log file (except when the -quick switch is used) using the -log switch followed by the desired log file name.
    NO BACKUP PROTECTION OF LOG FILES IS PERFORMED WHEN USING THE -log SWITCH. The log file will contain debug and/or verbose messages according to the switches chosen at
    launch. If neither switch is specified, no log file will be created unless the -quick switch is specified as this always creates a debug/verbose log file using the
    same default naming covention, except having the extension .qlog instead of .log. All other switches are ignored when using the -quick switch but backups for both
    msgFilterRules.dat and log files are performed as normal.

    All log files will contain timestamps for each entry.
