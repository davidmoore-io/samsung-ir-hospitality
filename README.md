# Samsung HG65NT678UF Hilton Dulles TV

https://github.com/jamisonderek/flipper-zero-tutorials/wiki
https://github.com/jamisonderek/flipper-zero-tutorials/wiki/Infrared

## Notes

I discovered that the power button is completely unreadable by the flipper, even
inb RAW mode.

The power button in the IRDB file `lodgenet_Irc3220.ir` does turn the TV on/off
however.

Remote3.ir

quac files: `apps_data/quac/Samsung_HG65NT678UF/`


### Hilton raw button comparison

- "1" button raw signal:

```
Filetype: IR signals file
Version: 1
# 
name: RAW_71
type: raw
frequency: 38000
duty_cycle: 0.330000
data: 8917 4461 563 1664 565 549 564 1665 564 549 564 549 565 549 564 549 564 1666 563 550 563 550 563 1665 564 1665 564 1664 565 1665 564 1665 564 550 563 1665 564 1665 564 548 565 550 563 549 564 549 564 549 564 1665 564 548 565 550 563 1664 565 1665 564 1665 564 1664 565 1665 564 550 564 39621 8947 2221 564
```

- "power" button raw signal:

```
Filetype: IR signals file
Version: 1
# 
name: RAW_75
type: raw
frequency: 38000
duty_cycle: 0.330000
data: 8920 4460 536 1694 535 576 537 1692 537 577 536 574 539 577 536 576 537 1692 537 577 536 577 536 1694 535 1692 537 1693 536 1694 535 1693 536 577 537 575 538 575 538 577 536 577 536 576 537 576 537 576 537 1692 537 1692 537 1692 537 1692 537 1692 537 1692 537 1692 537 1692 537 576 537 39647 8920 2249 537 95349 8920 2249 538
```


## Mute

A: 0x7c85
C: 0x6897

### remote.ir file

```
Filetype: IR signals file
Version: 1
# 
name: mute
type: parsed
protocol: NECext
address: 85 7C 00 00
command: 97 68 00 00
```

## Power

A: 0x7c85
C: 0x7f80

### remote.ir file

```
Filetype: IR signals file
Version: 1
# 
name: power
type: parsed
protocol: NECext
address: 85 7C 00 00
command: 80 7F 00 00
```

## remote inspection

order:    8C 73 00 00
menu:     90 6F 00 00
up:       98 67 00 00
down:     99 66 00 00
left:     9B 64 00 00
right:    9A 65 00 00
select:   95 6A 00 00
back:     9D 62 00 00
info:     A4 5B 00 00
exit:     9C 63 00 00
guide:    A2 5D 00 00
help:     A3 5C 00 00
rewind:   9E 61 00 00
pause:    9F 60 00 00
play:     A1 5E 00 00
forward:  A0 5F 00 00
prev_ch:  96 69 00 00
mute:     97 68 00 00
1:        83 7C 00 00
2:        82 7D 00 00   
3:        81 7E 00 00
4:        87 78 00 00
5:        86 79 00 00
6:        85 7A 00 00
7:        8B 74 00 00
8:        8A 75 00 00
9:        89 76 00 00
0:        8E 71 00 00
cc:       A6 59 00 00
sleep:    A5 5A 00 00
function: 92 6D 00 00

## attempt 1

```
Filetype: IR signals file
Version: 1
#
name: Source
type: parsed
protocol: NECext
address: 85 7C 00 00
command: 4C B3 01 FE
#
```

## extra buttons

Filetype: IR signals file
Version: 1
# 
name: Vol+
type: parsed
protocol: NECext
address: 85 7C 00 00
command: 8F 70 00 00
#
name: Vol-
type: parsed`
protocol: NECext
address: 85 7C 00 00
command: 93 6C 00 00
# 
name: Ch+
type: parsed
protocol: NECext
address: 85 7C 00 00
command: 8D 72 00 00
# 
name: Ch-
type: parsed
protocol: NECext
address: 85 7C 00 00
command: 91 6E 00 00
