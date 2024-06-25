FROM node:latest as build-stage

ARG HOST=http://localhost:8080

ENV NODE_OPTIONS=--openssl-legacy-provider

RUN git clone https://github.com/PassiveDNS/PassiveDNS.git /app
WORKDIR /app/frontend

RUN npm install
RUN npm run build

FROM nginx as production-stage

FROM nginx:latest AS frontend
COPY --from=frontend-builder /app/frontend/dist /www
EXPOSE 80
