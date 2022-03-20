# Heroes of the Storm - Voice Line files

This repo contains all the english (`enus`) base voice lines for heroes in Heroes of the Storm, in `.ogg` format.

The files were originally `.ogg` files from the game data and were organised via their Hero name.

This can be used for AI machine learning to clone a voice.

>Note: spaces (` `) and single quotes (`'`) were removed from the original file name for convience. 

## Converting into other formats

If you would like to have another format other than the one stated above, you can do the following:

1. Install [`ffmpeg`](https://ffmpeg.org/) and make sure its is in `$PATH`.
2. Copy the `voicelines` folder, (which contains the original audio files) to your desired folder name, e.g `hero_aac`.
3. CD into it: 
    
    ```bash
    cd hero_aac
    ```
4. Run the command to generate your file format (replace `aac` nearly at the end to your format):

    ```bash
    for file in $(find . -type f -iname "*.ogg"); do ffmpeg -hide_banner -loglevel error -i $file ${file%.*}.aac; done
    ```
5. Remove all the original `.ogg` files:
    ```bash
    find . -type f -iname "*.ogg" -exec rm {} \;
    ```
6. Go back to root directory:
    ```bash
    cd ..
    ```
7. Done!

# Disclaimer

All the audio files in the repo are the property of Blizzard Entertainment.  
