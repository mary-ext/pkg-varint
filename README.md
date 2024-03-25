# varint

Encode and decode Protobuf-style varint bytes from a buffer.

Fork of [chrisdickinson's `varint` npm package](https://npmjs.com/package/varint).

```ts
// Encoding a varint...
{
	const buffer = new Uint8Array(16);

	const written = encode(300, buffer, 0);
	// -> 2 bytes written

	console.log(buffer.subarray(0, written));
	// -> Uint8Array(2) [0xAC, 0x02]
}

// Decoding a varint...
{
	const buffer = new Uint8Array([0xAC, 0x02]);
	const [num, read] = decode(buffer, 0);
	// -> 2 bytes read, got 300
}
```
