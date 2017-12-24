Luminor
=============

A simple library that changes the brightness, contrast, and gamma value of on-memory images in real time

Summary
-------

- A simple C/C++ language API
- Optimized processing automatically generated with Halide language
- It consists of C ++ source code and runtime static library

Binary Releases
---------------
https://github.com/kanryu/luminor/releases


API
---

int luminor(struct halide_buffer_t *_input_buffer, float _brightness, float _contrast, float _gamma, struct halide_buffer_t *_output_buffer) HALIDE_FUNCTION_ATTRS;

- _input_buffer
    - input bitmap of rgb24 or gray8
- _brighness
    - Add the value to each pixel
    - default: 0.0, min: -128.8, max: 127.0
- _contrast
    - Multiply each pixel by the value(the base value is 0.5(128))
    - default: 1.0, min: 0.01, max: 10.0
- _gamma
    - Change the gamma value of each pixel
    - It gets brighter when it gets bigger, it gets darker when it gets smaller
    - default: 1.0, min: 0.01, max: 10.0
- _input_buffer
    - output bitmap, the same pixel format as _input_buffer


How to build
------------

  $ make

License
-------
MIT

Author
------

Copyright (c) 2017, KATO Kanryu