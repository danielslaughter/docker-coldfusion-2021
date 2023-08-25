FROM ortussolutions/commandbox

# Update and install Apache; add settings
RUN apt-get update
RUN apt-get install apache2 vim -y
RUN mkdir -p /www/logs
RUN mkdir -p /www/gvsu

# Copy and enable localhost.conf; disable 000-default
COPY ./build/localhost.conf /etc/apache2/sites-available/localhost.conf
RUN a2ensite localhost.conf
RUN a2dissite 000-default

# Install Apache modules
RUN a2enmod headers
RUN a2enmod rewrite
RUN a2enmod proxy
RUN a2enmod proxy_http

# Start Apache when Commandbox starts
ENTRYPOINT service apache2 start && $BUILD_DIR/run.sh