Instalacion de docker en Linux

https://www.hostinger.co/tutoriales/como-instalar-y-usar-docker-en-ubuntu/


Instalacion y consumo de rabbitMQ

https://www.jorgehernandezramirez.com/2017/05/04/rabbitmq-instalacion-en-docker-y-conexion-desde-springboot/


Instalacion de Balanceador de Carga

https://clouding.io/hc/es/articles/360010289000-Balancear-servicio-web-con-HAProxy-en-Ubuntu-18-04

datos para estaus
 http://IP_Publica_HAProxy:8083/stats, nos pedirá usuario y contraseña, indicaremos haproxy y balanceador.
 
 
 Arrancar XAMPP
 Sudo /opt/lampp/lampp start
 
 Puesto de estatus del balanceador
 0.0.0:80863/stats
 
 Iniciar o reiniciar balanceador
 systemctl restart haproxy
 
 
 Instalar XAMPP
 https://www.apachefriends.org/es/index.html
 
 
 
 Configuraciòn balanceador
 https://clouding.io/hc/es/articles/360010289000-Balancear-servicio-web-con-HAProxy-en-Ubuntu-18-04
 
 
 listen balanceador
	bind *:80
	mode http
	stats auth cda:cda
	balance roundrobin
	server frontend-01 192.168.0.111:80 check maxconn 4000 fall 3
	server frontend-02 192.168.0.112:80 check maxconn 4000 fall 3
	server frontend-03 192.168.0.113:80 check maxconn 4000 fall 3
	server frontend-04 192.168.0.114:80 check maxconn 4000 fall 3

listen stats
	bind *:8083
	mode http
	stats enable
	stats uri /stats
	stats realm HAProxy\ Statistics
	stats auth haproxy:balanceador
 



MInio:
wget https://dl.min.io/server/minio/release/linux-amd64/minio
chmod +x minio
./minio server /mnt/data

https://www.digitalocean.com/community/tutorials/how-to-set-up-an-object-storage-server-using-minio-on-ubuntu-18-04-es


LDAP:
http://somebooks.es/12-7-instalar-y-configurar-openldap-en-el-servidor-ubuntu/


http://www.mastertheboss.com/jboss-server/jboss-security/configuring-ldap-based-authentication-with-elytron-on-wildfly

e1NTSEF9czIxUGY3WGxBMTVNNjN6VFdweU5abzdWSVJ2M1RKamc=

