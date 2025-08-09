# renovate: datasource=docker depName=intel/intel-extension-for-pytorch
FROM intel/intel-extension-for-pytorch:2.7.10-xpu

# Set paths to use with sdnext
ENV SD_DATADIR="/mnt/data"
ENV SD_MODELSDIR="/mnt/models"

# Download the SDNext repository
RUN cat <<EOF > /bin/startup.sh
#!/bin/bash
git status || git clone https://github.com/vladmandic/sdnext.git .
python /app/launch.py "\$@"
EOF

# Make the startup script executable
RUN chmod 755 /bin/startup.sh

# Set the working directory to /app
WORKDIR /app

# Run SDNext with custom parameters
CMD [ "startup.sh", "-f", "--use-ipex", "--uv", "--listen", "--debug", "--api-log", "--log", "sdnext.log" ]
