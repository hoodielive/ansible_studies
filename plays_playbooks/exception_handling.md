# Error Handling 

* Ignore errors by using the ignore_errors keyword.
* Force previously notified handler to run using the force_handlers keyword.
* Define failure conditions using the failed_when keyword.
* Override the "changed" status result using the changed_when keyword.
* Abort an entire play if any task fails using the any_errors_fatal keyword.
* Implement a block in order to logically group tasks and provide error handling using the following keywords:
  * block 
  * rescue
  * always


