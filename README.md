# Go Race Condition in Concurrent Slice Append

This repository demonstrates a race condition in a Go program that concurrently appends numbers to a slice.  The program uses goroutines and a mutex to protect the slice, but the mutex is not correctly used, leading to unpredictable results.

## Problem

The issue lies in the way the `data` slice is accessed and modified by multiple goroutines.  Without proper synchronization, multiple goroutines may attempt to modify the slice simultaneously, resulting in data corruption and an incorrect final slice length.

## Solution

The solution involves correctly using the `sync.Mutex` to protect access to the `data` slice.  This ensures that only one goroutine can modify the slice at a time, preventing data races and producing the expected result.
