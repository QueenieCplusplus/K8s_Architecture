# K8s_Architecture
K8s 架構圖




                        etcd (log) 
                        
                         |
                         |
                        _|_________________                    
                       |                  |  ----- get ------  ____ Node____   
                       |  Core API (Auth) |  ----- list -----  |  Kuberlet |
                       |__________________|                    -------------
                           |           |
                           |           |
                           |           |
                           |           
                           |       Resorces Controll
                           |
                           |
                           
                       Event Listener (by Scheduler)
                         
                    
                    
                * etcd: to save status of node
                
                * code API Server: the core of K8s
                
                * Kuberlet: a software that install in node, communicating with core API Server.
                
                * Resources Controll: such as Controller Manager.
                
                * Event Listner: by Scheduler.
                
