Building cpuminer on Linux
--------------------------

Install the required dependencies

$ sudo apt-get install autoconf libjansson-dev libcurl4-openssl-dev

Run the installation

$ ./autogen

$ ./configure CFLAGS="-O1"

$ make install

If you want to optimise for speed, you can use

$ ./autogen

$ ./configure CFLAGS="-O3 -march=native"

$ sudo make install
