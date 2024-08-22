# Node.js Express Web Uygulaması

Bu proje, Docker ve Kubernetes kullanarak basit bir Node.js Express web uygulamasının dağıtımını göstermektedir.

## İçindekiler
- [Proje Özeti](#proje-özeti)
- [Kurulum](#kurulum)
- [Docker Kullanımı](#docker-kullanımı)
- [Kubernetes Kullanımı](#kubernetes-kullanımı)
- [Test Etme](#test-etme)
- [Ekstra Adımlar](#ekstra-adımlar)
- [Yazar](#yazar)

## Proje Özeti
Bu proje, "Hello World!" mesajını dönen basit bir Node.js Express web uygulamasını içerir. Uygulama, Docker kullanılarak konteynerize edilmiştir ve Kubernetes kullanılarak dağıtılmıştır.

## Kurulum

### Gerekli Araçlar
- Node.js
- Docker
- Kubernetes (minikube veya başka bir dağıtım)
- Docker Hub hesabı

### Node.js ve Express Kurulumu
Projeyi yerel olarak çalıştırmak için:
1. Projeyi klonlayın:
   ```bash
   git clone <repository-url>
   cd node-web-app

2. Bağımlılıkları yükleyin:

npm install

3. Uygulamayı başlatın:

node app.js
4. Tarayıcıda http://localhost:3000 adresini ziyaret edin.

### Docker Kullanımı:

## Docker İmajını Oluşturma
Dockerfile ile Docker imajını oluşturun:

docker build -t node-web-app .
Docker konteynerini çalıştırın:


docker run -p 3000:3000 node-web-app
## Docker Hub’a İmaj Yükleme
Docker Hub hesabınıza giriş yapın:


docker login
Docker imajını etiketleyin ve yükleyin:

docker tag node-web-app <your-dockerhub-username>/node-web-app
docker push <your-dockerhub-username>/node-web-app

## Kubernetes Kullanımı
Deployment ve Service Dosyalarını Uygulama
Deployment ve Service dosyalarını Kubernetes cluster'ınıza uygulayın:

kubectl apply -f node-deployment.yaml
kubectl apply -f node-service.yaml
Uygulamanın çalıştığını doğrulamak için:


kubectl get services
Buradan LoadBalancer IP adresini alarak tarayıcıda test edebilirsiniz.


## Test Etme
Web uygulamasını tarayıcıda http://<loadbalancer-ip> adresi üzerinden test edin.


## Ekstra Adımlar
Uygulamayı Ölçeklendirme
Pod sayısını artırmak için node-deployment.yaml dosyasındaki replicas değerini güncelleyin ve tekrar uygulayın:

kubectl apply -f node-deployment.yaml


## Ingress Controller Ekleme
Ingress Controller kurarak uygulamanıza belirli bir domaine veya IP adresine yönlendirme ekleyebilirsiniz.

## Yazar
Hale Ahıshalı Kizir https://github.com/halekizir
