### Use `code.interact()` to Drop into an Interactive Shell

```
import code
.
..
...
#Your code before the stop
print("Stopping here for inspection...")

# Open interactive shell
code.interact(local=locals())

# Code after this won't run until you exit the shell
print("This will run after you exit the interactive shell.")
exit()

```

