# Reflection

## 1.2. Understanding how it works.
![alt text](image1.2.png)

If we take a look at `main()` in `main.rs`, an instance of TimerFuture is created and awaited within an async block that is passed to spawner.spawn(). This will print "Gilang's Komputer: howdy!", wait for 2 seconds, then print "Gilang's Komputer: done!". Meanwhile, the main thread will immediately print "Gilang's Komputer: hey hey" and then drop the spawner.

The drop(spawner) line is important because it ensures that the spawner and any tasks it may be running are properly cleaned up when they are no longer needed. This is a good practice in Rust to prevent memory leaks and other resource-related issues.