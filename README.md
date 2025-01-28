# OTUS.Lesson19.Docker  
1) Установим Docker + Docker Compose (https://docs.docker.com/engine/install/debian/)  
  
# Add Docker's official GPG key:  
sudo apt-get update  
sudo apt-get install ca-certificates curl  
sudo install -m 0755 -d /etc/apt/keyrings  
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc  
sudo chmod a+r /etc/apt/keyrings/docker.asc  
  
# Add the repository to Apt sources:  
echo \  
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \  
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \  
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null  
sudo apt-get update  
  
# Install latest version:  
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin  
  
2) Скачаем контейнер и запустим его на 80 порту:  
	docker pull zhyrkin/otus-nginx  
	docker run  -d -p 80:80 zhyrkin/otus-nginx  
	  
3) Образ - это шаблон, на основе которого создается контейнер, существует отдельно и не может быть изменен.  
Контейнер Docker - это виртуализированная среда выполнения, в которой пользователи могут изолировать приложения от хостовой системы.  
  
4) Ответьте на вопрос: Можно ли в контейнере собрать ядро?  
	Нет, потому что Docker использует ядро хостовой системы.
