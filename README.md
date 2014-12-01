4-way-set-associative-phased-cache-verilog
===================================

Verilog implementation of a 4-way Set associative phased cache with a write buffer (write) policy and FIFO replacement policy

A multicycle datapath design has been for the implementing the above mentioned cache.
There are 4 states in total (0,1,2 and 3) and transition between the states is done in the CtrlCkt module.

State 0 - tag comparison to determine cache hit or cache miss

State 1 - Read from the cache and/or write to the write buffer

State 2 - Fetch approprite block of data from memeory to the cache (Replace if needed)

State 3 - Write a byte to the cache (from the CPU)


Read hit takes 2 cycles   (0-1)

Read miss takes 3 cycles  (0-2-1)

Write hit takes 3 cycles  (0-3-1)

Write miss takes 4 cycles (0-2-3-1)

One extra cycle is resulting in each of the above hit/miss conditions because of a requirement of a minimum of 2 cycles for a phased cache. Phased cache poses the condition that read should happen only if and after cache hit/miss has been determined.
