# Primes
List of the first 50 millions primes, for more ressources : [https://primes.utm.edu/](https://primes.utm.edu/).

Source: [https://primes.utm.edu/lists/small/millions/](https://primes.utm.edu/lists/small/millions/)

# How to get the curated list ?

These commands has been used on GNU/Linux (Ubuntu).
``` Shell
# Download the 50 archives.
curl -OL https://www.utm.edu/~caldwell/primes/millions/primes[1-50].zip
# Unzip 
find -maxdepth 1 -type f -name 'primes*.zip' -exec unzip {} \;
# Combine every text file in one file with one prime per line.
for each in $(ls -1 primes*.txt| sort -t's' -n -k2) ; do awk 'NR>2 { for (i=1; i<=NF; i+=1) if ($i ~ /[0-9]+/ ) print($i) }' $each ; done > primes.txt
# Check the result file
sha256sum -c SHA256SUM.txt
# Delete temporary files
find -maxdepth 1 -type f \( -name 'primes*.zip' -or -name 'primes??.txt' -or -name 'primes?.txt' \) -delete
```

# Use cases

Solving some math problems from [https://projecteuler.net/](https://projecteuler.net/), has been easier with a precomputed list of primes.

