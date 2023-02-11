Server Full fix for SA-MP

It works. You can test it yourself with. look for a spoofer ;)

More specifically, the plugin protects requestsconnectioncookie and incomingconnection from flooding by spoofing ip addresses via ip spoofing (raw sockets) and without it. A plugin with a hook that filters connections in the early stages, even before OnIncomingConnection is called and after it OnPlayerConnect, although the plugin is old, it is exclusive. I assume that they earned money on it, so it was transferred by me only this year. However, the fact remains that it really helps. It has the property of intercepting and contributing, after which it processes the original samp hook. It's just perfect for those who understand... after all, without a valid connection, the raknet traffic will not go further if it is discarded. By level, this is almost the lowest hook, below it, only ProcessQueryPacket, which is responsible for processing and sending query traffic to the client (gives an answer).
server.cfg lick hides messages about cookies and incoming. The plugin does not allow fake connections from spoofing and subsequent raknet traffic to pass.

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
