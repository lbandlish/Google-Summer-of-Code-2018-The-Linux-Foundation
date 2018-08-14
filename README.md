# Enhancements for ipptool - Google Summer of Code 2018

This repository contains the code for the project - Enhancements for ipptool under __The Linux Foundation__.

## The Technology
### [IPP](https://en.wikipedia.org/wiki/Internet_Printing_Protocol)
The Internet Printing Protocol (IPP) is an Internet protocol for communication between computers and printers (or print server). It allows programs to send one or more print jobs to the printer or print server and perform administration such as querying the status of a printer, obtaining the status of print jobs, or cancelling individual print jobs.

Like all IP-based protocols, IPP can run locally or over the Internet. Unlike other printing protocols, IPP also supports access control, authentication, and encryption, making it a much more capable and secure printing mechanism than older ones.

### Ipptool
Ipptool is a program that sends IPP requests to  the  specified printer-uri and tests and/or displays the results.
Each named testfile defines one  or  more requests,  including the expected response status, attributes, and values.
Output is either a plain text, formatted text, CSV, or XML report on the standard output, with a non-zero exit status indicating that one or more tests have failed.

### Ipptoolfile (testfile)
An ipptoolfile is a file that satisfies a predefined syntax and contains all information to be included in a request to be issued to a printer by ipptool.
Apart from that, it also includes information to be expected in a response from the printer.

## My work

Pull Request for my code into the ippsample repository:
https://github.com/istopwg/ippsample/pull/159


My work was to write ipptoolfiles that could check whether a printer satisifies particular IPP standards.
Printer Manufacturers could use these files to check IPP-conformance for their printers and identify the reasons for non-conformance, if any.
I had to write testfiles for the following standards:

IPP Standard | Description
------------ | -------------
RFC 3995 | IPP Event Notifications and Subscription
RFC 3996 | The 'ippget' Delivery Method for Event Notifications
PWG 5100.9-2009 | IPP Printer State Extensions
PWG 5100.7-2003 | IPP Job Extensions
PWG 5100.1-2017 | IPP Finishings 2.1 (FIN)
PWG 5100.6-2003 | IPP Page Overrides
PWG 5100.5-2003 | IPP Document Object
PWG 5100.3-2001 | Production Printing Attributes – Set1
PWG 5100.11-2010 | IPP: Job and Printer Extensions - Set 2 (JPS2)
PWG 5100.13-2012 | IPP: Job and Printer Extensions – Set 3 (JPS3)


### Ippfuzz
Apart from the above, I worked on ippfuzz: Fuzz test generator for ipptool.
This was a different program wholetogether, its motive was to [fuzz-test](https://en.wikipedia.org/wiki/Fuzzing) IPP-enabled printers to find anomalies.
I looked at many implementations of fuzz-testing to understand this concept and to devise a strategy to do this task.
I studied the [AFL](http://lcamtuf.coredump.cx/afl/) (American Fuzzy Lop) in detail, testing its implementation on simple C files.
I am still working on ippfuzz at the moment.



## Work to be done:

* Complete testfile for PWG 5100.13-2012 | IPP: Job and Printer Extensions – Set 3 (JPS3)
* Write code for Ippfuzz.

## Acknowledgements
I would like to thank Mr. Michael Sweet, who wasn't officially my mentor, but the go-to person for all my queries and progress evaluation. Without him, none of the work I did would have been possible. I would also like to thank my mentors Danny, Aveek, Ira, and Smith. Thank you Danny for having those weekly meetings with me and Akash, and helping us clarify our respective doubts. Thank you Aveek for always being there whenever I faced any kind of problem and helping me throughout this time.

## Conclusion
Google Summer of Code 2018 under The Linux Foundation has been a one-of-a-kind experience for me. I worked on something nowhere close to what I had worked on before, and learnt a lot of things along the way. Learning about fuzzing was the best thing about the project. Overall, it was a really great experience.


> _Lakshay Bandlish_.

