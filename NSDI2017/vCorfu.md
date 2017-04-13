# vCorfu: A Cloud-Scale Object Store on a Shared Log

## Shared log shortcoming:

1. clients can't read latest data. (cuz log only stores incremental updates) => playback is the boottleneck

2. 
