# Create a dataproc cluster

#  Insert your values in the <cluster-name>, <project-id>, and <bucket-name> placeholders.

gcloud dataproc clusters create <cluster-name> \
    --project <project-id> \
    --bucket <bucket-name>
    --initialization-actions \
        gs://dataproc-initialization-actions/jupyter/jupyter.sh


# Create an SSH tunnel

# Insert your cluster's zone and name in the <cluster-zone> and <cluster-name>placeholders, respectively

gcloud compute ssh --zone=<cluster-zone> \
  --ssh-flag="-D" --ssh-flag="10000" --ssh-flag="-N" --ssh-flag="-n" "<cluster-name>-m" &


# Configure your browser

# replace the <cluster-name> placeholder with the name of your cluster

# Browser executable path for ubuntu - /usr/bin/google-chrome

<browser executable path> \
    "http://<cluster-name>-m:8123" \
    --proxy-server="socks5://localhost:10000" \
    --host-resolver-rules="MAP * 0.0.0.0 , EXCLUDE localhost" \
    --user-data-dir=/tmp/


