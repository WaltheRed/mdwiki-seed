# VLC Snapshots

Hint: Use absolute paths!

    vlc <video-file> --file-logging --logfile=<log-file> --input-fast-seek --rate=<speed multiplier> --video-filter=scene --input-repeat=0 --scene-format=png --scene-ratio=<only use the n-th frames> --scene-prefix=snap --scene-path=<output-folder> vlc://quit

For more information check out the scene section in the CLI documentation found either exported locally using ```vlc --longhelp --advanced --help-verbose``` or [here/online](https://wiki.videolan.org/VLC_command-line_help/)

    --rate=1.0

The playback speed multiplier (good results were achieved with a multiplier of ```10```).

    --scene-ratio=24

Capture every n-th frame of the video output (keep in mind that that this directly influenced by ```-rate```).

Example:
Take a snapshot every 10 seconds in a video-file that plays with 30 frames per second.

    --rate=1 --scene-ratio=300

or
    
    --rate=2 --scene-ratio=150

or

    --rate=10 --scene-ratio=30