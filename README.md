# BOTS CHALLENGE (BC-GENERIC)
## What are the BCs?
BCs are challenges for programmers, where the players are controlled by a bot written by them.
The goal of these type of videogames is to satisfy the programmes for coding their bot.
The second goal is to challenge other programmers and to learn their algorithm and thinking.
## How can I play a BC?
You need to have a controller and one or two bots which communicates with the same protocol and plays the same game. This project is a generic implementation fo BC's controller. It doesn't support any game and it's inteded to be used as base for any other project.
## What is this project?
This is a project that contains a generic controller, a testing bot, a fake testing bot, a generic lib for the controllers and the bots, the documentation about the lib, the controller and the protocol and the utilities to start the controller/AI. All components of the project are written in C++ with the help of QT lib.
## Which are the system operating supported by this project?
This project uses C++/QT and support all operating system.
## How does it work?
The components follow these algorithm.
1) The user starts the script `script/run.sh` or `script/run.bat`.
2) The script runs its initialization algorithm (for example parsing arguments, reading level file, creating output/log files, ...).
3) The script starts asynchronously the controller and wait few seconds.
	1) The controller runs its initialization algorithm (ex: parse the command line arguments, read level files, read configuration files, setup communication system, ...).
	2) The controller starts its communication system.
	3) The controller waits the bots.
	4) The controller ask to bots to initialize the AI.
	5) The controller starts and finishes to coordinating the challenge.
	6) The controller inform the bots that the challenge is finished.
	7) The controller runs its post-game algorithm (like saving the status of the challenge).
	8) The controller finish to work.
4) The script starts asynchronously the bots and pass them the socket of the server.
	1) The bots runs their initialization algorithm (ex: parse the command line arguments, setup remote procedure system, read configuration file, init its AI algorithm, ...).
	2) The bots connect to the controller.
	3) The bots start and finish to run the operations asked by the controller. 
5) The script Waits the end of controller.
6) The script runs its post-execution algorithm (for example writing result/output/log, sending result, ...).

