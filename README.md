PlatformCore
============

## Setup
1. Before installing the helm chart make sure the secrets section defined below are installed

## Secrets
1. `kubectl create secret generic --from-env-file=./charts/postgres/.env postgres-secret`

## TODOs
1. Fix tests in `postgres`
1. Fix tests in `redis`
