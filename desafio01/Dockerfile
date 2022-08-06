FROM golang:alpine as build 

WORKDIR /app 
COPY codeeducation.go .

RUN CGO_ENABLED=0 GOOS=linux go build codeeducation.go

FROM scratch 
WORKDIR /app 
COPY --from=build /app .

ENTRYPOINT ["./codeeducation"]
