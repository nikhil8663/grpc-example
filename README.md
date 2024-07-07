# gRPC Example in Go

This is a simple example of a gRPC client and server implemented in Go.

## Project Structure

grpc-example/
├── client/
│ └── client.go
├── go.mod
├── go.sum
├── helloworld/
│ ├── helloworld.proto
│ ├── helloworld.pb.go
│ └── helloworld_grpc.pb.go
└── server/
    └── server.go

## Prerequisites

- [Go](https://golang.org/doc/install) 1.20 or later
- [Protocol Buffers](https://grpc.io/docs/protoc-installation/) compiler (`protoc`)
- gRPC Go plugins for Protocol Buffers:
  ```sh
  go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
  go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
  
Generate gRPC Code
Run the following command to generate the Go code from the .proto file:
protoc --go_out=. --go_opt=paths=source_relative --go-grpc_out=. --go-grpc_opt=paths=source_relative helloworld/helloworld.proto


Install Dependencies
Navigate to the project root and run:

go mod tidy
Running the Server
Open a terminal and navigate to the server directory:

Copy code
cd server
go run server.go
The server will start and listen on localhost:50051.

Running the Client
Open another terminal and navigate to the client directory:

Copy code
cd client
go run client.go
You should see the following output:

makefile
Copy code
Greeting: Hello world
Project Explanation
helloworld.proto: Defines the gRPC service and messages.
helloworld.pb.go and helloworld_grpc.pb.go: Generated files containing Go code for the service and messages defined in helloworld.proto.
server/server.go: Implements the gRPC server.
client/client.go: Implements the gRPC client.
