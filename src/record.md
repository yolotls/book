# Record

Record layer provides both the parsing and building of TLS record layer.

Instead of using allocating types we use "worst case" heapless static arrays that get initialized to the needed point upon building.

This means that if the configured size of the worst case is lower than what for example other end provides may result into error.

To ensure records are not overflown we can use maximum record size to tell the other side what is the maximum used record size what we use.

Builder uses callbacks to fill the data during encoding and parsing also uses callbacks to extract the required information for the downstream layer typiclaly.
