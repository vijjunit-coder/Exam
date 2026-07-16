n = int(input())

intervals = []

for _ in range(n):
    start, end = map(int, input().split())
    intervals.append([start, end])
intervals.sort()

merged = [intervals[0]]

for start, end in intervals[1:]:
    last_end = merged[-1][1]
    if start <= last_end:
        merged[-1][1] = max(last_end, end)
    else:
        merged.append([start, end])
for start, end in merged:
    print(start, end)
