# F# Mutable Variable Scope Issue

This example demonstrates a common error in F# when dealing with mutable variables within functions.  The `swap` function attempts to swap the values of `x` and `y`, but it fails because it operates on copies of the variables, not the original variables themselves.

## Bug Description:

The `swap` function is intended to swap the values of two mutable variables. However, due to how F# handles function parameters and mutability, it doesn't modify the original variables. The values of `x` and `y` remain unchanged after the call to `swap`.

## Solution:

The solution involves passing mutable variables by reference.  This is accomplished using the `&` operator to pass pointers to the variables' memory locations.