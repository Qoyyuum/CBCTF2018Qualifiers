# FileX

Packet Analysis : 75 Points

## Question

Find the suspicious file.

Flag format: CBCTF{filename}

## How I got the flag

I first tried to extract all objects. Looked into every file. Nothing. All of the files extracted were health stuff, yoga pants and detoxification. Clever distraction.

Then I followed TCP stream. Not even too far, found game.exe which was "suspicious" in `tcp stream eq 1`

CBCTF{game.exe}

TODO: Add p2.pcap file
