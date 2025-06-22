# Text Manipulation

## Objectives

Train grep command usage

## Instructions

### Find all error messages

<details>
<summary>Show</summary>
<p>

```bash
grep "ERROR" log.txt
```

Alternatively, you can run

```bash
grep -i "error" log.txt
```

</p>
</details>

### Display lines containing the word _"request"_

<details>
<summary>Show</summary>
<p>

```bash
grep "request" log.txt
```

</p>
</details>

### Count how many warnings occured

<details>
<summary>Show</summary>
<p>

```bash
grep -ci "warning" log.txt
```

</p>
</details>

### Show all lines that are not `[INFO]` messages

<details>
<summary>Show</summary>
<p>

```bash
grep -v "^\[INFO\]" log.txt
```

</p>
</details>

### Show line numbers of all `[ERROR]` messages

<details>
<summary>Show</summary>
<p>

```bash
grep -n "ERROR" log.txt
```

</p>
</details>

### Find logs that happened at `09:02`

<details>
<summary>Show</summary>
<p>

```bash
grep "09:02" log.txt
```

</p>
</details>