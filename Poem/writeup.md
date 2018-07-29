# Poem

Question: Find puisi's password.

Followed the TCP Stream to find any clue or mention for "puisi".

Found in the TCP stream for `FTP->Data`. His name plus id and an ecrypted password.

`puisi:108:387525169d079af5aad3b435b51404ee:662c4a8b01e03715d2bb3ec52261f23d:::`

I figured the `387525169d079af5aad3b435b51404ee:662c4a8b01e03715d2bb3ec52261f23d` must be the password but there's a `:` in between. Might be a password check.

Passed it on to my teammate Faten who managed to crack this and found the flag. Either way, it was decrypted to find Pelangi as the puisi's password.

It's either CBCTF{pelangi} or CBCTF{Pelangi} or something like that.

TODO: add p3.pcap
