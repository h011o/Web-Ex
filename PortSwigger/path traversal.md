# LAB: : File path traversal, simple case

## My Solve

* GET request for an image looks like this : `GET /image?filename=24.jpg HTTP/2`
* I modified filename to look like: `GET /image?filename=../../../etc/passwd HTTP/2`, this gives us the contents of the `etc/passwd` file. 

This works because -

* `../` means go up one directory.
* Using trial and error we can find that we need to skip three such directories.

## Concepts Learned

* Learned how to exploit filename API's in burpsuite. 
