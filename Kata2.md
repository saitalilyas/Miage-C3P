# Mars Rover Extension

Time passes and Nasa got new requirements.
Please take any of them and address them. 


## New Requirements

### Natural 1-based numbering.

NASA engineers discovered that Pharo collection where the first element of an array is 1 and not 0, is way better than 0-based indexing. So they decided to clean their implementation.

The following 

```
3 3 
1 1 N 
```

means that the robot is on the first cell heading N and not the second diagonal one. 

### Rover should not get over the grid border. 
NASA discovered that if a rover gets off the grid it loses the signal reception and get lost because of unreachable. 

Therefore a rover should never move out of the grid in case of move to a cell out of the grid it should act as if the move has been done. 

```
3 3
0 0 N

```

### Rover walks back.

NASA added a nice feature it can ask any rover to go walk back some steps.

- `B` ask the robot to move in reverse direction.

```
5 S
1 2 N
LMMB
```

### Rover walk recording.

NASA wants to analyse the real path the rover did. Indeed, since the communication can be corrupted or when the rover may bump into another one, or when it may cross the edge of the grid, it skips the move. 
Therefore this is important to be able to request a rover for its walk recording. For this we need a new message reCording. 

The following is an example
```
5 5
1 2 N
RMM
C
should return the list ((1 2) (2 2) (3 2)
```


### More robust communication.

- NASA communication can get corrupted and we will get wrong formatted code as input.

The following is an example
```
5 S
1 2 N
LNLMLMLMM
```

The rover should validate the input before executing. 

### Error correction.

NASA decided to enhance its protocol and send lists of possible corrections. 
In the following the two first lines indicates that in case of wrong communication any S in grid specification should be turned into a 5 and 
any N in the movement specification should be turned into an M. 

```
S -> 5
N -> M

5 S
1 2 N
LNLMLMLMM
```

### Rover should not bump in each other. 

NASA wanted to optimize the time for the rovers to a task and decided to execute Rover actions one after the other and not the full sequence of move at one.  But doing so Nasa discovered that the rovers can crash into each other
when their paths are crossing. 

Fix this. If a rover sees that the cells where it should move it is occupied,  it should not move there

### JSON attacks

- Nasa decided to upgrade the communication and now we can have different medium 

		1 2 N 
		

	- The nasa wants to replay the play.

	- 

