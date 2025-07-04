Cyber Tralala - WRO Future Engineers 2025
====

We are Cesar Escarra, Diego Concepcion and Christopher Vazquez. We are students from Thomas Jefferson School Of Panama and we are the members of the team Cyber Tralala that competes in the WRO 2025 Future Engineers Category. In this Repository, we share all the information of our project.  

Somos Cesar Escarra, Diego Concepcion y Christopher Vazquez. Somos estudiantes del Thomas Jefferson School y conformamos el equipo Cyber Tralala que participa en la categoria de futuros ingenieros de la WRO. En este repositorio compartimos toda la informacion de nuestro proyecto.  

All parts of this repository are available in English and Spanish for a better understanding of it.  

Todas las partes de estes repositorio estan disponibles tanto en Ingles como en Español para una mejor comprehension del mismo.  
  
## Content/Contenido 

* `t-photos` contains 2 photos of the team . Contiene las fotos de nuestro equipo.
* `v-photos` contains photos of the vehicle. Contiene las fotos de nuestro vehiculo.
* `video` contains the video.md file with the link to a video where driving demonstration exists. Contiene los archivos con links a videos de youtube con el funcionamiento del robot.
* `schemes` contains one schematic diagrams in form of PNG and Fritzing of the electromechanical components illustrating all the elements (electronic components and motors) used in the vehicle and how they connect to each other. Contiene un diagrama electromecanico en formato PNG y Fritzing ilustrando todos los componentes usados en el vehiculo y sus debidas conexiones.
* `src` contains code of control software for all components which were programmed to participate in the competition. Contiene la programación usada en nuestro vehiculo para participar en la competencia.
* `models` is for the files for models used by 3D printers produce the vehicle elements. Contiene los modelos 3D utilizados para imprimir piezas para nuestro vehiculo.
* `other` is for other files which can be used to understand how to prepare the vehicle for the competition. It includes datasets, hardware specifications, communication protocols descriptions, links for buying, etc. Contiene especificaciones de hardware, protocolos de comunicacion, links de compra y otros.  
  
## How does our robot work?

Mobility management

We decided to use a rear-wheel drive remote control car as the basis for our project. A remote control car provides a fairly resistant chassis in addition to bringing 6v motors for movement and direction, allowing us high speed if necessary. The steering of our car consists of a direct current motor which operates a rack and pinion system to give direction to the front axle. Many cuts were made to the original chassis to be able to remove the original circuits and place our circuits without modifying the original aesthetics of the car much, but this part can be skipped and simply use the chassis without the outer casing, thus having a lot of free space.

Power and sense management/Power and sense management

For this project we decided to eliminate the car's original power source which was AA batteries and use 18650 lithium ion batteries because they have a much greater discharge capacity than AA batteries, in addition to having more capacity. These batteries are widely used from flashlights to electric vehicles, this way we ensure that it is easy to get chargers and spare parts.

Obstacle management

For this project we decided to use hc-sr04 ultrasonic sensors because they are cheap, easy to obtain and have fairly low consumption. We are using two sensors, one on each side, to detect the distance to the walls on the sides so that we can make corner turns and stay without crashing in the open challenge. In the case of the obstacle challenge, the sensors still play a secondary role in helping to turn and prevent the car from crashing into walls.

For obstacle management we decided to use a Huskylens camera. This camera is very intuitive to use and has artificial intelligence which helps with detection, in this case of colors. The camera provides very good integration with the Microbit platform in addition to the ability to program new colors in just seconds.

Open Challenge Programming

To program the open circuit, we use simple programming based on the two ultrasonic sensors. First, the ultrasonic variable and the elapsed time in the loop are established to have a constant reading, a conditional is placed to activate the H-bridge so that the rear motor goes forward with a constant speed until the elapsed time is the equivalent to 3 turns, where it stops moving. Now we place a condition, If our sensor detects a distance greater than 1.5 meters to one side, this means that the car must be turned to that side by activating the H-bridge corresponding to that direction of the front motor. Afterwards, if the sensors detect a distance greater than 30 cm on each side (which means that it is in the center) the car will advance straight, otherwise, the car will look for which of the two sides the measurement is less than 30cm to turn in the other direction and rectify.

Programming Challenge Obstacles

To begin, we first activate the huskylens in I2C protocol to communicate with the microbit and place it in color detection mode. In addition, we start with the rear motor at a slightly higher power controlled by pwm to have inertia when starting.

In the loop, we place all the ultrasonic sensor variables and the huskylens sampling, then we place the rear motor at a lower power and set the conditionals for the huskylens color detection. When it detects “ID1” corresponding to red, it turns to the right until it disappears from the field of view that we established by coordinates, the same with green “ID2” in the other direction. Finally, we put the same ultrasonic distance detection program that we used in the open challenge.
