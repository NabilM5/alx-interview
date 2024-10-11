# Lockboxes Problem

Overview

This project solves the “Lockboxes” problem, where you are given n locked boxes numbered sequentially from 0 to n-1. Each box may contain keys to unlock other boxes. The goal is to determine whether all boxes can be opened, starting from the first unlocked box (box 0).

Problem Statement

You have n locked boxes, each represented as a list of keys. The task is to write a function, canUnlockAll(boxes), that checks if all the boxes can be opened. Each key corresponds to a box number, and a key inside a box unlocks the corresponding box.

	•	boxes[0] is always unlocked.
	•	A key with the value x unlocks box x.
	•	There may be keys that do not correspond to any box.

The function should return True if all boxes can be unlocked, or False if at least one box remains locked.

Approach

The solution uses a graph traversal strategy to explore the boxes, starting from box 0. The idea is to unlock boxes progressively by using the keys found in each unlocked box.

	1.	Start from box 0: This box is initially unlocked.
	2.	Track unlocked boxes: Use a list to keep track of which boxes are unlocked.
	3.	Use the keys: As each box is unlocked, use its keys to unlock additional boxes.
	4.	Check all boxes: Continue the process until no more boxes can be unlocked.
	5.	Result: If all boxes are unlocked by the end of the process, the function returns True; otherwise, it returns False.

Example

boxes = [[1], [2], [3], [4], []]
print(canUnlockAll(boxes))  # True: All boxes can be unlocked.

boxes = [[1, 4, 6], [2], [0, 4, 1], [5, 6, 2], [3], [4, 1], [6]]
print(canUnlockAll(boxes))  # True: All boxes can be unlocked.

boxes = [[1, 4], [2], [0, 4, 1], [3], [], [4, 1], [5, 6]]
print(canUnlockAll(boxes))  # False: Not all boxes can be unlocked.

Method

The algorithm starts by marking box 0 as unlocked and uses the keys inside it to unlock other boxes. As new boxes are unlocked, the process continues with their keys, until all possible boxes are explored. If all boxes are unlocked, the function returns True; otherwise, it returns False.

