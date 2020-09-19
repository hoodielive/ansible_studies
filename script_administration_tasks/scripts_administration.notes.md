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

    echo "Hello Aeon"

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

* Example3: 
    ```bash
    #!/bin/bash 
    echo -n "Enter the name of a state: "
    read STATE
    echo -n "The capital of $STATE is: "

    case $STATE in
      Georgia)
        echo "Atlanta"
        ;; 
      Virginia)
        echo "Richmond"
        ;; 
      Texas)
        echo "Austin"
        ;;
      Maine)
        echo "Augusta"
        ;;
      *) 
      echo "Not in database"
      ;;
    esac
    ```
