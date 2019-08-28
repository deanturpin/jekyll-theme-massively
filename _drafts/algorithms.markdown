---
layout: post
title: Software problem categories
---

# Flood fill

- Search a 2 dimensional space
- Perform some operation
- Define exit criterion

# Valley problem
<!--kg-card-begin: code-->

    int countingValleys(int n, string s) {
    
      int altitude = 0;
      bool started_descent = false;
      int valleys = 0;
    
      for (auto c : s){
    
        // Update altiude
        if (c == 'U')
          ++altitude;
        else if (c == 'D')
          --altitude;
    
        // Check if we've started out descent
        if (!started_descent && altitude < 0) {
          started_descent = true;
        } else 
          if (started_descent && altitude == 0) {
            ++valleys;
            started_descent = false;
          }
      }
    
      return valleys;
    }

<!--kg-card-end: code-->
# Travelling salesman

TBD

# Hashing problem

Creating the hash is O(k)

# Password cracking

All permutations

## 3 digits (0 to 9)

10^3

## 4 characters (a to z)

26^4

## Iterate over a subset of a list - filling jars
<!--kg-card-begin: code-->

    // Complete the solve function below.
    int solve(int n, vector<vector<int>> operations) {
    
      // O(n)
    
      // Create jars
      std::vector<int> jars(n);
    
      for (auto op : operations)
        for (int i = op.at(0) - 1; i < op.at(1); ++i)
          jars[i] += op.at(2);
      
      return std::floor(std::accumulate(jars.begin(), jars.end(), 0) / jars.size());
    }

<!--kg-card-end: code-->