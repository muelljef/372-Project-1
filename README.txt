/******  For chatserve in python    ******/
#### SETUP && COMPILE ####

# First compile the chatclient program
gcc -o chatclient chatclient.c

# Second ensure both programs can be executed (this step may not be required)
chmod +x chatserve
chmod +x chatclient

#### EXECUTION ####

# First: start the chatserve program with an unused port number
# (replace <port#> with a valid port number like 50222)
./chatserve <port#>

# Second: start the chatclient program from another terminal 
# with the hostname of the chatserve program and the port number
# specified by chatserve
# (e.g. ./chatclient flip2 50222)
./chatclient <server-hostname> <port#>


#### CONTROL ####

## To Send Messages
# chatclient will initiate the connection and send the first message
# then chatserve will be able to send a return message and the two
# program will continue to alternate sending messages back and forth

## To Quit
# to quit the current connection either chatserve or chatclient can
# enter \quit into the message prompt and the connection will be closed
# chatclient will exit and the program will be closed
# chatserve will continue to run and listen for connections

## Close chatclient
# Send SIGINT (Ctrl + C) to the chatserve program, it will close the 
# socket and exit the program

## To Restablish
# If chatserve is still running just run step 2 from EXECUTION
# and if not run both steps from EXECUTION
