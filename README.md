# Docker Temelleri

Bu repo, Docker temellerini öğrenmek için hazırlanmıştır. Docker'ı öğrenmek için bu repo'yu takip edebilirsiniz.

## Docker Nedir?

Docker, uygulamaları ve uygulamaların çalıştığı ortamı bir arada paketleyerek, uygulamaları kolayca dağıtabileceğiniz
bir platformdur.

## Kapsayıcı(Container) Nedir?

Docker kapsayıcıları, çalışan uygulamalar için hafif sanallaştırılmış çalışma ortamlarıdır. Uygulamalrı yalıtılmış
ortamlara(kapsayıcılara) paketlemek; uygulamaları geliştirmeyi, dağıtmayı, bakımını yapmayı ve kullanmayı da
kolaylaştırır.

## Docker Mimari Bölümleri

### Client

Docker client, kullanıcıların Docker ile etkileşim kurmasını sağlar.

### Docker Host

Docker host, Docker client ile etkileşim kurarak Docker kapsayıcılarını oluşturur, yönetir ve çalıştırır.

### Docker Image

Docker image, Docker kapsayıcılarının çalışması için gerekli olan dosyaları içeren bir dosyadır.

### Docker Container

Docker container, Docker image'lerden oluşturulan çalışan birimlerdir.

### Docker Registry

Docker registry, Docker kapsayıcılarını depolamak için kullanılan bir depodur. Docker registry, Docker Hub gibi üçüncü
parti servislerde bulunabilir.

## Docker Kurulumu

### Docker Engine Kurulumu

Docker Engine, Docker'ın temel bileşenidir. Docker Engine, Docker kapsayıcılarını oluşturmak, yönetmek ve çalıştırmak
için kullanılır. İşletim sistemi bazlı olarak Docker Engine'ı kurmak için aşağıdaki linkleri kullanabilirsiniz.

