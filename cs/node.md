# Node.js

This snippet gets a file relative to current directory and removes the Windows drive prefix, if one exists

```JavaScript
const getFilePath = (fileName) => {
	var filePath = new URL(fileName, import.meta.url).pathname;
	if (filePath.match(/:/) != null) {
		const index = filePath.match(/:/).index;
		filePath = filePath.slice(index + 1, filePath.length);
	}
	return filePath;
};
```
