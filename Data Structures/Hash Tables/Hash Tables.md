<hr>

## Hash Tables (Dict)
- Key:Value Pairs
<br>

<h2 align='center'>Time Complexity </h2>

<div align='center'>

| Operation    | Time Complexity | Example (Python)           | Example (Javascript)|
| ------------ | --------------- | -------------------------- | -------------------- |
|Get Item      | O(1)            | `my_dict.get("age")`       |
|Set Item      | O(1)            | `my_dict["name"] = "Mike"` |
|Delete        | O(1)            | `my_dict.pop("age")`       |
|Search	 Key		| O(1)							| `'key' in my_dict`         |
|Search Value	 | O(n)            | `value in my_dict.values()`|
</div>
<br>

## Cons:
- **Collisions** - handled by linked list originally
	- Python uses open addressing 

