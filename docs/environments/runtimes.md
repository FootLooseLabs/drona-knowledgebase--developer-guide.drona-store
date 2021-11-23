
##Env Vars

###@drona.ror_executionspace

###@drona.ror_agent
```
DATABASE_URL="mongodb://127.0.0.1:27017/drona-ror-agent"
OPERATION_MAX_EXE_TIME=120000 

LOCAL_MODBUS_HOST="127.0.0.1"
LOCAL_MODBUS_PORT=502
LOCAL_MODBUS_ID=1

PLC_HOST="192.168.0.12"
PLC_PORT=502
PLC_ID=255
```


###@drona.ror_taskspace
```
 DATABASE_URL="mongodb://127.0.0.1:27017/drona-store-execution-agent-db"
 JOB_MAX_EXE_TIME=50
 JOB_MAX_PENDING_TIME=900
 JOBSPACE_VISIBILITY_DURATION=1800
```

##@drona.store_execution_agent

###Env Vars
```
 DATABASE_URL="mongodb://127.0.0.1:27017/drona-store-execution-agent-db"
```