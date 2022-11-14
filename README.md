# Primes
List of primes, for more ressources : [https://primes.utm.edu/](https://primes.utm.edu/)

Source: [https://primes.utm.edu/lists/small/millions/](https://primes.utm.edu/lists/small/millions/)

# Shell 
``` Shell
curl -OL https://www.utm.edu/~caldwell/primes/millions/primes[1-50].zip
find -maxdepth 1 -type f -name 'primes*.zip' -exec unzip {} \;
for each in primes*.txt ; do awk 'NR>2 { for (i=1; i<=NF; i+=1) if ($i ~ /[0-9]+/ ) print($i) }' $each ; done | sort -h > primes.txt
```
