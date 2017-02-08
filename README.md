Fizzer - FIX Fuzzing Framework
===========================================
Original Authors: 

Brian Holyfield - Gotham Digital Science 
Michael Hanchak - Gotham Digital Science 

www.gdssecurity.com
labs@gdssecurity.com

Small changes:
Frans Lategan - Made a few changes to use UTC time, update sequence numbers if that is sent from the server, and get rid of some extra fluff in .pcap files.

Also fixed the logon message that seemed to use incorrect parts.
Other minor changes to make it work better with the specific FIX implementation I came across. YMMV

===========================================
Usage:

    Fizzer.exe <host> <port> <sender-comp-id> <input file> <sequence start> [csv log file]

Input file should be a TCPDump or Wireshark capture of a legitimate FIX conversation in raw format.  Messages will be extracted and used as the base for fuzzing.  The last login request sent to the FIX Receiver will also be extracted.  Messages where the SenderCompId does not match the value from the command line, Logon, and Heartbeat messages will all be ignored.  In addition, the following fields are not fuzzed by default in this release: BeginString(8), BodyLength(9), MsgType(35), MsgSeqNum(34), and CheckSum(10)   

===========================================
License:
 
Fizzer is released under the Reciprocal Public License 1.5 (RPL1.5)
https://opensource.org/licenses/RPL-1.5

===========================================

