---
layout: post
title:  "Optimization and Linear Programming"
author: "Carter Lockwood"
date:  2020-10-19
categories: school excel om500 management optimization
---
## **Optimization, Linear Programming, and Integer Programming**
This post is basically just a notes page to help myself better understand the aforementioned topics. 

Typical objectives of optimization:
- maximize profit
- minimize cost
- reduce risk, etc

An optimization model has three parts: **the target cells, the changing cells, and the constraints**. The target cell represents the objective or goal. You want to either minimize or maximize the quantity in the target cell.

Changing cells are the worksheet cells that you can change or adjust to optimize the target cell.Constraints are limits imposed on the changing cells.

### The Optimal Product Mix Problem
Companies frequently need to determine hte quantity of each product to produce on a monthly basis. How much of each do we produce to maximize profits. 

Usually this is subject to these constraints:
- Product mix can't use more resources than are available
- There is a limited demand for each product. You don't wanna make more of a product during a month than demand dictates because the exces production is wasted.

**Use SUMPRODUCT**
Sp uses corresponding values in cell ranges and returns the sum of those values. Each cell range used in a SP evaluation must have the same dimensions.

## Temporary Break