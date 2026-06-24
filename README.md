from Bio import SeqIO         #working code

# Read FASTA file
record = SeqIO.read("zebra_sequnce.fasta.txt", "fasta")

# Extract sequence
seq = record.seq

# Basic information
print("ID:", record.id)
print("Length:", len(seq))

# Nucleotide counts
A = seq.count("A")
T = seq.count("T")
G = seq.count("G")
C = seq.count("C")

print("A:", A)
print("T:", T)
print("G:", G)
print("C:", C)

# GC Content
gc = (G + C) / len(seq) * 100
print("GC Content:", round(gc, 2), "%")

# First and last 50 bases
print("\nFirst 50 Bases:")
print(seq[:50])

print("\nLast 50 Bases:")
print(seq[-50:])

# Reverse Complement
print("\nReverse Complement (First 100 Bases):")
print(seq.reverse_complement()[:100])

# Translation
trimmed_seq = seq[:len(seq) - (len(seq) % 3)]
protein = trimmed_seq.translate()

print("\nProtein Translation (First 100 Amino Acids):")
print(protein[:100])

# Protein length
print("\nProtein Length:", len(protein))
