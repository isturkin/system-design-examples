# Task definition

Create URL shortener service which converts long url addresses into short ones.

**Writes Load**: 100 000 000 addresses per day / 24 hours / 3600 sec = 1160 RPS \
**Reads Load**: 1160 * 10 = 11600 RPS (if there are 10 times more reads than writes)

If we would like to store records during 10 years then we need to store 100 millions * 365 * 10 records = 365 TB

# Intermediate thoughts

We see that there is a huge amount of data.
Will we use sharding technique? What about hot nodes?

Define the hash value space - we should generate only unique hash values or implement some conflict resolution mechanism.

# Hashing function

base62 vs sha-1 vs md5?