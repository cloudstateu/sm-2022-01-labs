<img src="../../../img/logo.png" alt="Chmurowisko logo" width="200" align="right">
<br><br>
<br><br>
<br><br>

# Installing Istio

## LAB Overview

#### In this lab you will install Istio

## Task 1: Istio installation

1. istioctl x precheck
2. istioctl install --set profile=demo
3. istioctl verify-install
4. kubectl get ns
5. kubectl -n istio-system get deploy
6. kubectl get svc istio-ingressgateway -n istio-system
7. Install Prometheus:
    
    ```bash
    kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.16/samples/addons/prometheus.yaml
    ```
8. Install Kiali:
   
    ```bash
    kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.16/samples/addons/kiali.yaml
    ```

9. Install Jeager:
    
    ```bash
    kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.16/samples/addons/jaeger.yaml
    ```


## END LAB

<br><br>

<center><p>&copy; 2023 Chmurowisko Sp. z o.o.<p></center>
