---
layout: page
title: NinCompression
description: File compressor written from scratch in Python, with RLE, Huffman, and LZ77
importance: 3
summary: A file compressor written from scratch in Python, with RLE, Huffman, and LZ77 coders, a checksummed file format, a command-line tool, and a React web UI.
tech:
  - Python
  - Huffman Coding
  - LZ77
  - React
  - Vite
---

**Python, Huffman Coding, LZ77, React, Vite** · [Source on GitHub](https://github.com/nithin-sai-ega/NinCompression)

- Implemented four compression algorithms from scratch with no compression libraries: run-length encoding, Huffman coding, LZ77 with a sliding window, and LZ77 followed by Huffman coding.
- Sped up LZ77 match finding with a hash table keyed on three-byte prefixes, with five compression levels that trade speed for ratio; 100 KB of text compresses in about 0.3 seconds.
- Designed the `.nin` file format with a CRC-32 checksum, so damaged or truncated files are rejected with a clear error.
- Added an auto mode that tries every algorithm and keeps the smallest result, falling back to storing the data when nothing helps.
- Built a command-line tool, a standard-library HTTP server, and a React and Vite web interface that share the same code.
- Wrote 65 unit tests covering randomized round trips, corrupt and truncated input, the command line, and the server, and a benchmark script that compares the algorithms against zlib as a yardstick.
