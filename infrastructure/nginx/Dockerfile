# Use ultra-lightweight Nginx Alpine Base Image
FROM nginx:1.25-alpine

# Remove default configuration file
RUN rm /etc/nginx/conf.d/default.conf

# Copy custom configurations from repository
COPY nginx.conf /etc/nginx/nginx.conf
COPY conf.d/default.conf /etc/nginx/conf.d/default.conf

# Expose HTTP Edge Port
EXPOSE 80

# Built-in Container Healthcheck
HEALTHCHECK --interval=15s --timeout=3s --retries=3 \
  CMD wget --quiet --tries=1 --spider http://localhost/healthz || exit 1

# Start Nginx in foreground mode
CMD ["nginx", "-g", "daemon off;"]