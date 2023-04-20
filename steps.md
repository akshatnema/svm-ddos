## Steps to start the project

1. First terminal in network/controller directory.
2. in first,
    ```
   ryu-manager --ofp-tcp-listen-port 6653 c1.py
    ```
3. Second terminal as same as first one.
    ```ryu-manager --ofp-tcp-listen-port 6633 c2.py ofctl_rest.py``` 
4. Third terminal in network/topologies directory
    ```sudo mn --custom mn_ddos_topology.py --controller=remote,ip=192.168.181.151:6653 --controller=remote,ip=192.168.181.151:6633 --topo ddostopo```
    where `192.168.181.151` is the ip of the computer
    Third terminal is now mininet terminal
5. In mininet,
   `xterm h1`, `xterm h2` and `h_target wireshark &`
6. To generate bash traffic, in fourth terminal (network/topologies)
    `sudo bash gen_traffic.sh 137.204.10.100`