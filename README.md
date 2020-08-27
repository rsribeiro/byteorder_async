byteorder - async
=========
This is a fork of [byteorder](https://github.com/BurntSushi/byteorder) with the addition of:

*  Using modern rust for try (? rather than try!)
* support for `tokio::io`
* support for `futures::io`

### Installation

[![](https://img.shields.io/crates/v/byteorder_async?style=for-the-badge)](https://crates.io/crates/byteorder_async)


for `futures::io`
```toml
byteorder_async = {version="1.3.0", features=["futures_async"] }
```


for `tokio::io`
```toml
byteorder_async = {version="1.3.0", features=["tokio_async"] }
```


Basic async usage:

```rust
use byteorder_async::AsyncReadByteOrder;

let reader : io::AsyncRead = ...;
// after the byte_order its the same calls.
let byte = reader.read_u8().await;
```
