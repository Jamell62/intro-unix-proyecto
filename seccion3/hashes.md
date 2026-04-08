# Comparative table of hashes and Hashcat results

+--------------------------+------------------------------------------+-------------------------------------------------+
| Parameter                | Case 1: Low Entropy                      | Case 2: High Entropy                            |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Original Password        | 12345678                                 | t2Ua2^6d$TlzWuI                                 |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Hash Algorithm           | MD5                                      | MD5                                             |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Character Type           | Numeric (0–9)                            | Alphanumeric + Symbols                          |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Estimated Entropy        | ~25 bits                                 | ~50 bits                                        |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Attack Method            | Dictionary (rockyou.txt)                 | Brute Force (?a x14)                            |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Execution Environment    | Debian VM (no GPU acceleration)          | Debian VM (no GPU acceleration)                 |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Hashcat Result           | Failed (timeout / freeze)                | Failed (infeasible)                             |
+--------------------------+------------------------------------------+-------------------------------------------------+
| Failure Reason           | Limited VM resources                     | Huge keyspace (94^14), CPU-only                 |
+--------------------------+------------------------------------------+-------------------------------------------------+


# Analysis of Results

Hardware Limitations
This exercise clearly shows that even though the MD5 algorithm is considered weak and vulnerable, the lack of GPU passthrough in a virtual machine greatly reduces performance. In this case, the number of hashes processed per second (H/s) was very low, which directly affected the results. Because of this limitation, even a simple dictionary attack could not be completed and ended up failing due to timeouts or system freezes.

Impact of Entropy
The difference between the two cases is significant and grows exponentially. In the first case, the failure was mainly due to technical limitations of the environment. However, in the second case, the situation is very different: the password is much longer and uses a wide variety of characters, which creates an extremely large number of possible combinations. This makes a brute-force attack practically impossible with standard hardware, as it would take an unrealistic amount of time (potentially centuries).

Importance of the Dictionary
The use of rockyou.txt is very common in penetration testing because it contains millions of previously leaked passwords. However, its effectiveness depends entirely on whether the target password is included in that dataset. In this experiment, even though the password 12345678 is very common, the system limitations prevented the attack from completing, showing that both the quality of the dictionary and the available hardware play a crucial role in the success of password cracking.
