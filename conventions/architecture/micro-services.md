# About micro services conventions

The key words “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, and “OPTIONAL” in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).

## Summary

* [Health check](#health-check)
* [Metrics](#metrics)

# Health check

All micro service __MUST__ have a `/_health` HTTP URL accessible on port 80 with these following responses according to the statutes:

| Health status | Response body | Response HTTP code | Response content type |
|---------------|------------------------------------------------------------------|--------------------|---------------------------------|
| Success | `{"alive": true}` | 200 | `application/json; charset=utf-8` |
| Failed | `{"alive": false, "message": "Error description, human readable"}` | 503 | `application/json; charset=utf-8` |

# Metrics

All micro service __MUST__ have a `/_metrics` HTTP URL accessible on port 80 with code 200.  
These metrics __MUST__ be readable by [Prometheus](https://prometheus.io/).  
You __MUST__ read and apply the [best practices of naming](https://prometheus.io/docs/practices/naming/).  
You __MUST__ implement 10 metrics at least.  
All metrics __MUST__ be maintained for backward compatibility reasons.

## Note for Go programmers

It's __RECOMMENDED__ to use the [Prometheus client for Go](https://github.com/prometheus/client_golang).
