# Install dhcpcanon

## Installation in Debian/Ubuntu from source code

### Install system dependencies
    sudo apt-get install python-dev

### With virtualenv

#### Obtain virtualenv
Check https://virtualenv.pypa.io/en/latest/installation.html or
if Debian equal/newer than Jessie (virtualenv version equal or greater than 1.9)

    sudo apt-get install python-virtualenv

#### Create a virtual environment
    mkdir ~/.virtualenvs
    virtualenv ~/.virtualenvs/dhcpcanonenv
    source ~/.virtualenvs/dhcpcanonenv/bin/activate

#### Install dependencies in virtualenv
    git clone https://github.com/juga0/dhcpcanon
    cd dhcpcanon
    pip install -r requirements.txt
or run:
    python setup.py install

## Running

    dhcpca.py [-h] [-d] [-l LEASE] [-v] [interface]

positional arguments:
  interface             interface to configure with DHCP

optional arguments:
  -h, --help            show this help message and exit
  -d, --debug           debug
  -l LEASE, --lease     custom lease time
  -v, --version         version

To run as a non privileged user, run scripts/setup_noroot.sh, and run dhcpcanon:
    python bin/dhcpca.py