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
                           |       Resorces Controll (cotains Node Controller)
                           |
                           |
                           
                       Event Listener (by Scheduler)
                         
                    
                    
                * etcd: to save status of node
                
                * code API Server: the core of K8s, it has many modules that provide services, and
                                   every module has its own memory to save status.
                
                * Kuberlet: a software that install in node, communicating with core API Server.
                
                * Resources Controll: such as Controller Manager.
                
                * Event Listner: by Scheduler.
                

