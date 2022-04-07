## Nature in Future

# Project description
For this project, 4 people worked as a team. We each created sculptures that mimic movement of various animals using a servo motor, and a stepper motor.
The sculptures were all under the theme of "Nature in future" - a near dystopian future where only artificially created sculptures of organisms remain, as they are extinct due to climate change. This idea roots from our imagination that humans, or androids with artificial intelligence in the future, would yearn for mother nature they destroyed, and create a replica.
  
## Set up

ESP32 was connected to servo motor and stepper motor. 
![67072545432__6880A0E7-8CD5-4224-9B3A-18F251B68747](https://user-images.githubusercontent.com/25335750/162140825-73bc994e-b27c-45c9-9a61-9d319a317e41.jpg)


Then, they were put in a cardboard enclosure with only the tip of the motors visible:
![IMG_0872 HEIC](https://user-images.githubusercontent.com/25335750/162140623-e25c2a6e-6967-4dc3-b009-828c4f4541a8.jpg)
![IMG_0873 HEIC](https://user-images.githubusercontent.com/25335750/162140625-9de44130-ea4f-4c55-9113-a451ab50f4c8.jpg)
![IMG_0874 HEIC](https://user-images.githubusercontent.com/25335750/162140627-073bafd4-b0b0-4f29-91d3-08d82acb3b3d.jpg)


Using cardboard, I drew and cut out fish:
![IMG_0842 HEIC](https://user-images.githubusercontent.com/25335750/162140514-48d458f1-47e9-47e3-9cf7-3fce783c144c.jpg)
![IMG_0846 HEIC](https://user-images.githubusercontent.com/25335750/162140515-8dff86ff-1d90-4792-a034-0dca8257bc21.jpg)


![IMG_0854 HEIC](https://user-images.githubusercontent.com/25335750/162120445-a9037a55-044c-4a0e-96e1-b5e363715fd1.jpg)
![IMG_0858 HEIC](https://user-images.githubusercontent.com/25335750/162120450-92d2e200-e9df-4fe2-9e43-8365dcd25f3a.jpg)

In order to make two fish rotate 360 degrees with stepper motor, I cut the tip of a straw in half and slid the papers in:
![IMG_0847 HEIC](https://user-images.githubusercontent.com/25335750/162122255-f14578da-5d5e-47b6-b405-9091532ecd58.jpg)
![IMG_0848 JPG](https://user-images.githubusercontent.com/25335750/162122290-ecfb43ef-31df-4c02-8d5f-33c1ec1ec482.jpg)

In order to mimic movement of fish swimming, for the bigger fish, its tail was linked to a servo motor with a string:
![IMG_0878 HEIC](https://user-images.githubusercontent.com/25335750/162122388-120bcc2a-2fd8-4986-b401-5e2e2aa61001.jpg)
![IMG_0879 HEIC](https://user-images.githubusercontent.com/25335750/162122415-6c0ca3fd-bb89-4fa3-acdb-7096b4f088b7.jpg)
Its body was taped to a straw, which was put in a hole of the enclosure box. Since it was not taped or tied to anything, as the servo motor moves, the fish moves freely. In the code that can be found at: https://github.com/sitongfX/NatureInFuture/blob/main/NAM_fish/NAM_fish.ino , I set the servo motor to quickly move from 0 to 200, then reset to 0, in a loop:
 
                for(int i = 0; i<2000;i++){
                 //servo
                  state = state + 10;
                  myservo.write(state);
                
                   //stepper
                  moveSteps(true, 5, 3);
                  if(state == 200){
                    state = 0;
                    myservo.write(state);
                  }
                }
                

This would mimic how a fish's tail moves while it swims.


To visualize water, the enclosure was covered with blue paper:
![IMG_0877 HEIC](https://user-images.githubusercontent.com/25335750/162123727-2e825378-9963-4aef-acf4-f56366302f9b.jpg)

### Installation

As a class, we all installed the sculptures and ran our motors simultaneously. This was possible with help of webAPI, provided by Professor Santlucito: https://github.com/mbennett12/kinetic-sculpture-webapi 


On a sheet of blue paper, 4 of us installed our sculptures:
![IMG_0885 HEIC](https://user-images.githubusercontent.com/25335750/162140876-9e1ec56e-d979-448c-b64e-6e44c44f263d.jpg)


![IMG_0887 HEIC](https://user-images.githubusercontent.com/25335750/162124586-b0b9667b-92f9-4faa-8a0f-0d10f5a2bf70.jpg)

#### Technical difficulties
When I was writing the code, I was testing it without the web API, and the code to run the motor in void loop(){} ran without any delay. However, transferring this snippet of code to the provided code with web API and HTTP requests, there were delays and motors moved with some lags. This was fixed with running the code in a for loop for many times.

The details of the code for each sculptures and the ReadMe file can be found at the combined git repo: https://github.com/sitongfX/NatureInFuture

Our sculptures in action can be watched at: https://youtu.be/s9gXnl4QDos



