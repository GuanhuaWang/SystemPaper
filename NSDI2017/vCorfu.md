# vCorfu: A Cloud-Scale Object Store on a Shared Log

## Shared log shortcoming:

1. clients can't read latest data. (cuz log only stores incremental updates) => playback is the bottleneck

2. 


## vCorfu

build a two layer architecture of streams under global log.

vCorfu sequencer not only track the tail of the global log, but also the tail of each stream.

client get two address 1) global address 2) stream address.

Client write to log replica using global address, and write to stream replica using stream ID and stream address.

### overhead

more commit log (since we need to not only write to global log, but also stream log), but it pay back.

### benefit

now we can access log on only one replica (stream replica), instead of multiple replica belong to global log servers.
