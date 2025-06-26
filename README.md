# SIC/XE Emulator

## Overview

This project is a complete emulator for the **SIC/XE (Simplified Instructional Computer - Extended)** architecture. The emulator simulates the assembly process by performing **both Pass 1 and Pass 2** of the assembler and generating standard **HTME records** for SIC/XE programs.

---

## Features

- ✅ Reads a SIC/XE assembly source file
- ✅ Removes comments and line numbers to produce a clean intermediate file
- ✅ **Pass 1**: Calculates location counters and generates the symbol table
- ✅ **Pass 2**: Generates object code and HTME records
- ✅ Produces clear, structured output files for each stage

---

## File Structure

| File              | Description                                                |
|-------------------|------------------------------------------------------------|
| `in.txt`          | Input SIC/XE assembly program (with line numbers & comments) **Note: Comments should start with a `.` for correct processing** |
| `intermediate.txt`| Clean assembly code (comments and line numbers removed)    |
| `out_pass1.txt`   | Location counter for each line (result of Pass 1)          |
| `symbTable.txt`   | Generated symbol table (Pass 1 output)                     |
| `out_pass2.txt`   | Object code for each line (result of Pass 2)               |
| `HTME.txt`        | Final object code in standard HTME format                  |

---

## How It Works

### 1. Input File Preparation

- Provide your SIC/XE assembly program in `in.txt`.
- Each line may contain:
  - A line number (optional)
  - Assembly instruction
  - Comments (must start with a `.` to be properly ignored)

---

### 2. Intermediate File Generation

- The program reads `in.txt`.
- Removes:
  - Line numbers
  - Comments
- The cleaned assembly code is saved as `intermediate.txt`.

---

### 3. Pass 1 - Location Counter & Symbol Table

- Reads `intermediate.txt`.
- Calculates the location counter for each line.
- Builds the symbol table with labels and their corresponding addresses.
- Outputs:
  - `out_pass1.txt`: Location counters
  - `symbTable.txt`: Symbol table

---

### 4. Pass 2 - Object Code & HTME Records

- Reads `intermediate.txt`.
- Generates:
  - Object code for each line
  - HTME records following SIC/XE conventions
- Outputs:
  - `out_pass2.txt`: Object code
  - `HTME.txt`: Final HTME records

---

## Notes

⚠️ **Important:**  
- Comments in `in.txt` **must start with a `.`** for the emulator to properly exclude them during processing.
- Ensure your assembly code follows SIC/XE standards for accurate results.

---

## Example Run

1. Place your assembly program in `in.txt`.
2. Run the emulator.
3. Review the generated files:
   - `intermediate.txt`
   - `out_pass1.txt`
   - `symbTable.txt`
   - `out_pass2.txt`
   - `HTME.txt`

---

## Requirements

- Standard C++ / Python (depending on your implementation)
- Basic understanding of SIC/XE assembly

---

## Conclusion

This emulator provides a straightforward, educational tool to understand and visualize the assembly process for SIC/XE architecture, from raw assembly code to final HTME output.
