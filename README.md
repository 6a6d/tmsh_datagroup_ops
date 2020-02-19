# tmsh_datagroup_ops
tmsh script to add, edit, delete datagroup records

copy the script to a bigip hard drive and add to the configuration using this command:
  tmsh load cli script dg_records merge
  
Uage;

From TMSH on the BigIP:
    /cli
    run script dg-records “add-record URI_pool_mapping { /uri3 { data pool3 } }

From bash on the BigIP:
    tmsh run cli script dg-records “add-record URI_pool_mapping { /uri3 { data pool3 } }

Using Curl from any mahine via the REDT API:
    curl –kv –u admin:admin  https://localhost/mgmt/tm/ltm/script -X POST -H "Content-Type: application/json" -d { \
        ”name”: “dg-records”, \
        “command”:”run”, \
        “cmdUtilArgs”:”addrecord this_dg  name data” \
    }
