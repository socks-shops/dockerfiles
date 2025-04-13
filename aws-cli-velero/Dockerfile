FROM alpine:3.19

# Install curl and unzip
RUN apk add --no-cache curl unzip

# Set Velero version
ENV VELERO_VERSION=v1.12.3

# Download and install Velero
RUN curl -L https://github.com/vmware-tanzu/velero/releases/download/${VELERO_VERSION}/velero-${VELERO_VERSION}-linux-amd64.tar.gz \
    | tar -xz && \
    mv velero-${VELERO_VERSION}-linux-amd64/velero /usr/local/bin/velero && \
    rm -rf velero-${VELERO_VERSION}-linux-amd64

# Installer AWS CLI v2
RUN curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" \
    && unzip awscliv2.zip \
    && ./aws/install \
    && rm -rf awscliv2.zip aws/

# Set default command to shell
CMD ["sh"]
