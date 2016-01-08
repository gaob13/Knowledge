#PG::Error could not connect to server: Connection refused 
    Is the server running on host "localhost" ( 127.0.0.1 ) and accepting 
    TCP / IP connections on port 5432 ?

This can happen, if you didn’t configure your server specifically. 
To see if your Postgresql is accepting requests, simply run the following command in your terminal:

 
    [x]psql - h localhost mydb
To resolve this issue, follow the next steps. 

[x]The first step is to modify postgresql.conf 
Locate “ listen_addresses ” in your configuration and cange its value from

    'localhost'
    to 
    '*'

Now postgresql server will accept all kinds of connections, instead of just loop-back connections.

[x]Now we have to modify pg_hba.conf 
Open it with your favorite editor and search the following line

1 
    
    host    all             all             127.0.0.1 / 32            trust
    
Change 
    
    127.0.0.1/32 
    into 
    0.0.0.0/0 
    
to accept connections from all hosts.

We now have to restart our postgresql server. Open your terminal and enter:

1 
    
    [x]psql - h localhost mydb
    
Keep on hacking ;-)
