# Gleam

>> 编译的时候报错
 `
 % go build                                                                                                                  
 #github.com/chrislusf/gleam/plugins/file/parquet
 ../../go/pkg/mod/github.com/chrislusf/gleam@v0.0.0-20201128110619-d48afd638bae/plugins/file/parquet/parquet_file_reader.go:8:2: imported and not used: "github.com/xitongsys/parquet-go/types"
 ../../go/pkg/mod/github.com/chrislusf/gleam@v0.0.0-20201128110619-d48afd638bae/plugins/file/parquet/parquet_file_reader.go:73:29: undefined: ParquetTypeToGoType
`

>> slove:it seems in v1.6.0 that functions was removed. Doing go get -u github.com/xitongsys/parquet-go@v1.5.4 solves the problem for me, but it would be better if gleam had some go.mod file
