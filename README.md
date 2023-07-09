## Spring Boot, JPA, PostgreSQL with Prometheus, Grafana and Istio on K3s

![GitHub contributors](https://img.shields.io/github/contributors/christopher3810/SpringServicemonitoring)
![GitHub issues](https://img.shields.io/github/issues/christopher3810/SpringServicemonitoring)
![GitHub forks](https://img.shields.io/github/forks/christopher3810/SpringServicemonitoring)
![GitHub stars](https://img.shields.io/github/stars/christopher3810/SpringServicemonitoring)
![GitHub license](https://img.shields.io/github/license/christopher3810/SpringServicemonitoring)

<p align="center">
    <img src ="https://github.com/christopher3810/JavaPlayGround/assets/61622657/dc94b4d0-95b9-44bb-9205-e4b4d4c9099c" width="500" height="500">
</p>

### 목표

Spring Boot, JPA, PostgreSQL 기반 웹 프로젝트를 k3s 클러스터에서 동작하게하고,

Prometheus와 Grafana를 사용하여 리소스 모니터링을 구현하는 것.

### 설계

```mermaid
graph LR
    subgraph K3s Cluster
        istioControlPlane{Istio Control Plane}
        subgraph Node 1
            subgraph Pod1
                spring1[Spring Boot App]
                istioProxy1(Istio Proxy)
            end
        end
        subgraph Node 2
            subgraph Pod2
                prometheus[Prometheus]
                istioProxy2(Istio Proxy)
            end
        end
        subgraph Node 3
            subgraph Pod3
                Grafana[Grafana]
                istioProxy3(Istio Proxy)
            end
        end
        istioControlPlane --> istioProxy1
        istioControlPlane --> istioProxy2
        istioControlPlane --> istioProxy3
    end

```

### tools

Spring boot.
Prometheus.
Grafama.
K3s.
Istio.
