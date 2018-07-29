# Mr. Postman

50 Points

## Question

Can you help decode this?

## How I got the flag

First thought it was a QR code. Tried to scan. Nothing. Maybe something is in it. Checked with file, and binwalk. Nothing and its too small for anything hidden. This is crypto so maybe its the image more.

I just did a Reverse Google Image to find out more about it.
Found name: MaxiCode

I went on to see if theres anything on github or online codebases to decode this. My google-fu got me a VB script. I've no clue how to run.

Another result got me zxwing.org. An online barcode decoder.

Decode with this: https://zxing.org/w/decode.jspx

CBCTF{It5_jU5T_Up5CoD3}
