## Error Detection
> Two dimensional parity

- One parity bit for every 7 bits
- 14 redundant bits for 42 bit message

![[Pasted image 20231004142942.png]]

> Checksum


![[Pasted image 20231004145147.png]]

>Cyclic Redundancy Check

`M(x)/ C(x) = Q(X)`

M(x) = C(x) + Q(x) + R(x)


## Reliable Transmission

> Stop and wait

- Sender waits until it receives the corresponding acknowledgement from receiver
- 4 possible scenarios (see slides)

> Sliding window

- improves data link usage by allowing transmition of more frames, even if not all frames were acknowledged 