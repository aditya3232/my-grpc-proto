## 1. Makefile
- make clean -> Hapus seluruh folder protogen/, lalu buat ulang protogen/go
- make protoc-go -> Generate kode Go dan gRPC dari proto/hello, payment, dan transaction ke protogen/go/
- make build -> clean + protoc-go
- make clean-gateway -> Hapus dan buat ulang protogen/gateway/
- make protoc-go-gateway -> Generate kode gRPC-Gateway (REST ke gRPC) ke protogen/gateway/go
- make protoc-openapiv2-gateway -> Generate spesifikasi OpenAPI (YAML, digabung jadi merged) ke protogen/gateway/openapiv2
- make build-gateway -> clean-gateway + protoc-go-gateway (tanpa OpenAPI)

## 2. Grpc
- install protoc-gen-go-grpc
```bash
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
```
- Make sure Go's bin directory is in your PATH
```bash
export PATH="$PATH:$(go env GOPATH)/bin"
```
- Then reload
```bash
source ~/.zshrc
```
- Verify both plugins are found
```bash
which protoc-gen-go protoc-gen-go-grpc
```