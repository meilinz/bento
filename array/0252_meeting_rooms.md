# 252 Meeting Rooms
## Problem Description
https://leetcode.com/problems/meeting-rooms/

## Solution
### Python 3
```
class Solution:
    def canAttendMeetings(self, intervals: List[List[int]]) -> bool:
        intervals.sort()
        for i in range(len(intervals)-1):
            if intervals[i][1] > intervals[i+1][0]:
                return False
        return True
```
