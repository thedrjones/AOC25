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
