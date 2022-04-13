# Setting up the development environent

## 1.  Install pre-requisites : 
> 1. `nodejs==v12.19.0`
> 2. `mongodb`

## 2.  Install atom : 
> `git clone https://github.com/footlooselabs/atom.js` <br/>
> `cd <./atom.js> &&  ./install.sh`


## 3.  Install agents (micro-services) : 
> `git clone --single-branch --branch rpi <repo-url> <recommended_name>` <br/>
> <i>(clone the `rpi` branch of the following)</i> <br/><br/>
> <i><span style="color:blue">recommended_name</span> : `<repo_url>` --></i> <br/><br/>
> 1. <span style="color:blue">rtc_webrequest_handler: </span> `https://bitbucket.org/footlooselabs/request_handler` <br/>
> 2. <span style="color:blue">ror_agent:</span> `https://bitbucket.org/drona-footloose/drona-ror-agent` <br/>
> 3. <span style="color:blue">fsm_agent:</span> `https://github.com/FootLooseLabs/atom.fsm` <br/>
> 4. <span style="color:blue">ror_taskspace:</span> `https://bitbucket.org/footlooselabs/drona.ror-interface` <br/>
> 5. <span style="color:blue">store_execution_agent:</span> `https://bitbucket.org/footlooselabs/drona.operator_backend_node` <br/>


## 4.  Run atom daemon : 
> `sudo atom -s`

## 5.  Start the agents :
> `cd <./agent_dir> && sudo npm run start ∀ the above 5 agents`

------------------------

## 6.  Verify if everything has properly started :
Check if all the processes are running - <br/>
> `sudo pm2 ls`<br/><br/>
Check if all the processes are communicable - <br/>
> `sudo atom -ss`<br/><br/>
Verify if there are no other errors - <br/>
> `sudo pm2 log`<br/><br/>