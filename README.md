# kvraft #
## overview ##
Based on raft-protocol and leveldb, implement a simple but strong consistency distributed kv storage system.</br>
Only for sutdy, not business.

## Building ##
1 Install **levigo**

Refer to https://github.com/jmhodges/levigo

2 Install **kvraft server**
<pre><code>$ go install kvraft
</code></pre>
	
3 Install **kvraft-cli**
<pre><code>$ go install kvraft/cli
</code></pre>

## usage ##
1 **Run server**

must greater than three instances
<pre><code>$ kvraft config.json
config_example.json
{
    "local":{
        "server_id":1,
        "endpoint":"127.0.0.1:30261"
    },
    "peers":[
        {
            "server_id":2,
            "endpoint":"127.0.0.1:30262"
        },
        {
            "server_id":3,
            "endpoint":"127.0.0.1:30263"
        }
    ],
    "dbpath":"/path/to/leveldb/store"
}
</code></pre>
2 **Run client**
<pre><code>$ cli ip:addr
connect any instace of cluster
</code></pre>

