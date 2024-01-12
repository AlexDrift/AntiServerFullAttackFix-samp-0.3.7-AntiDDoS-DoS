Server Full fix for SA-MP

It works. You can test it yourself with. look for a spoofer ;)


Protection against sampst, sampstu, sampstm, sampstuf, sampsu and their analogues. 
More specifically, the plugin protects against flooding [connection]36.72.108.25:17273 requests connection cookie. and [connection]incoming connection: 127.0.0.1:50222 id: 0 by spoofing ip addresses via ip spoofing(raw sockets) and without it. 
My version (no complaints) The hook is working, all addresses are fully updated. There are problems with the Windows version of the plugin, which is not critical. The Linux version is fully stable and ready for use. 
Version 0.3.7-R2-2 is a plugin with a hook that filters connections in the early stages, even before public OnIncomingConnection is called and after it public OnPlayerConnect, although the plugin is old, it is exclusive. I assume that they earned money from it, so it was transferred by me only this year. However, the fact remains that it really helps. It has the ability to intercept and contribute, after which it processes the original samp hook. It's just perfect for those who understand... after all, without a valid connection, RakNet traffic will not go further if it is discarded. 
By level, this is almost the lowest hook, below it, only ProcessQueryPacket, which is responsible for processing and sending query traffic to the client (gives an answer). server.cfg lick hides messages about cookies and incomming. The plugin prevents fake connections from spoofing and subsequent RakNet traffic from passing through. Do not believe people that the plugin is allegedly not stable, it has been tested on high online and installed on some large mobile projects, including on the RDS server where online reaches 100-140 players. The plugin will help, but you will need hosting with basic traffic filtering, or in Russian, with basic protection. If you install it on a bare VDS or noob hosting, the plugin will protect the server, but the VDS channel will form (If an attack suddenly begins). 
Recommended hosting services: ruhoster, myarena, stormwall, frame-host, ddos guard (no longer marketing). More specifically, the plugin protects at the level of the RakNet network engine, but not as it will not protect your hosting, only partially. The plugin's source code is also present. 

Tags: SAMP AntiDDoS/DoS, AntiDDoS/DoS SAMP, SAMP AntiDDoS, AntiDDoS SAMP, AntiServerFullAttackFix, RaknetIPWhiteList


----

Installation

Linux:

    download archive
    unzip master.zip
    cd ./AntiServerFullAttackFix-master
    make AntiServerFullFix

Now copy the AntiServerFullFix.so file to your server plugins folder, add it to the server.cfg on the plugins line (order doesn't matter) and your server will be protected.

Windows:

    Open the solution with Visual Studio 2013 (express is fine) and hit "Build Solution"

Now copy the Release/AntiServerFullFix.dll file to your server plugins folder, add it to the server.cfg on the plugins line (order doesn't matter) and your server will be protected.

Notes:

    If your players keep timing out make sure to define (or undefine, whichever is appropriate) [AntiServerFullAttack.cxx::88]

		//enable/disable (whichever is appropriate) this definition if you have problems with players losing randomly connection
		#define REQUIRE_BYTESWAP

    This will fix issues with players losing connection to your server

    CentOS and Fedora (RedHat based systems) Users: Your operating system enforces security protections which also prevent memory hacking (which this plugin does).
    You need to disable setenforce on your system (setenforce 0).
