#TODO change version after release
FROM consol/sakuli-ubuntu-xfce-java:v1.2.0-247-sakuli-se-SNAPSHOT

MAINTAINER Tobias Schneck "tobias.schneck@consol.de"
ENV REFRESHED_AT 2018-04-23

### Install gedit as test app
USER 0
RUN apt-get update \
    && apt-get install -y gedit \
    && apt-get clean -y
USER 1000

### Install webdriver
ENV WEB_DRIVER /headless/webdriver
#chrome
RUN mkdir $WEB_DRIVER && cd $WEB_DRIVER \
    && wget https://chromedriver.storage.googleapis.com/2.25/chromedriver_linux64.zip \
    && unzip *.zip && rm *.zip && ls -la
#firefox
#RUN wget -qO- https://github.com/mozilla/geckodriver/releases/download/v0.20.1/geckodriver-v0.20.1-linux64.tar.gz \
#    | tar xz -C  $WEB_DRIVER