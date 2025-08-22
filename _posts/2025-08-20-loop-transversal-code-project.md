---
layout: post
title: "Project Overview: Loop Transversal Code"
date: 2025-08-20 10:00:00 +0800
categories: [Projects, Coding Theory]
tags: [python, error-correction, algorithms]
description: "An overview of the Loop Transversal Code project, a Master's thesis project for constructing and analyzing syndrome maps in greedy loop transversal codes."
---
As part of my Master's thesis, I developed the "Loop Transversal Code" project, which provides tools for constructing and analyzing syndrome maps in greedy loop transversal codes.

## Online Demo

An interactive web-based version of the tool is available. Use it to explore syndrome mappings and parity check matrices directly in your browser:

👉 **[Loop Transversal Code Explorer](https://jcleealg.github.io/loop-transversal-code/)**

## Project Overview

Traditional error-correcting codes are designed first, then analyzed to determine which errors they can correct. In contrast, the Loop Transversal Code method starts with a list of errors you want to fix and uses a greedy algorithm to build a custom code tailored to that list. This project demonstrates the greedy construction process and provides CLI tools for exploring syndrome mappings and parity check matrices.

### Reference

This project is based on my Master's thesis, which can be found here:
- [Loop Transversal Code (NCKU Thesis Library)](https://thesis.lib.ncku.edu.tw/thesis/detail/4759066580a6172d56505500348dae66/)

## Main Features

The command-line interface supports several key features:
- `full-syndrome-mapping`: Display syndrome mappings for all error patterns.
- `basis-mapping`: Display syndrome mappings for basis vectors.
- `parity-check-matrix`: Output the parity check matrix.
- `all-mapping`: Run all three features in sequence.

## Installation

To run the project locally, install the required dependencies:
```bash
pip install -r requirements.txt
```

## Example Usage

Here are a few examples of how to use the CLI:

```powershell
# Example 1: Simple basis
python main.py all-mapping --error-patterns "[[1,0,0],[0,1,0],[0,0,1]]"

# Example 2: Custom error patterns
python main.py all-mapping --error-patterns "[[0,0,0,0,0,1],[0,0,0,0,1,0],[0,0,0,0,1,1],[0,0,0,1,0,0],[0,0,0,1,1,0],[0,0,1,0,0,0],[0,0,1,1,0,0],[0,1,0,0,0,0],[0,1,1,0,0,0],[1,0,0,0,0,0],[1,1,0,0,0,0]]"

# Example 3: Standard basis
python main.py parity-check-matrix --standard-basis 3
```

## Testing

To run all tests and verify the core logic, use `pytest`:
```bash
pytest
```
