# Ghost Google Cloud Storage Plugin

## Installation

```bash
npm install --save ghost-google-cloud-storage
```

## Create storage module

```bash
mkdir -p /var/lib/ghost/adapters/storage
cp -r node_modules/ghost-google-cloud-storage/gcloud ./adapters/storage/
```

## Configuration

Add a `storage` block to your `config.${GHOST_ENVIRONMENT}.json` as below:

```json
"storage": {
    "active": "gcloud",
    "gcloud": {
        "projectId": "<Project ID>",
        "keyPath": "<Path to JSON Key for Service Account>",
        "bucketName": "<Bucket Name>",
        "assetDomain": "<Bucket Name>.storage.googleapis.com",
        "insecure": false,
        "cacheControlMaxAge": 2419200
    }
}
```

For environment variables,

```
storage__active=gcloud
storage__gcloud__projectId=<Project ID>
storage__gcloud__keyPath=<Path to JSON Key for Service Account>
storage__gcloud__bucketName=<Bucket Name>
storage__gcloud__assetsDomain=<Bucket Name>.storage.googleapis.com
storage__gcloud__insecure=false
storage__gcloud__cacheControlMaxAge=2419200
```

Notes:

- `assetDomain` is optional, default is `<Bucket Name>.storage.googleapis.com`
- `insecure` is optional, default is false, set true if use http instead of https
- `maxAge` is optional, default is 2419200 (= 28 days)
