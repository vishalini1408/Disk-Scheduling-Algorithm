# Experiment 13: Disk Scheduling Algorithm

## Title
C-SCAN Disk Scheduling — Online Exam Portal

## Aim
To implement the C-SCAN disk scheduling algorithm and observe the order in which pending disk requests are served and the total head movement.

## Input Details
- Initial disk-head position: `53`
- Last track: `199`
- Requests: `98, 183, 37, 122, 14, 124, 65, 67`

## Algorithm
1. Store the initial head position, last track, and pending requests.
2. Sort the requests in ascending order.
3. Move the head upward and serve every request greater than or equal to the initial head position.
4. Move the head to track `199`.
5. Wrap around to track `0`.
6. Serve the remaining requests below the initial head position.
7. Display the service order and total seek distance.

## Compile and Run
```bash
gcc cscan.c -o cscan
./cscan
```

## Expected Output
```text
Order: 53 -> 65 -> 67 -> 98 -> 122 -> 124 -> 183 -> 199 -> 0 -> 14 -> 37
Total seek = 382 tracks
```

## Observation
The head moves from track 53 to 199 (146 tracks), wraps from 199 to 0 (199 tracks), and then moves from 0 to 37 (37 tracks). The total head movement is `146 + 199 + 37 = 382 tracks`.

## Result
The C-SCAN disk scheduling algorithm was implemented in C, and the service order and total seek distance were displayed.
