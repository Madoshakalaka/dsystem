# D System 
**It's a work in progress**

Tired of creating service files or Windows registry shenanigans?

with dsystem, you can make any python script run on startup like never before.

It can be as easy as:

`./your_script.py run-on-startup`




# Minimal Code

```.python
# my_script.py

from dsystem import run_on_startup, stop_run_on_startup

if argv[1] == 'run-on-startup':
    run_on_startup()
elif argv[1] == 'stop-run-on-startup':
    stop_run_on_startup()
else:
    # attach your code here
```

Note the system knows your script by its filename.

So if you wish to rename or move the entry script, it's recommended to call `stop_run_on_startup()` to 
clean the old service first.

# Under the Hood

On Unix, it uses systemd
On Windows, it uses Startup Folder/Windows Registry

