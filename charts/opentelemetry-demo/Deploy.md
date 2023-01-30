# opentelemetry-demo

## Setup

```bash

kubectl create ns open-telemetry

# 1. Package
helm dependency update charts/opentelemetry-demo/

helm package charts/opentelemetry-demo/ -d charts/opentelemetry-demo/

# 2. Install
helm install \
--namespace open-telemetry \
otel-demo \
/etc/kubernetes/charts/opentelemetry-demo-0.16.0.tgz \
-f /etc/kubernetes/charts/opentelemetry-demo-0.16.0.yaml

# 3. Upgrade
helm upgrade \
--namespace open-telemetry \
otel-demo \
/etc/kubernetes/charts/opentelemetry-demo-0.16.0.tgz \
-f /etc/kubernetes/charts/opentelemetry-demo-0.16.0.yaml

# 4. Uninstall
helm uninstall \
--namespace open-telemetry \
otel-demo 

# 5. Template
helm template \
--namespace open-telemetry \
otel-demo \
charts/opentelemetry-demo/ \
-f charts/opentelemetry-demo/values-amd64.yaml > \
charts/opentelemetry-demo/dist.yaml
```

## images

```bash
# github.com/open-telemetry/opentelemetry-demo
## kafka
docker pull ghcr.io/open-telemetry/demo:v1.2.1-kafka && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-kafka registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-kafka && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-kafka
## quoteservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-quoteservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-quoteservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-quoteservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-quoteservice
## emailservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-emailservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-emailservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-emailservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-emailservice
## productcatalogservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-productcatalogservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-productcatalogservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-productcatalogservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-productcatalogservice
## paymentservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-paymentservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-paymentservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-paymentservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-paymentservice
## checkoutservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-checkoutservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-checkoutservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-checkoutservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-checkoutservice
## currencyservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-currencyservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-currencyservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-currencyservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-currencyservice
## frauddetectionservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-frauddetectionservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-frauddetectionservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-frauddetectionservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-frauddetectionservice
## loadgenerator
docker pull ghcr.io/open-telemetry/demo:v1.2.1-loadgenerator && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-loadgenerator registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-loadgenerator && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-loadgenerator
## frontendproxy
docker pull ghcr.io/open-telemetry/demo:v1.2.1-frontendproxy && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-frontendproxy registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-frontendproxy && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-frontendproxy
## accountingservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-accountingservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-accountingservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-accountingservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-accountingservice
## frontend
docker pull ghcr.io/open-telemetry/demo:v1.2.1-frontend && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-frontend registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-frontend && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-frontend
## featureflagservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-featureflagservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-featureflagservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-featureflagservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-featureflagservice
## cartservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-cartservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-cartservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-cartservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-cartservice
## recommendationservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-recommendationservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-recommendationservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-recommendationservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-recommendationservice
## adservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-adservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-adservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-adservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-adservice
## shippingservice
docker pull ghcr.io/open-telemetry/demo:v1.2.1-shippingservice && \
docker tag ghcr.io/open-telemetry/demo:v1.2.1-shippingservice registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-shippingservice && \
docker push registry.cn-qingdao.aliyuncs.com/wod/open-telemetry-demo:v1.2.1-shippingservice

# opentelemetry-collector
docker pull otel/opentelemetry-collector-contrib:0.69.0 && \
docker tag otel/opentelemetry-collector-contrib:0.69.0 registry.cn-qingdao.aliyuncs.com/wod/opentelemetry-collector-contrib:0.69.0 && \
docker push registry.cn-qingdao.aliyuncs.com/wod/opentelemetry-collector-contrib:0.69.0

## redis
docker pull redis:alpine && \
docker tag redis:alpine registry.cn-qingdao.aliyuncs.com/wod/redis:alpine && \
docker push registry.cn-qingdao.aliyuncs.com/wod/redis:alpine

# postgres
docker pull postgres:14 && \
docker tag postgres:14 registry.cn-qingdao.aliyuncs.com/wod/postgres:14 && \
docker push registry.cn-qingdao.aliyuncs.com/wod/postgres:14

# prometheus
docker pull quay.io/prometheus/prometheus:v2.41.0 && \
docker tag quay.io/prometheus/prometheus:v2.41.0 registry.cn-qingdao.aliyuncs.com/wod/prometheus:v2.41.0 && \
docker push registry.cn-qingdao.aliyuncs.com/wod/prometheus:v2.41.0

# jaeger
docker pull jaegertracing/all-in-one:1.39.0 && \
docker tag jaegertracing/all-in-one:1.39.0 registry.cn-qingdao.aliyuncs.com/wod/jaeger:1.39.0 && \
docker push registry.cn-qingdao.aliyuncs.com/wod/jaeger:1.39.0

# grafana
docker pull grafana/grafana:9.3.1 && \
docker tag grafana/grafana:9.3.1 registry.cn-qingdao.aliyuncs.com/wod/grafana:9.3.1 && \
docker push registry.cn-qingdao.aliyuncs.com/wod/grafana:9.3.1
```
