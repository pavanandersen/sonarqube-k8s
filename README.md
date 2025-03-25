# sonarqube-k8s

helm repo add sonarqube https://SonarSource.github.io/helm-chart-sonarqube
helm show values sonarqube/sonarqube  > values.yaml
helm repo update
kubectl create namespace sonarqube
helm upgrade --install -n sonarqube sonarqube sonarqube/sonarqube -f values.yaml

MUDAR NO VALUES O VALOR "community.enable" PARA "true" e descomentar "monitoringPasscode"

kubectl port-forward sonarqube-sonarqube-0 :9000 

INSTALAR sonar-scanner

sudo apt update
sudo apt upgrade -y
sudo apt install openjdk-11-jdk -y
java -version
cd /opt

BAIXE O ARQUIVO ZIP DO SITE PARA /opt/

sudo unzip (extraia o arquivo)
sudo mv sonar-scanner-4.7.0.2747-linux sonar-scanner
vim  ~/.bashrc

ADICIONE A ULTIMA LINHA

export PATH=$PATH:/opt/sonar-scanner/bin

REINICIE O BASH

source ~/.bashrc

sonar-scanner --version

