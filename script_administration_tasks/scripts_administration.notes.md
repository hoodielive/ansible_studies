# Script Administration Tasks 

### Bash 
  * The first line must include a shebang '#!/bin/bash'.
  * Comments can be added by using the # symbol.
  * Exec permission needs to be added to the script.
  * Exec the script using the 'absolute path' or './script' (if it occurs in the cwd).
  * Example:
    ```bash 
    #!/bin/bash 
    # hello aeon script

    echo "Hello Aeon"!

    ```

 * Example2:
   ```bash
   #!/bin/bash 
   # for loop 

   for i in {1..5}
   do
      echo "Hello $i times!"
   done
   ```
