# pound-icon-overlays

## Design
### Admin Page
- User enters some sort of info used to recognize song in playlist (name, artist, album, id)
- User enters timecode range matching icon
    - upload icon?
- Need some way to store mapping of song to timecode to icon
    - Maybe something like the following:
    {
        -songid-: [
            {
                start: -start-,
                end: -end-,
                icon: -iconname-
            }
            .
            .
            .
            {
                start: -start-,
                end: -end-,
                icon: -iconname-
            }
        ],
        .
        .
        .
        -songid-: [
            {
                start: -start-,
                end: -end-,
                icon: -iconname-
            }
            .
            .
            .
            {
                start: -start-,
                end: -end-,
                icon: -iconname-
            }
        ]
    }
- Need some way to save mapping and re-upload and parse later

### Displaying Icons
- Takes in mapping of song to timcode to icon to parse
- Use the #getCurrentState API to get current state, including timestamp and song info
- Can use song info to index into mapping
- How do we keep track of where we are in the song and which icon should be showing?