# Set Default Namespace for Current Context
kubectl config set-context --current --namespace=roboshop

# kubectl config view --minify | grep namespace
kubectl config view --minify | grep namespace

# Set Namespace When Creating Resources (Alternative)
kubectl apply -f yourfile.yaml -n roboshop

# Inside your YAML manifest
metadata:
  namespace: roboshop

# See Your Current Context
kubectl config get-contexts

# Command to Show Current Namespace

kubectl config view --minify --output 'jsonpath={..namespace}'

kubectl config get-contexts

# install kubens
sudo git clone https://github.com/ahmetb/kubectx /opt/kubectx
sudo ln -s /opt/kubectx/kubens /usr/local/bin/kubens # This creates a symbolic link called /usr/local/bin/kubens that points to /opt/kubectx/kubens


# To list all namespaces:
kubens

# To switch to a specific namespace
kubens <namespace-name>


kubectl apply -k "github.com/kubernetes-sigs/aws-ebs-csi-driver/deploy/kubernetes/overlays/stable/?ref=release-1.43"

kubectl kustomize \
    "github.com/kubernetes-sigs/aws-efs-csi-driver/deploy/kubernetes/overlays/stable/ecr/?ref=release-2.1" > private-ecr-driver.yaml

# k9s
curl -sS https://webinstall.dev/k9s | sh