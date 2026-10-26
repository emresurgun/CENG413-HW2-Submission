# CENG413 HW-2 — Docker Compose

Emre Şurğun-230212034

## Build and Run

cp .env.example .env && docker compose up -d --build

## Test

curl http://localhost:8080/health


curl http://localhost:8080/tasks


curl -X POST http://localhost:8080/tasks -H "Content-Type: text/plain" --data "Complete HW-2"

## Stop

docker compose down

