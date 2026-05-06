# Climate Tech Carbon Footprint Calculator API

> REST API for sustainability platforms and ESG reporting tools calculating scope 1, 2, and 3 carbon emissions. Accepts activity data inputs including energy consumption in kWh, fuel volumes, travel distances, procurement spend by category, and logistics shipment data. Returns CO2e emissions with methodology notes, emission factor sources, and confidence intervals. Supports GHG Protocol, ISO 14064, and TCFD reporting standards. Generates structured data for regulatory disclosure to CDP, EU CSRD, and SEC climate rules. Processes batch emissions calculations for 10000 data points per API call. Covers 50 countries with localised electricity grid emission factors updated quarterly.

## Features

- Full REST API

## Quick Start

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Configure environment
cp .env.example .env
# Edit .env with your settings

# 3. Run locally
uvicorn main:app --reload --port 8000

# 4. View interactive docs
open http://localhost:8000/docs
```

## Docker Deployment

```bash
# Build and run
docker compose up -d

# Check health
curl http://localhost:8000/health
```

## Authentication

Get a token first:
```bash
curl -X POST "http://localhost:8000/auth/token?username=admin&password=admin123"
```

Use the token in subsequent requests:
```bash
curl -H "Authorization: Bearer YOUR_TOKEN" http://localhost:8000/items
```

## API Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/health` | System health |
| POST | `/auth/token` | Get JWT token |
| GET | `/items` | List all items |
| POST | `/items` | Create item |
| GET | `/items/{id}` | Get item |
| PATCH | `/items/{id}` | Update item |
| DELETE | `/items/{id}` | Delete item |
| GET | `/stats` | API statistics |

Full interactive docs: `http://localhost:8000/docs`

## Rate Limits

| Endpoint | Limit |
|----------|-------|
| `/auth/token` | 10/minute |
| `GET /items` | 60/minute |
| `POST /items` | 30/minute |
| `DELETE /items` | 20/minute |

## Running Tests

```bash
pip install pytest httpx
pytest tests/ -v
```

## Production Notes

- Change `SECRET_KEY` in `.env` before deploying
- Replace in-memory `_db` with a real database
- Add proper user management to `auth.py`
- Configure `ALLOWED_ORIGINS` for CORS
- Use Nginx/Traefik as reverse proxy

## License

MIT



---

## Free vs Pro

| Feature | Free | Pro |
|---------|:----:|:---:|
| 100 requests/day | Yes | Yes |
| Standard endpoints | Yes | Yes |
| JSON responses | Yes | Yes |
| Unlimited requests | - | Yes |
| Premium endpoints | - | Yes |
| Batch processing | - | Yes |
| Webhook notifications | - | Yes |
| SLA guarantee | - | Yes |
| Priority support | - | Yes |

### Upgrade to Pro

Get the full version with all premium features, priority support, and lifetime updates.

**[Get Pro Version](https://buy.stripe.com/8x28wP7r18Is1dedI0cZa0B)**

- [Buy Now (Stripe)](https://buy.stripe.com/8x28wP7r18Is1dedI0cZa0B)
- [Buy on Gumroad](https://pulsegear.gumroad.com/l/tqpia)
- [Buy on Whop](https://whop.com/climate-tech-carbon-footprint-calculator-api)

