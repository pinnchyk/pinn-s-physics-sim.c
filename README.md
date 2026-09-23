# pinn-s-physics-sim.c

███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████
███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████
██████████████████████████████████████████████▛░░▀██████████████████▀▀▀▜██▛▀░░▐████████████████████████████████████████
████████████████▛▀▀▀██████████████████████████▌░░░██████████████████░░░▐██▌░░░▐████████▛▀▀▀████████████████████████████
███████████████▙▖░░░██████████████████████████▙░░█████████████████▛▀░░░▝▀▜▌░░░▐███████▙▖░░░████████████████████████████
███▛▘░░░▀▜███████▙▄███▛▀▀▀██▀▜█████▀▀▀▜█▀▀████████████▀▀▀▀▜███████▙▄░░░▗▄▟▌░░░▐█▛▀██████▙▄███▛▀▀▀██▀▜█████████▀▀▀▜█████
███▌░░░░░░░░▀███▌░░░██▌░░░░░░░░▝▜██░░░░░░░░▝▜███████▛▘░░░▗▄▟████████░░░▐██▌░░░░░░░░░███▌░░░██▌░░░░░░░░▝███▛▘░░░░░░▝▜███
███▌░░░░▙▖░░░░██▌░░░██▌░░░░▄░░░░▐██░░░░▗░░░░▐██████▌░░░░████████████░░░▐██▌░░░░▗▖░░░░██▌░░░██▌░░░░▄░░░░███░░░▗▄█░░░▐███
███▌░░░░██▌░░░██▌░░░██▌░░░███░░░▐██░░░▐██░░░▐██████▙▖░░░░▜██████████░░░▐██▌░░░▐██▌░░░██▌░░░██▌░░░██▌░░░██░░░▗▟██░░░▐███
███▌░░░░█▛▘░░░██▌░░░██▌░░░███░░░▐██░░░▐██░░░▐████████▙▄░░░░▐████████░░░▐██▌░░░▐██▌░░░██▌░░░██▌░░░██▌░░░██░░░▐██▀░░░▐███
███▌░░░░▘░░░░▄██▌░░░██▌░░░███░░░▐██░░░▐██░░░▐██████████▀░░░▗▟███████░░░▐██▌░░░▐██▌░░░██▌░░░██▌░░░██▌░░░██░░░░▝░░░░░▐███
███▌░░░░░░▗▄████▌░░░▀█▌░░░███░░░▐██░░░▐██░░░▐██████▛▀▀░░░░▗▟████████░░░▝▜█▌░░░▐██▌░░░██▌░░░▀█▌░░░██▌░░░███▖░░░░░░░░▐███
███▌░░░░████████▙▄▄▄██▄▄▄▟███▄▄▄▟█▄▄▄▟███▄▄▄▟██████▙▖░░▄▄▟██████████▄░░▄▟█▙▄▄▄███▙▄▄▄██▙▄▄▄█▙▄▄▄███▙▄▄▄█████████░░░▐███
███▌░░░░███████████████████████████████████████████████████████████████████████████████████████████████████████░░░░▐███
███▌░░░░█████████████████████████████████████████████████████████████████████████████████████████████████████▛░░░░▐████
███▌░░▄▄██████████████████████████████████████████████████████████████████████████████████████████████████▙▖░░░░░▟█████
███████████████████████████████████████████████████████████████████████████████████████████████████████████▙▄▄▄████████
███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████
███████████████████████████████████████████████████████████████████████████████████████████████████████████████████████
(ye, this cool ASCII art thingie was made by me using a programme of mine, you can check it out too, should be uploaded and free to use)

A personal project of mine, initially inspired by webgoatguy's video on Particle Life, a web simulator of simplified "life" using particles that follow certain rules when interacting with one another. 
Written in C (yes, not the best choice of language, I realize that a bit late) after getting it taught to me during my last year of highschool.
At the moment of first upload (23/09/2026, august 31st version), it only supports simulating electrically charged particles. Program's basic functions include: creation of particles inside the simulation and modification of their properties and variables (velocity, position, charge, mass), copying said particles any (positive integer) number of times, visual display of the particles, pausing and unpausing simulation. Full list of commands as for now:

========================

[pinn_physics_sim.c]: List of commands:

   Basic commands:
     exit - Exit the program (recommended over simply closing the window to avoid possible memory leaks; this code is very mediocre, alright?)
     pause - Toggle pause
     launch - Launch the simulation (with customizable dimensions; 600x600px by default)
     terminate - Terminate the simulation
   Particle management:
     newParticle - Create a new particle in the simulation
     copyParticle - Make exact copies of a particle of choice
     particleList - List all particles in the simulation
     particleCount - List current number of particles in the simulation
     particleInfo - List data of a specific particle
     particleMod - Modify a variable of a specific particle
     particlesDistance - Calculate the distance between two given particles
   Simulation rules:
     setFriction - Set the friction constant (default = 5 px/s; one second  => -5 px/s)
     setTickSpeed - Set the speed of one tick (default = 0.016 s; ~60 TPS)
   VFX:
     particleUnivSize - Modify the size of all particles in the simulation (10x10px by default)
     grid - Toggle grid visibility (ON by default)
     gridSpeed - Modify grid's oscilation speed (0 by default)

========================

You might've noticed, but these are written commands, and yes, the way you interact with the simulation is via typing out commands in the console, since well I haven't got any experience with GUIs, okay? Example of a command structure for you to have some understanding: newParticle [initial X position] [initial Y position] [particle type (type 0 by default)] [initial X velocity] [initial Y velocity] [charge(if type 0)]. Type of the particle is a variable left for future implementation, where type 0 particles are the ones available right now, the electromagnetic particles, and all other integers will be specific particle types just like the different colored particles in previously mentioned Particle Life website, which will have specific rules of attraction and repellence they'd follow when interacting with others. The program as of now is pretty much a framework for the actual idea that kickstarted it. When will I finish it?

hell if i know

Hope you'll enjoy the simulation though.
