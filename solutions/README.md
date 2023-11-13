# Intro to Go Lab 2 - Solutions

## Question 1a

3 messages are sent and recieved. 

## Question 1b

The frist 2 messages have been sent and recieved, and although you can see the line `sendMessage is sending: pinggg` that message is not in fact sent, this is because `main()` exits, meaning there is no corresponding recieve operation for the third messsage and it is lost.

## Question 1c

The Go language runtime reports a deadlock as `sendMessages()` has terminated, and there is no other goroutine that can send a 4th message, resutling in `main()` being stuck attemtping to recieve a 4th message. 

## Question 1d

The two go routines no longer need to sync on send/recieve, so we see the lines indicating that `sendMessages()` has immidiately sent and queued the 3 messages on the buffer, and that `main()` reads the messages sequentially 1s apart. 

## Question 2a

See `ping.go`

## Question 2b

See `ping.go`

## Question 2c

In the outputed trace, our running goroutines are shown as non overlapping diferent coloured blocks with arrows representing the messages that are being passed between them, illustrating how the messages "ping-pong", and how the functions `foo()` and `bar` are blocking.

We can occasionally see that `foo()` or `bar()` take much longer than average, showcasing when another process is scheduled by the OS and our program is paused, this highlights the importance of minimisig the number of processes running on our machine when conducting benchmarking or tracing so as to ensure accuracy. 


