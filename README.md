# AIM
To simulate Huffman and Shannon-Fano coding and compute average codeword length, entropy, efficiency, redundancy, and variance for a given set of symbol probabilities and codeword lengths.

# SOFTWARE REQUIRED
Python 3.x and any Python IDE or code editor such as VS Code, PyCharm, or Jupyter Notebook.

# ALGORITHMS
1. Input the number of symbols.
2. Enter the probability and codeword length for each symbol.
3. Calculate average codeword length using the formula L = Σ(p[i] * l[i]).
4. Compute entropy using H = Σ(p[i] * log₂(1/p[i])).
5. Determine efficiency as H / L.
6. Calculate redundancy as 1 - efficiency.
7. Compute variance as Σ(p[i] * (l[i] - L)²).
8. Display the results.

# PROGRAM
import math

L = 0
hs = 0
p = []
lk = []

n = int(input("Enter the number of samples: "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample value {i + 1}: "))
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample value {j + 1}: "))
    lk.append(l)

for k in range(n):
    L += p[k] * lk[k]

for k in range(n):
    hs += p[k] * math.log(1 / p[k], 2)
hs = round(hs, 3)

eff = round(hs / L, 3)
red = round(1 - eff, 3)

var = 0
for k in range(n):
    var += p[k] * (lk[k] - L) ** 2
var = round(var, 3)

# OUTPUT
print("\n--- Results ---")
print(f"Average Codeword Length: {round(L, 3)}")
print(f"Entropy: {hs}")
print(f"Efficiency: {eff}")
print(f"Redundancy: {red}")
print(f"Variance: {var}")

# RESULT
The Huffman and Shannon-Fano coding simulation was successfully implemented. The program computed the average codeword length, entropy, efficiency, redundancy, and variance based on the input probabilities and codeword lengths.
