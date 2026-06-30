# cf-worker-emailer

A cloudflare worker to handle website form

## Required Secrets

- TO_EMAIL: ${{ secrets.TO_EMAIL }}
- FROM_EMAIL: ${{ secrets.FROM_EMAIL }}
- RESEND_API_KEY: ${{ secrets.RESEND_API_KEY }}
- TURNSTILE_SECRET: ${{ secrets.TURNSTILE_SECRET }}

## Required Vars

(see wranngler.toml)

- ALLOWED_ORIGIN = "https://mydomain.tld"
- THANKYOU_URL = "https://mydomain.tld/thank-you/"
- ERROR_URL = "https://mydomain.tld/contact/?error=1"


## Process
- Receive POST
- Validate JSON
- Reject invalid requests
- Verify Turnstile
- Rate limit
- Honeypot check
- Send email
- Return success
