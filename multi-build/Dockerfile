# FROM gcc:12.2.0 AS compiler
# WORKDIR /app
# COPY ./hello.c .
# RUN gcc hello.c

# FROM ubuntu:20.04
# WORKDIR /app
# COPY --from=compiler /app/a.out .
# CMD ["./a.out"]

# 開発・本番共通部分
FROM ubuntu:20.04 AS base
RUN apt update
CMD ["sh", "-c","echo My name is $my_name"]

# 開発環境用
FROM base AS development
ENV my_name=TEST

# 本番環境用
FROM base AS production
ENV my_name=Bob