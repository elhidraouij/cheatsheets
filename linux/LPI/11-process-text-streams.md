# LPI

## Process text streams

### Redirections and pipes

`cat [filename]`, to display the content of the file  
`cat > [filename]`, to redirect _stdin_ to the file  
`cat [a_file] > [another_file]`, it will copy the content of `a_file` to `another_file`  
You can verify this by taping `diff [a_file] [another_file]` to print the difference between the two files  
`echo 'text' >> [a_file]`, will append `text` to the end of `[a_file]`

A great example of using a pipe (`|`) for redirecting output is by using the `grep command` as we did in `env | grep PATH`

### Processing text streams

