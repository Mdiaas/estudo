# stage de build
FROM golang:1.19 AS build

WORKDIR /app

COPY . /app

RUN CGO_ENABLED=0 GOOS=linux go build -o main main.go

# stage imagem final
FROM scratch

WORKDIR /

COPY --from=build /app/main ./

ENTRYPOINT  [ "./main" ]