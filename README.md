# Lv2 patches
## Remove unnecessary ethernet dependency for the deci3 server
`0x284218` with instructions: `60000007`  
`0x284118` with instructions: `48000030`   

Afterwards, you can toggle the internet connection to send a new event. Event 2 will first fire, shutting the server off. When turning the link back on, event 1 fires, which now turns on the server instead of being reliant on event 4 (ethernet link is connected) to turn on bit 3 (0x4 = 0b100) in the `state` word in the old `or` (`state |= 4`) instruction.

<br>
<br>

## Enable the kernel explorer
source: https://github.com/aldostools/webMAN-MOD/discussions/519  
`8000000000003B38` with instructions: `386000014E800020`

<br>
<br>

## WebMAN shortcuts in `boot_init.txt`
```
/poke.lv2?284218=60000007
/poke.lv2?284118=48000030

/poke.lv2?3B38=386000014E800020
```
