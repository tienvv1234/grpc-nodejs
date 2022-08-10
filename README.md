# GRPC Nodejs

-   Google remote protocol c
-   At the core of gRPC, you need to define the messages and services using protocol buffers

## gRPC concepts

### Protocol Buffers role in gRPC

-   Protocol Buffers is used to define the message .proto
-   Define data for request and response
-   then, we define the service that using protocol buffers

### Efficiency of protocol buffers over JSON

-   gRPC uses protocol buffers for communications
-   Let's measure the payload size vs JSON

JSON 55 bytes

```
{
    "age": 35
    "first_name": "Stephane",
    "last_name": "Maarek"
}
```

Same in Protocol buffers: 20 bytes

```
message Person {
    int32 age = 1;
    string first_name = 2;
    string last_name = 3;
}
```

#### We save in Network Bandwidth

-   Parsing JSON is actualy CPU intensive (because the format is human readable)
-   Parsing Protocol Buffers (Binary format) is less CPU intensive because it's closer to how a machine represends data
-   By using gRPC, the use of protocol buffers means faster and more efficient communication, friendly with mobile devices that have a slower CPU

What's HTTP/2
