# Slow Internet because of all the devices connected to your same network?

## Solution : Evil Limiter

A tool to limit and monitor the bandwidth (upload/download) of devices connected to your network without physical or administrative access.
evillimiter employs ARP spoofing and traffic shaping to throttle the bandwidth of hosts on the network.  

Repo Link :https://github.com/bitbrute/evillimiter  

### How to install

    git clone https://github.com/bitbrute/evillimiter.git  
    cd evillimiter  
    sudo python3 setup.py install
  
### How to use?
  * open terminal and enter _evillimiter_
  * ? to display help
  * scan for devices  
    scan
    
  * Now enter hosts to view connected devices
    hosts
  
  * Now Select the host or hosts you wanna limit using their number and enter following command  
      limit id1,id2 100kbit or 1mbit or limit all 100kbit
      eg: limit 1,2,3 100kbit
## thats it
