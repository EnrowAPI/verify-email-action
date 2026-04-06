# Verify Email Action

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/EnrowAPI/verify-email-action)](https://github.com/EnrowAPI/verify-email-action)
[![Last commit](https://img.shields.io/github/last-commit/EnrowAPI/verify-email-action)](https://github.com/EnrowAPI/verify-email-action/commits)

GitHub Action to verify if an email address is deliverable. Powered by [Enrow](https://enrow.io).

## Usage

```yaml
- name: Verify email
  uses: EnrowAPI/verify-email-action@v1
  id: enrow
  with:
    api_key: ${{ secrets.ENROW_API_KEY }}
    email: 'john.doe@apple.com'

- name: Check result
  run: echo "Qualification: ${{ steps.enrow.outputs.qualification }}"
```

## Inputs

| Name      | Required | Default | Description                    |
| --------- | -------- | ------- | ------------------------------ |
| `api_key` | Yes      |         | Your Enrow API key             |
| `email`   | Yes      |         | Email address to verify        |
| `wait`    | No       | `true`  | Poll until the result is ready |

## Outputs

| Name            | Description                               |
| --------------- | ----------------------------------------- |
| `qualification` | Result qualification (`valid`, `invalid`)  |
| `id`            | The verification ID                       |
| `raw`           | Full JSON response from the API           |

## Pricing

Enrow gives you **50 free credits** when you sign up. Each email verification costs **1 credit**.

[Create a free account](https://app.enrow.io/sign-up)

## Links

- [Enrow website](https://enrow.io)
- [API documentation](https://docs.enrow.io)
- [Dashboard](https://app.enrow.io)
