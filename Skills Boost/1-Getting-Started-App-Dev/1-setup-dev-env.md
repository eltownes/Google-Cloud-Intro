### notes

* create VM via GC console
  * Allow full access to all Cloud APIs
  * Allow HTTP traffic

* SSH into VM
  * ```
    sudo apt-get update
    ```
  * ```
    sudo apt-get install -yq openjdk-11-jdk
    ```
  * jdk cert
    * ```
      sudo sed -i 's/^\(keystore\.type\s*=\s*\).*$/\1jks/' \
        /etc/java-11-openjdk/security/java.security; \
      sudo rm /etc/ssl/certs/java/cacerts; \
      sudo /usr/sbin/update-ca-certificates -f
      ```
  * ```
    sudo apt-get install git -y
    ```
  * ```
    sudo apt-get install -yq maven
    ```
  * IP tables
    * ```
      sudo iptables -t nat -A PREROUTING \
        -p tcp --dport 80 \
        -j REDIRECT --to-port 8080
      ``````
  * ```
    export GCLOUD_PROJECT="$(curl -H Metadata-Flavor:Google \
    http://metadata/computeMetadata/v1/project/project-id)"
    ```

* Verify
  * `java -version`
  * ```
    git clone --depth=1 https://github.com/GoogleCloudPlatform/training-data-analyst
    ```
  * simple nav
    * ```
      ln -s ~/training-data-analyst/courses/developingapps/v1.3/java/devenv ~/devenv
      ```
    * ```
      cd ~/devenv
      ```
    * ```
      mvn clean install
      ```
    * ```
      mvn spring-boot:run
      ```
 
* From GC console launch external ip 

* SSH
  * ```
    mvn exec:java@list-gce
    ```





