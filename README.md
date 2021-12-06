# PSD
Pulse Shape Discrimination on Red Pitaya
========================================

This repository incude C/C++ files source for implementing Pulse Shape Discrimination (PSD) on a Rd Pitaya 125-15 board.
The code uses JsonCPP package, what should be initially installed.
A batch file, install_jsoncpp.sh, include the instruction to install this package.
Building the PSD application is with simple make command. It generates an executable called psd.
That application assumes positive nuclear pulses are sampled in RF Input #1, at 125 M Hz, without decimition (e.g. Decimation = 1).
There are few command line option to the psd program. One may get those options by entering
./psd -h
The result is:

Red Pitaya PSD Analyzer
Synopsis:
./psd -h -i <iterations> -l <long> -n <samples> -p <output PSD> -r <output raw>
        -s <short length> -t <trigger level> -w <raw pulses to save>
Where                                   | Defaults
    f - Option File in JSON format.     | default: 'psd_params.json'
    h - help                            | false
    i - iterations (-1 == inf)          | 1,000
    j - input json parameters           | psd_params.json
    l - long persiod [nSec]             | 999.999997
    n - samples (buffer length)         | 1,000
    p - output psd results              | psd_results.csv
    r - output raw name                 | signals.csv
    s - short period [nSec]             | 999.999997
    t - trigger levet                   | 0.005000
    w - raw pulses to save              | 10
    v - Input Voltage                   | 0.000000
    T - Input Tau                       | 0.000000

The directory rfin includes the Red Pitaya C example program, that can also be found here:
https://redpitaya.readthedocs.io/en/latest/appsFeatures/examples/acqRF-exm1.html
