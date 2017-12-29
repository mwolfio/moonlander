
* Login to your raspberry pi with putty

* Update the system software

  $ `sudo apt-get update`

* Install necessary library files

  $ `sudo apt install libjansson-dev libcurl4-openssl-dev`

* create a directory in your home directory for bfgminer

  $ `mkdir miner`

* Move into the new folder with the name 'miner'

  $ `cd miner`

* download the precompiled (ready to run) bfgminer from jstefanop

  $ `wget https://github.com/jstefanop/bfgminer/releases/download/bfgminer-5.4.2-futurebit2/bfgminer_5.4.2-futurebit2_linux_armv6.tar.gz`

* unpack this tar.gz file

  $ `tar xzfv bfgminer_5.4.2-futurebit2_linux_armv6.tar.gz`

* Navigate into the newly unpacked folder

  $ `cd bfgminer_5.4.2-futurebit2_linux_armv6`

(This is the complete bfgminer
including a short startup script from jstefanop)


## Configuration Option 1
* Edit the existing start script

  $ `nano start_moonlander2.sh`

* Change:

  - The Pool
  - The Username (after -u)
  - The Password (after -p)


* Save the file

* Quit the editor

* Try the new startup script

  $ `./start_moonlander2.sh`


## Configuration Option 2

* create a new start script called "startmoonlander.sh"

  (change the pool - the username - the password options as needed)

  $ `echo ./bfgminer --scrypt -o stratum+tcp://us.litecoinpool.org:3333 -u jstefanop.1 -p 1,d=128 -S ALL --set MLD:clock=600 >startmoonlander.sh`

* Make the file executable

  $ `chmod +x startmoonlander.sh`

* Try the new startup script

  $ `./startmoonlander.sh`
