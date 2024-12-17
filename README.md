# Unexpected behavior of calc() with percentages in CSS
This repository demonstrates a common issue encountered when using the `calc()` function in CSS with percentage values.  The problem arises from the order of calculations and the dependency on the parent container's size being determined before the calculation is applied.

## Bug Description
The `calc()` function, while powerful, can produce unexpected results if it relies on the size of a parent element that hasn't been fully rendered yet. Specifically, if a percentage is involved in the calculation, the result might be incorrect unless the parent's size is available.

## Reproduction Steps
1. Clone the repository.
2. Open `index.html` in a web browser.
3. Observe the unexpected width of the inner element. This occurs because `calc(50% - 10px)` is calculated before the parent's width is fully determined.

## Solution
The solution involves ensuring that the parent element's dimensions are fully established before `calc()` is evaluated. This can often be achieved by adjusting the order of CSS rules or by ensuring the parent element's size is explicitly defined before the child's dimensions are computed.