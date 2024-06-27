# Primitives wrapper

All primitives except `null` and `undefined`, have their corresponding object wrapper types. The primitive does not have methods such as `toString` etc, it is the wrapper that it initialised when the property/method is accessed

| Type | `typeof` return value | Object wrapper |
| --- | - | - |
| Null | `"object"` | N/A |
| Undefined | `"undefined"` | N/A |
| Boolean | `"boolean"` | Boolean |
| Number | `"number"` | Number |
| BigInt | `"bigint"` | BigInt |
| String | `"string"` | String |
| Symbol | `"symbol"` | Symbol |
