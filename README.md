[##### Slide for Presentation #####](https://speakerdeck.com/praparn/secure-and-monitor-your-service-connectivity-without-service-mesh-68ef2ad7-9a0e-4f50-a0ff-0967fb64a460)

#########################################################         
Demo Video                  
#########################################################

[Presentation Video](https://www.youtube.com/watch?v=jYtJVHCsKpw&t=9s)

[Part 1: Setup Cilium & Hubble](https://youtu.be/84PQ8bJV_tc)                
[Part 2: Deploy application with single namespace](https://youtu.be/FrUiqx7H3F4)                  
[Part 3: Deploy application with multiple namespace and apply security policy](https://youtu.be/ftA41oD6JXM)                  

#########################################################                  
 Instruction for Operate with Hubble/Cilium                                                                                                 
#########################################################

 Pre-requiste before start lab                                                                                                             
 1. Kubernetes farm without network "Pod network add-on" or remove this existing owner (Status will be not ready)                          
                                                                                                                                           
 2. Install cilium client (binary) for verify cilium status as detail below:                                                               
    "curl -L --remote-name-all https://github.com/cilium/cilium-cli/releases/latest/download/cilium-linux-amd64.tar.gz{,.sha256sum}"       
    "sha256sum --check cilium-linux-amd64.tar.gz.sha256sum"                                                                                
    "sudo tar xzvfC cilium-linux-amd64.tar.gz /usr/local/bin"                                                                              
    "rm cilium-linux-amd64.tar.gz{,.sha256sum}"                                                                                            
                                                                                                                                           
 3. Install hubble cli (binary) for track in command line with command below:                                                              
    "export HUBBLE_VERSION=$(curl -s https://raw.githubusercontent.com/cilium/hubble/master/stable.txt)"                                   
    "curl -L --remote-name-all https://github.com/cilium/hubble/releases/download/$HUBBLE_VERSION/hubble-linux-amd64.tar.gz{,.sha256sum}"  
    "sha256sum --check hubble-linux-amd64.tar.gz.sha256sum"                                                                                
    "sudo tar xzvfC hubble-linux-amd64.tar.gz /usr/local/bin"                                                                              
    "rm hubble-linux-amd64.tar.gz{,.sha256sum}                                                                                             
                                                                                                                                           
 4. Install helm for package management with command below:                                                                                
    "curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3"                                      
    "chmod 700 get_helm.sh"                                                                                                                
   ./get_helm.sh                                                                                                                               
###########################################################                  
 Example of Kubernetes Farm in Lab:                                                                
 :~$kubectl get node                                                                                                                       
 NAME                                             STATUS     ROLES                  AGE   VERSION                                          
 ip-X-X-X-X.ap-southeast-1.compute.internal    NotReady   worker                 27d   v1.22.1                                          
 ip-X-X-X-X.ap-southeast-1.compute.internal    NotReady   control-plane,master   27d   v1.22.1                                          
 ip-X-X-X-X.ap-southeast-1.compute.internal    NotReady   control-plane,master   27d   v1.22.1                                          
 ip-X-X-X-X.ap-southeast-1.compute.internal    NotReady   control-plane,master   27d   v1.22.1                                          
 ip-X-X-X-X.ap-southeast-1.compute.internal    NotReady   worker                 27d   v1.22.1                                          
 ip-X-X-X-X.ap-southeast-1.compute.internal    NotReady   worker                 27d   v1.22.1                                          
###########################################################                  
