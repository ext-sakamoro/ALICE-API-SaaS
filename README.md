# ALICE-API SaaS

High-performance API gateway with distributed rate limiting

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-API |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/routes` | ルーティング設定 |
| `GET  /api/v1/metrics` | レート制限メトリクス |
| `POST /api/v1/proxy` | リクエストプロキシ |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
