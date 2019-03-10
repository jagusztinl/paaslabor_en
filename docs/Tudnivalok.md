# Knowledge

## VirtualBox Import

For home work, to complete the exercises, the virtual machine can be downloaded here (from BME network): curl -L0 http://ossrv1.aut.bme.hu/alerantbme_paaslabor_student_2019.ova

You also have a desktop on the desktop at C: VPCImages PAAS alerantbme_paaslabor_student_2019.ova

### Delete previous virtual machine
Carefully avoid erasing other virtual machines!

1. At workstation in VirtualBox, select AlerantBME_CentOS7 Delete / Delete Delete all files
2. On VirtualBox-> File-> Virtual Media Manager, check that the AlerantBME_CentOS7 disk does not exist, if it is there, delete it.

### Importing a virtual machine
1. Create the C: Work VirtualBox directory (if there is a virtual machine in it and there is no other virtual machine in it, delete it all)
2. In VirtualBox:
- Check File-> Preferences-> General-> Default Machince (File-> Preferences-> General-> Default Machine Folder) Folder: C: \ t
- Import Appliance: C: VPCImages PAAS alerantbme_paaslabor_student_2019.ova
- At the last step of the wizard, check to see if a good path has been entered

## VirtualBox CentOS Information
- Start the CentOS image in VirtualBox and work on it!
- CentOS Login: ** BME Paas user / password: paaslabor **
- sudo can be used (cautiously :))
- if you need some package on Linux: sudo yum install -y XXXXXXXX
- mount host host directory:
1. Create a folder (under machine shares) in Devices / Shared Folders in VirtualBox. host name
2. Then you can mount it in CentOS: sudo mount -t vboxsf host / media (host a share name)
- Firefox is the browser
- You should set the bidirectional clipboard in VirtualBox to make copy-paste work
- status and restart of services such as sudo systemctl restart NetworkManager
- Make a working library for yourself and work on it

## GitHub

Everyone must create a GitHub account or use the existing one!

1. https://github.com/
2. Sign Up
3. username pl. alerantbmexy, etc ...., you need to confirm your registration via email
4. Create a new project with GitHub-on start project, eg gyakorlat2

You can work in the ~ / git directory in CentOS image (there will be more projects)

Git Important Commands:
`` Shell
echo "# practice2" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/alerantbmexy/gyakorlat2.git
git push -u origin master
`` `

Here's how to clone examples in practice:
`` Shell
Example # Cloning Java OpenShift Wildfly Application
git clone https://github.com/bparees/openshift-jee-sample practice2
git pull https://github.com/bparees/openshift-jee-sample practice2

# Do not place it back in the original location, but under your own user
git remote set-url origin https://github.com/alerantbmenz/gyakorlat2.git

# modifications
git commit -a -m 'Some commit message'
# upload to the new location under our own account
git push origin master
`` `
You can now create a new proxy on your own code base based on your own GitHub URL.

Such is the directory structure:
`` Shell
[bmepaasuser @ localhost ~] $ tree git /
git /
└── practice2
    ├── pom.xml
    ├── README.md
    └── src
        └── main
            Va java
            ├── resources
            └── webapp
                ├── images
                │ └── jbosscorp_logo.png
                ├── index.html
                └── snoop.jsp

`` `


## DNS and hosts file
- Openhift applications core components are basically available with IP, but FQDNs are included in the / etc / hosts file
- Dnsmasqd is also installed on the machines, which also works with wildcard DNA, eg. XXX.apps.openshift.local also dissolves to the correct IP

dnsmasq config file: /etc/NetworkManager/dnsmasq.d

## IPs
`` Shell
192.168.30.11 bmepaas-master.openshift.local
192.168.30.12 bmepaas-node1.openshift.local
192.168.30.13 bmepaas-node2.openshift.local
`` `


## Contacts

## Docker Theme
- There are already Docker images on the local machine, you are trying to use it first and do not download new ones!

## OpenShift Theme
- Central OpenShift dashboard: https: //bmepas-master.openshift.local: 8443
- Starting local OpenShift: sudo systemctl start openshift

## Minutes

** Collect materials for the report (marked separately when what), to have all the information at the time of filling. **

# How can I try out at home?
Linux is a simpler but not exclusive platform!
## Virtual Machine
You can also take the virtual machine that is used in practice!
## Docker
- Install and play with it (for Linux via the package manager or [from] (https://store.docker.com/search?offering=community&type=edition) for all kinds of platforms)
- Or play with [online] (http://training.play-with-docker.com/)!
## Kubernetes
- Native Kubernetes installation on Linux
- [Minicube] (https://github.com/kubernetes/minikube)
## Openshift
- oc cluster up [here] (https://www.okd.io/)
- [Minishift] (https://github.com/minishift/minishift)
## Openshift course
- https://learn.openshift.com

## Useful links, blogs
- https://github.com/veggiemonk/awesome-docker
- http://www.opensourcerers.org/tag/openshift/
- http://training.play-with-docker.com/
- https://learn.openshift.com
