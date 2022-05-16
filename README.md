# PingPongGame

## Aim:
To develop a ping pong game using C# program in unity .


## Algorithm:
### Step 1:
Create a new scene and save. Then right click hierarchy and click ->create empty (name as Game manager).
### Step 2:
In the Asserts create new C# script and (name as GameManager) two more scripts (named as Ball and Paddle).
### Step 3:
Right click creat-> 2D->spirates-> circle then create->2D->spirates->square. Drag these from asserts to hierarchy and change the position and scale in the inspector.
### Step 4:
For both the sprites->Add Components-> BoxCollider 2D (Tick in IsTigger) and Rigidbody 2D(Change the body type to Kinematics )
### Step 5:
For both the sprites -> Add the tag. In inspector-> Tag-> Click AddTag and create the tag with name as(Paddle) and make the tag as Paddle so we can whether ball is hitting paddle or somewhere else in script. Similarly do for Ball.
### Step 6:
Drag the ball and paddle from hierarchy to the Asserts-> Sprites to create prefabs and reset the position of Paddle to (0,0,0) and delete ball and paddle from hierarchy.
### Step 7:
Click the Game manager in hierarchy and drag the GameManager script to Inspector and open the script
Public Ball ball;
Public Paddle paddle;
Check in the unity whether the variables are displaying in the unity.
### Step 8:
Now Click the ball game object which we deleted from hierarchy and incorporate the ball script to it, similarly,click paddle game object and incorporate the paddle script to it. Then drag the paddle variable and ball variable into game manager.
Type the code th GameManager and Paddle
### Step 9:
Edit-> Project settings-> Input -> Axes (2) -> Horizontal (name as PaddleLeft) and Vertical (name as PaddleRight)
### Step 10:
In PaddleRight (Negative button - down and positive buttom - up) and paddleLeft(Negative button - s and positive buttom - w)
 After completing, to move the ball, in the ball inspector give the value for speed
 
 ## Program:
 ```
 using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class GameManager : MonoBehaviour
{
    public Ball ball;
    public Paddle paddle;
    public static Vector2 bottomLeft;
    public static Vector2 topRight;
    // Start is called before the first frame update
    void Start()
    {
        bottomLeft = Camera.main.ScreenToWorldPoint(new Vector2(0, 0));
        topRight = Camera.main.ScreenToWorldPoint(new Vector2(Screen.width, Screen.height));
        Instantiate(ball);
        Paddle paddle1 = Instantiate(paddle) as Paddle;
        Paddle paddle2 = Instantiate(paddle) as Paddle;
        paddle1.Init(true);
        paddle2.Init(false);
    }

    // Update is called once per frame
    void Update()
    {

    }
}
 ```
 
 ## Output:
 ![image](https://user-images.githubusercontent.com/75235128/168572900-f1332f43-6237-44a0-95cd-1a443f0659f0.png)

 
 ## Result:
Thus ping pong game using C# program in unity is created .
