# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by improperly managing dependencies.

The `bug.js` file contains the erroneous code.  The `bugSolution.js` provides the corrected implementation.

## Problem

The `useEffect` hook is designed to perform side effects based on changes to specified dependencies.  In the example, the dependency array `[count]` is incorrectly used, leading to an infinite loop.  Each time `count` is updated, `useEffect` reruns, updating `count` again, and the cycle repeats.

## Solution

The solution involves a careful examination of the dependencies.  To prevent the infinite loop, either remove the dependency array entirely (if the effect should run only once after mount) or use a different dependency that reflects the conditions under which the effect needs to run. For example, if this effect only needs to run once after mount and the count is not needed, then you remove dependency array entirely.