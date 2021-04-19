# buxtax
Automatically fill in Belgian tax form from BUX report.

# usage
```
$ ./buxtax -h
usage: buxtax [-h] [--config CONFIG] [--natnum NATNUM] [--name NAME]
              [--address ADDRESS] [--output OUTPUT] [--signature SIGNATURE]
              [--location LOCATION] [--date DATE]
              input

BUX Belgian tax report converter

positional arguments:
  input                 BUX tax report (pdf)

optional arguments:
  -h, --help            show this help message and exit
  --config CONFIG, -c CONFIG
                        Config file
  --natnum NATNUM, -i NATNUM
                        National number
  --name NAME, -n NAME  Full name
  --address ADDRESS, -a ADDRESS
                        Address lines
  --output OUTPUT, -o OUTPUT
                        Output file (pdf)
  --signature SIGNATURE, -s SIGNATURE
                        Image to sign form (square image)
  --location LOCATION, -l LOCATION
                        Location
  --date DATE, -d DATE  Date
```

Default values:
* config: buxtax.json
* output: tob_`year`_`month`.pdf
* location: Last word from last address line
* date: Current day

All other arguments are required, either as command line argument or as a configuration entry.

# requirements
Requires python3 and the following modules:
```
pip install PyPDF2
pip install reportlab
pip install segno
```

Additionally, it will use `pdftotext` from the `poppler-utils` package.
