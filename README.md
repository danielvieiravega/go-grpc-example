Exemplo de utilização do gRPC usando go.
O código foi feito acompanhando o curso de Comunicação entre sistemas da plataforma https://fullcycle.com.br/

sudo apt install protobuf-compiler 
go mod init github.com/<seu_user>/<repo_name>
go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest
export PATH="$PATH:$(go env GOPATH)/bin"
source ~/.bashrc


--gerar os stubs
protoc --proto_path=proto/ proto/*.proto --plugin=$(go env GOPATH)/bin/protoc-gen-go-grpc --go-grpc_out=. --go_out=.