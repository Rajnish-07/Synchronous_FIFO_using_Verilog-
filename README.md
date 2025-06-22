# Synchronous_FIFO_using_Verilog-
FIFO buffers data, synchronizes and preserves order. This synchronous FIFO uses the same clock for read and write. Data is written when wr_en is high and not full; read when rd_en is high and not empty. Empty: wr_ptr == rd_ptr with same MSB. Full: wr_ptr == rd_ptr with different MSB. The waveform shows correct FIFO operation: empty → full → empty.
