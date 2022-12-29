docker build -t jenkins2 -f master/Dockerfile .

$docker run --name=jenkins-data jenkins-data
$docker run -p 8080:8080 -p 50000:50000 --name=jenkins-master --volumes-from=jenkins-data -d jenkins2
$docker exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword
