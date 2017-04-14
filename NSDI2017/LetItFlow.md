# Let It Flow: Resilient Asymmetric Load Balancing with Flowlet Switching

## problem

asymmetric network condition, A B channel have dynamic capacity. 

How to adjust transmission rate on each channel dynamically?

## Advantage

No need feedback information. Simple

Only based on estimated RTT, to transmit flowlet with different time interval gap. The longer RTT, longer interval gap => less pkt transmission.
