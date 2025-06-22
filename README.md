# 🧠 Synchronous FIFO using Verilog

This repository implements a **Synchronous FIFO (First In First Out) buffer** using Verilog HDL.  
A FIFO is a commonly used memory structure that **buffers data**, **synchronizes flow**, and **preserves input order**, making it essential in digital systems such as data communication, pipelining, and real-time processing.

---

## 📋 Description

This FIFO design operates under a **single clock domain** (synchronous), using the same clock for both **read and write operations**. The FIFO supports:

- ✅ Write operations when `wr_en` is high and FIFO is not full
- ✅ Read operations when `rd_en` is high and FIFO is not empty

The **waveform** demonstrates the expected FIFO behavior:

> ➤ Initially `empty` → data written sequentially → FIFO becomes `full` → data read out → FIFO returns to `empty`

---

## ⚙️ Core Functionality

- **Write Operation**:
  - Data is written when `wr_en = 1` and `full = 0`
  - Write pointer (`wr_ptr`) increments on successful write

- **Read Operation**:
  - Data is read when `rd_en = 1` and `empty = 0`
  - Read pointer (`rd_ptr`) increments on successful read

---

## 🧠 Full & Empty Logic

- **Empty Condition**:
  ```verilog
  empty = (wr_ptr == rd_ptr); // MSB and LSB both equal
