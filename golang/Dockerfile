FROM golang:1.21.4-alpine3.18 as build

WORKDIR /src/hello

COPY . .

RUN go mod init example/hello

RUN go build


FROM scratch

WORKDIR /hello

COPY --from=build /src/hello /hello

ENTRYPOINT ["./hello"]