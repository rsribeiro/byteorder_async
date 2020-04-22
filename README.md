byteorder - async
=========
This is a fork of [byteorder](https://github.com/BurntSushi/byteorder) with the addition of:

*  Using modern rust for try (? rather than try!)
* support for `tokio::io`
* support for `futures::io`

### Installation

[![](https://img.shields.io/crates/v/byteorder_async?style=for-the-badge)](https://crates.io/crates/byteorder_async)


for `futures::io`
```
byteorder_async = {version="1.0.0", features=["futures_async"] }
```


for `tokio::io`
```
byteorder_async = {version="1.0.0", features=["tokio_async"] }
```


Basic async usage:

```
use byteorder_async::AsyncReadByteOrder;

let reader : io::AsyncRead = ...;
// after the byte_order its the same calls.
let byte = reader.byte_order().read_u8().await;
```



Note:
Thre reason for the `byte_order()` call is because `async fn` is not supprted in traits yet. 