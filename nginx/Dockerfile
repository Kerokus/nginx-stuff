# Use the official Nginx image from Docker Hub
FROM nginx:alpine

# Remove the default Nginx configuration file
RUN rm /etc/nginx/conf.d/default.conf

# Copy your custom Nginx configuration file into the container
COPY default.conf /etc/nginx/conf.d/default.conf
COPY /certs/idsg.dev.svc.ac2sp.army.mil.crt /etc/nginx/certs/idsg.dev.svc.ac2sp.army.mil.crt
COPY /certs/idsg.dev.svc.ac2sp.army.mil.key /etc/nginx/certs/idsg.dev.svc.ac2sp.army.mil.key

# Expose port 80 to the host
EXPOSE 80
