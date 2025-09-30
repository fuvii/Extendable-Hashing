Extendable Hashing

Reference: IBM Research Paper, October 2022

Overview

This project implements extendable hashing, a dynamic hashing technique designed to efficiently handle growing datasets. It uses a directory tree to manage data inserts and lookups, dynamically expanding the structure as needed to maintain high performance.

Features

Dynamic Inserts: Automatically splits buckets when overflow occurs.

Fast Lookups: Achieves near-constant-time searches even as the dataset grows.

High Performance:

Search operations up to 2.65× faster than traditional hashing.

Insert operations up to 4.41× faster than traditional hashing.

How It Works

Hashing: Data items are hashed to determine the target bucket.

Directory Tree: A directory points to buckets. Each directory entry corresponds to a hash prefix.

Bucket Splits: When a bucket overflows, it is split, and the directory is updated to reflect the new structure.

Dynamic Growth: Only the necessary portion of the directory grows, keeping memory usage efficient.

Example Directory Tree Structure (textual representation):

Directory (global depth = 2)
--------------------------------
00 -> Bucket A
01 -> Bucket B
10 -> Bucket C
11 -> Bucket D


If Bucket B overflows, it splits and the directory updates:

Directory (global depth = 3)
--------------------------------
000 -> Bucket B1
001 -> Bucket B2
00  -> Bucket A
10  -> Bucket C
11  -> Bucket D

Usage

Clone the repository:

git clone <repository_url>
cd extendable-hashing


Build and Run:
Adjust based on your implementation language:

# Example for Python
python main.py

# Example for C++
g++ -o extendable_hash main.cpp
./extendable_hash


Perform Operations:

Insert new keys

Search for keys

Observe bucket splits and directory expansion

Performance
Operation	Speedup vs Traditional Hashing
Search	2.65×
Insert	4.41×
