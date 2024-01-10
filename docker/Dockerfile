# FROM alpine:3.19
FROM debian:trixie-20231218-slim

# RUN apk update
# RUN apk add libc6-compat libgcc libstdc++
RUN apt-get update
RUN apt-get install -qq wget

RUN wget -q https://download.dfinity.systems/ic/69e1408347723dbaa7a6cd2faa9b65c42abbe861/openssl-static-binaries/x86_64-linux/pocket-ic.gz
RUN gzip -d pocket-ic.gz
RUN chmod +x pocket-ic

ENTRYPOINT [ "/pocket-ic" ]
CMD [ "-p", "8000" ]

EXPOSE 8000



# docker build -t pic .
# docker build -t pic --platform linux/x86_64 .
# docker run  pic
