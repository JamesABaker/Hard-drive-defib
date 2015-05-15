*This project starded from a modified local script heavily based on a [mac issues article by Topher Kessler](http://www.macissues.com/2014/04/05/how-to-fix-deep-formatting-problems-with-os-x-drives/).*


#Hard drives are not ideal.

It's *hard* to take the eject messages seriously since 99.9% of the time everything is fine. But sometimes it goes wrong. ***REALLY*** wrong. Sometimes all you want to do is start over, but the wussy osx macbook won't let you.

This is a last resort little script that completely fecks up a hard drive by attempting to randomly write over it. However the idea is that it "unsticks" the hard drive. Then you can start again from some sort of diskutil thing.

**Be careful which disk you attack!** By default the script *"attacks"* `dev/disk2` so you'll need to change this to whatever disk is causing you problems. You should already know which one is causing the problems. Use `diskutil list` just to be sure.



##Running

 1. `cd` to the download directory and run the following command to make the script executable:

 `chmod 777 deep.sh`

 2. Now switch to root in the Terminal

 `sudo su`

 3. And finally run the script, immediately followed by attaching your drive to the Mac:

 `./deep.sh`

 4. Plug in the hard drive.

 5. Wait for the script to stop for a bit, then close the terminal and terminate processes.

 6.Get out of root by closing the terminal or ctrl C/D (I forget which)

 7. Run `diskutil eraseDisk JHFS+ Test /dev/disk2` again being careful to check which disk needs erasing (it may have changed since last time you checked `diskutil list`). The disk is now as good as new and **all your old data is gone**.

 8. Check your activity monitor. If you see `bash` running it means the loop is still going (unless you ran some other bash script with root permission). If `bash` is still running in root then run:

 `sudo killall bash`

 9. Pray that this works otherwise it's a hardware thing...
