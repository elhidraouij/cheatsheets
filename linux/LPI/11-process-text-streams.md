# LPI

## Process text streams

### Redirections and pipes

`cat [filename]`, to display the content of the file  
`cat > [filename]`, to redirect _stdin_ to the file  
`cat [a_file] > [another_file]`, it will copy the content of `a_file` to `another_file`  
You can verify this by taping `diff [a_file] [another_file]` to print the difference between the two files  
`echo 'text' >> [a_file]`, will append `text` to the end of `[a_file]`

A great example of using a pipe (`|`) for redirecting output is by using the `grep` command as we did in `env | grep PATH`

### Processing text streams

#### Filter in content

`grep [regex] [file.txt]` or `[command] | grep [pattern]`, to filter information on text streams

| Options | Description               |
| ------- | ------------------------- |
| `-i`    | Ignore the case           |
| `-n`    | Display row number        |
| `-c`    | Count occurence           |
| `-v`    | Reverse the pattern       |
| `-r`    | Recurse through directory |

#### View a file in a pager

Rather than use `cat`, you can use the `less [file_name]` command to paginate the result

#### Getting a portion of a text file

`head [file_name]`, to display the first ten lines of a file  
`tail [file_name]`, to display the last ten lines of a file

`tail -n 5 [file_name]`, to display the last 5 lines only  
`head -n 12 [file_name]`, to display the 12 first lines only

We can pipe the result to the `nl` command to display lines number.

### Edit streams with `sed`

