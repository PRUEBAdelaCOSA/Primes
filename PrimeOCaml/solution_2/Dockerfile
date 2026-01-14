FROM primeimages/ocaml:5.1 AS build

WORKDIR /prime-ocaml-functional

COPY . .

RUN dune build

FROM alpine:3.23.2

WORKDIR /app
COPY --from=build /prime-ocaml-functional/_build/install/default/bin/prime-ocaml-functional prime-ocaml-functional.exe

ENTRYPOINT [ "./prime-ocaml-functional.exe" ]
