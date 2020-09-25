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
                


K8s Process

    (1) Event Listener listens status of Node, and log it.

    (2) API call relative method for the resorce to Pod depends on (1).

    (3) Node using get/list method to have result of Pod from API, and to do relative task to Pod Instance.

Queenie 小心得

    其實 K8s API 就像是陳時中和唐鳳，某 pod 像是口罩或口罩供應服務，而 Node 像是藥局，
    陳與唐針對（聆聽到社會上的）口罩供給狀態與防疫狀況頒布即時的規範（例如對口罩提供何種資源物件），
    而 Node 藥局（在聆聽陳與唐的規範後）對 pod 口罩實例作出相應行為。


