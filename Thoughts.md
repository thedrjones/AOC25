## Day 1
Today's task was brute forced moving one position at a time, but it ran in < 35ms ... so no need to optimize yet. I try to start simple if I can then work up the complexity when needed.

Part two was pretty much a case of checking when the number hit 0, since I already iterated every single number as it passed by. 


## Day 2
Part one is nice and easy, just split in two, see if it's the same, I kind of guessed where part 2 might go, but didn't immediately go down that road as it may have been a red herring.

When it came to part two, I had three solutions, each is single threaded and still essentially brute forced, the one shared is the quickest at <3.25 seconds to run.

Using 123123123 as the example:
1. Try was check each of the 2 recurring 123 groups a block at a time (~9 seconds)
2. Create 123_123_123 and compare with 123123123 (~3.45 seconds, lazy!)
3. Check if 123123123 has 3 iterations of 123 using the pattern match function (3.25 seconds, a little better).

I could make it quicker by being a bit more elegant of a method. Maybe I will revisit after I complete the 12 puzzles if I find the time.

I could dispatch each range to a number of range processing jobs and go multi-thread, but I'm trying to avoid that until I really need it. Part of my plan is show "real-world" MUMPS code, not much of the legacy code-base I see in my day-to-day work is multi-threaded.

## Day 3
Part one is a nice straightforward pick the two highest can put them together. I wondered if part two would be that the cell's alignment was wrong and you needed to go vertical or something.

Part two was harder to work out than I can to admit too, I had a number of false starts that probably would work in the end, but I realised in the end I probably just need to pick the highest in a rolling window, eunsuring there is always at least enoug hleft to get to the lower digits in the 12 digit number. A bigger number on the left should always result in the highest result in the end.

Today was a busy day at work and with evening visits to friends, so I've not quite finished the part 2 solution yet, but hopefully I'll manage to finish it in the next few days.

## Day 4 
Part one is a nice simple task, just work out the position to check how may can be removed. I wondered if part two would be something about moving more, so made it so it could be called multiple times, a good gamble it would seem.

Part two is just recurring part one with an extra step to remove those you've found could be removed. It ran through 63 (64th iteration had no removals) iterations in 0.48 seconds, which is good enough for me to not feel the need to optimize.
