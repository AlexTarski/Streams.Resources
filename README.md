# Streams.Resources


Custom stream realization, which reads the content of the small file from the big one.

For example, the custom streams constructor takes a basic stream with a big file and the name of the small file.

Read from the custom stream returns the content of the small file.



The big file consists of sequential sections. Each section consists of the name of the small file (Key) in ASCII

and the content of the small file (Value) represented by random bytes.

Each Key and Value (even Value of the last section) should end with Separators: sequential 0 and 1 bytes.

Small files can contain sequences of 0 and 1 bytes inside. To make a difference between such sequences

and Separators each zero bytes in Key and Value are represented by doubled zeroes.



Additionally, bufferization of the stream is implemented (read from the basic stream by parts of 1024 bytes each).