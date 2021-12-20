Templates are compiled in two phases

Before instantiation, this will detect:

-   syntax errors

-   unknown names (functions, types)

-   static assertions

After instantiation, this will check:

-   templated parameters support the required operations