- [Docker Engine Kurulumu (Linux)](https://docs.docker.com/engine/install/)
- [Docker Engine Kurulumu (Windows)](https://docs.docker.com/docker-for-windows/install/)
- [Docker Engine Kurulumu (Mac)](https://docs.docker.com/docker-for-mac/install/)

## Docker Temel Komutları

**docker info** : Docker'ın çalışma durumunu gösterir.

```shell
$ docker info
```

**docker ps** : Çalışan kapsayıcıları listeler.

```shell
$ docker ps
```

**docker ps -a** : Tüm kapsayıcıları listeler.

```shell
$ docker ps -a
```

**docker container ls** : Çalışan kapsayıcıları listeler.

```shell
$ docker container ls
```

**docker container ls -a** : Tüm kapsayıcıları listeler.

```shell
$ docker container ls -a
```

**docker container run** : Yeni bir kapsayıcı oluşturur.

```shell
$ docker container run <image_name>
```

**docker container run -d** : Yeni bir kapsayıcı oluşturur ve arka planda çalışmasını sağlar.

```shell
$ docker container run -d <image_name>
```

**docker container run -it** : Yeni bir kapsayıcı oluşturur ve içerisine girilmesini sağlar.

```shell
$ docker container run -it <image_name>
```

**docker container run -p** : Yeni bir kapsayıcı oluşturur ve portları bağlar.

```shell
$ docker container run -p <host_port>:<container_port> <image_name>
```

**docker container start** : Bir kapsayıcıyı başlatır.

```shell
$ docker container start <container_id>
```

**docker container exec** : Bir kapsayıcıya komut gönderir.

```shell
$ docker container exec <container_id> <command>
```

**docker container ls -a --no-trunc** : Tüm kapsayıcıları listeler ve id'leri tam olarak gösterir.

```shell
$ docker container ls -a --no-trunc
```

**docker container ls -a -q** : Tüm kapsayıcıların sadece id'lerini listeler.

```shell
$ docker container ls -a -q
```

**docker container ls -a -l** : Son oluşturulan kapsayıcıyı listeler.

```shell
$ docker container ls -a -l
```

**docker container ls -a --filter "status=exited"** : Durmuş kapsayıcıları listeler.

```shell
$ docker container ls -a --filter "status=exited"
```

**docker container logs** : Bir kapsayıcının loglarını gösterir.

```shell
$ docker container logs <container_id>
```

**docker container logs --tail** : Bir kapsayıcının loglarını belirtilen sayıda gösterir.

```shell
$ docker container logs --tail <number> <container_id>
```

**docker container attach** : Bir kapsayıcıya bağlanır ve logları gösterir.

```shell
$ docker container attach <container_id>
```

**docker container stop** : Bir kapsayıcıyı durdurur.

```shell
$ docker container stop <container_id>
```

**docker container start -a** : Durmuş bir kapsayıcıyı başlatır.

```shell
$ docker container start -a <container_id>
```

**docker container kill** : Bir kapsayıcıyı durdurur.

```shell
$ docker container kill <container_id>
```

**docker container inspect** : Bir kapsayıcı hakkında bilgi verir.

```shell
$ docker container inspect <container_id>
```

**docker container inspect grep** : Bir kapsayıcı hakkında bilgi verir ve içerisinde belirtilen kelimeyi arar.

```shell
$ docker container inspect <container_id> | grep <word>
```

**docker container rm** : Bir kapsayıcıyı siler.

```shell
$ docker container rm <container_id>
```

**docker container rm -f** : Bir kapsayıcıyı zorla siler.

```shell
$ docker container rm -f <container_id>
```

**docker container -d -p 5000:80 nginx** : Yeni bir kapsayıcı oluşturur ve portları bağlar.

```shell
$ docker container -d -p 5000:80 nginx
```

**docker container port** : Bir kapsayıcının portlarını gösterir.

```shell
$ docker container port <container_id>
```

**docker container -d -p 5000:80 --name webhost nginx** : Yeni bir kapsayıcı oluşturur, portları bağlar ve isim verir.

```shell
$ docker container -d -p 5000:80 --name webhost nginx
```

**docker container rename** : Bir kapsayıcının ismini değiştirir.

```shell
$ docker container rename <container_id> <new_name>
```

**docker plugin install** : Yeni bir eklenti yükler.

```shell
$ docker plugin install <plugin_name>
```

**docker plugin ls** : Yüklü eklentileri listeler.

```shell
$ docker plugin ls
```

**docker plugin enable** : Bir eklentiyi etkinleştirir.

```shell
$ docker plugin enable <plugin_name>
```

**docker plugin disable** : Bir eklentiyi devre dışı bırakır.

```shell
$ docker plugin disable <plugin_name>
```

## Docker Hub

Docker Hub, Docker'ın resmi bulut depolama hizmetidir. Docker Hub'da bulunan tüm imajlar, Docker'ın resmi depolama
hizmetidir.

**docker search** : Docker Hub'da arama yapar.

```shell
$ docker search <image_name>
```

**docker pull** : Docker Hub'dan bir imaj indirir.

```shell
$ docker pull <image_name>
```

**docker push** : Docker Hub'a bir imaj yükler.

```shell
$ docker push <image_name>
```

**docker login** : Docker Hub'a giriş yapar.

```shell
$ docker login
```

**docker logout** : Docker Hub'dan çıkış yapar.

```shell
$ docker logout
```

## Docker File Nedir?

Dockerfile, bir imaj oluşturmak için kullanılan bir metindir. Dockerfile'ın içerisinde imajın hangi işletim sistemi ile
oluşturulacağı, hangi paketlerin kurulacağı, hangi portların
açılacağı, hangi komutların çalıştırılacağı gibi bilgiler bulunur. Dockerfile'ın içerisindeki komutlar, imaj
oluşturulurken sırayla çalıştırılır.

### Docker File Komutları

**vim Dockerfile** : Dockerfile oluşturmak için kullanılır.

```shell
$ vim Dockerfile
```

**FROM** : Hangi işletim sistemi ile imaj oluşturulacağı belirtilir.

```shell
FROM <image_name>
```

**LABEL** : İmaj hakkında bilgi verir.

```shell
LABEL <key>=<value>
```

**MAINTAINER** : İmajı oluşturan kişiyi belirtir.

```shell
MAINTAINER <name>
```

**RUN** : İmaj oluşturulurken çalıştırılacak komutlar belirtilir.

```shell
RUN <command>
```

**CMD** : İmaj oluşturulduktan sonra çalıştırılacak komutlar belirtilir.

```shell
CMD <command>
```

**EXPOSE** : İmaj oluşturulduktan sonra hangi portların açılacağı belirtilir.

```shell
EXPOSE <port_number>
```

**ENV** : İmaj oluşturulduktan sonra hangi ortam değişkenlerinin tanımlanacağı belirtilir.

```shell
ENV <key>=<value>
```

**ADD** : İmaj oluşturulduktan sonra hangi dosyaların kopyalanacağı belirtilir.

```shell
ADD <source> <destination>
```

**COPY** : İmaj oluşturulduktan sonra hangi dosyaların kopyalanacağı belirtilir.

```shell
COPY <source> <destination>
```

**ENTRYPOINT** : İmaj oluşturulduktan sonra varsayılan olarak çalıştırılacak komut belirtilir.

```shell
ENTRYPOINT <command>
```

**VOLUME** : İmaj oluşturulduktan sonra hangi dizinlerin saklanacağı belirtilir.

```shell
VOLUME <directory>
```

**USER** : İmaj oluşturulduktan sonra hangi kullanıcı ile çalışılacağı belirtilir.

```shell
USER <user_name>
```

**WORKDIR** : İmaj oluşturulduktan sonra hangi dizinde çalışılacağı belirtilir.

```shell
WORKDIR <directory>
```

**MKDIR** : İmaj oluşturulduktan sonra hangi dizinlerin oluşturulacağı belirtilir.

```shell
MKDIR <directory>
```

**docker image build** : Dockerfile'ın içerisindeki komutları kullanarak imaj oluşturur.

```shell
$ docker image build -t <image_name> .
```

### Docker File Örnekleri

Ubuntu işletim sistemi ile imaj oluşturmak için Dockerfile'ın içerisine aşağıdaki komutları ekleyebiliriz.

```shell
FROM ubuntu                     // Ubuntu işletim sistemi ile imaj oluşturulur.
RUN apt-get -y update           // Ubuntu işletim sistemi güncellenir.
RUN apt-get -y install nginx    // Nginx paketi kurulur.
RUN apt-get -y install httpd    // Apache paketi kurulur.
```

## Docker Registry Oluşturma

Docker Registry, Docker imajlarını saklamak için kullanılan bir depodur. Docker Registry, Docker'ın resmi depolama
hizmetidir. Docker Registry'ye imaj yüklemek için Docker Hub kullanılabilir. Docker Registry'ye imaj yüklemek için
aşağıdaki komutları kullanabiliriz.

```shell
$ docker image tag <image_name> <registry_url>/<image_name>
$ docker image push <registry_url>/<image_name>
```

## Docker Volume Nedir?

Docker Volume, Docker Container'ın içerisindeki dosyaları saklamak için kullanılan bir depodur. Container'lar
silindiğinde Docker Volume'lar silinmez.

### Docker Volume Komutları

**docker volume create** : Docker Volume oluşturur.

```shell
$ docker volume create <volume_name>
```

**docker volume ls** : Docker Volume'ları listeler.

```shell
$ docker volume ls
```

**docker container run -it -v** : Docker Container'ın içerisindeki dosyaları Docker Volume'lar ile saklar.

```shell
$ docker container run -it -v <volume_name>:<container_directory> <image_name>
```

**docker volume inspect** : Docker Volume'lar hakkında bilgi verir.

```shell
$ docker volume inspect <volume_name>
```

**docker volume rm** : Docker Volume'ları siler.

```shell
$ docker volume rm <volume_name>
```

**docker volume prune** : Kullanılmayan Docker Volume'ları siler.

```shell
$ docker volume prune
```

### Docker Volume Dockerfile İçerisinde Kullanımı

Dockerfile'ın içerisinde Docker Volume kullanmak için aşağıdaki komutları kullanabiliriz.

```shell
FROM ubuntu                 // Ubuntu işletim sistemi ile imaj oluşturulur.
RUN apt-get update          // Ubuntu işletim sistemi güncellenir.
RUN app-get upgrade         // Ubuntu işletim sistemi güncellenir.
RUN app-get install nano    // Nano paketi kurulur.
RUN mkdir /data                 // /data dizini oluşturulur.
WORKDIR /data                   // /data dizini çalışma dizini olarak ayarlanır.
RUN echo "Hello World" > hello.txt    // hello.txt dosyasına "Hello World" yazılır.
VOLUME /data                       // /data dizini Docker Volume olarak ayarlanır.
```

## Docker Ağları

Docker Ağları, Docker Container'lar arasında iletişim kurmak için kullanılır.

### Docker Ağ Komutları

**docker network create** : Docker Ağı oluşturur.

```shell
$ docker network create <network_name>
```

**docker network ls** : Docker Ağlarını listeler.

```shell
$ docker network ls
```

**docker network inspect** : Docker Ağlar hakkında bilgi verir.

```shell
$ docker network inspect <network_name>
```

**docker network rm** : Docker Ağlarını siler.

```shell
$ docker network rm <network_name>
```

**docker network prune** : Kullanılmayan Docker Ağlarını siler.

```shell
$ docker network prune
```

**docker container run --network** : Docker Container'ı Docker Ağına bağlar.

```shell
$ docker container run --network <network_name> <image_name>
```

**docker container run --network-alias** : Docker Container'ı Docker Ağına bağlar ve Docker Ağına alias verir.

```shell
$ docker container run --network <network_name> --network-alias <alias_name> <image_name>
```

## Docker Compose Nedir?

Docker Compose, Docker Container'ları birlikte çalıştırmak için kullanılır.

### Docker Compose Komutları

**docker-compose --version** : Docker Compose'ın versiyonunu gösterir.

```shell
$ docker-compose --version
```

**docker-compose up** : Docker Compose ile Docker Container'ları çalıştırır.

```shell
$ docker-compose up
```

**docker-compose up -d** : Docker Compose ile Docker Container'ları arka planda çalıştırır.

```shell
$ docker-compose up -d
```

**docker-compose down** : Docker Compose ile çalıştırılan Docker Container'ları durdurur.

```shell
$ docker-compose down
```

**docker-compose ps** : Docker Compose ile çalıştırılan Docker Container'ları listeler.

```shell
$ docker-compose ps
```

### Docker Compose Dosya Yapısı

Docker Compose dosyası, Docker Container'larının çalıştırılması için gerekli bilgileri içerir. Docker Compose dosyası
aşağıdaki gibi oluşturulur.

```yaml
version: '3.8'          #Docker Compose dosyasının versiyonu belirtilir. 
services:               #Docker Container'larının bilgileri bu bölümde belirtilir.
  server_a:             #Docker Container'ın adı belirtilir.
    image: nginx:latest #Docker Container'ın imajı belirtilir.
    ports:              #Docker Container'ın portları belirtilir.
      - "8001:80"       #Docker Container'ın 8001 portu, bilgisayarın 80 portuna bağlanır.
```

