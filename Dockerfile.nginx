ARG CLI_IMAGE
FROM ${CLI_IMAGE} as cli

FROM amazeeio/nginx-drupal

COPY .lagoon/drupal.conf /etc/nginx/conf.d/app.conf
RUN fix-permissions /etc/nginx/conf.d/app.conf

COPY --from=cli /app /app

# Define where the Drupal Root is located
ENV WEBROOT=web
