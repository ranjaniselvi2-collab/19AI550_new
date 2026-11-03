# Ex.No: 4  Implementation of Kinematic movement -seek and Flee behavior in Unity
### DATE:                                                                            
### REGISTER NUMBER : 212225230224
### AIM: 
To write a program to simulate the process of seek and Flee behavior in Unity without NavigationMeshAgent. 
### Algorithm:
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., SeekBehaviorDemo).
2. Create the Moving Object
   In the Hierarchy, right-click → 3D Object → Cube (or Sphere).
   Rename it to Seeker and Reset its position:Select the Seeker, go to Inspector → Transform → Set Position to (0,0,0).
3. Create the Target Object
   Right-click in the Hierarchy → 3D Object → Sphere (or any other shape).
   Rename it to Target. Move it away from Seeker, e.g., set Position to (5, 0, 5).
   Select the Target, add a Material, and change the color. (if needed) 
4. Adding the Seek Behavior Script
   Create the Script-In the Project Window, go to the Assets folder.
   Right-click → Create → C# Script.
5. Write a script for seek behavior and save it
6. Attach the Script
   Select Seeker in the Hierarchy - Drag & Drop the SeekBehavior script onto the Inspector Panel.
   Drag & Drop the Target from the Hierarchy into the "Target" field in the script component.
12.  Write a script for flee behavior and attach it to target
13.  Run the game
14. Stop the program
    
### Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class seekScript : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (target.position - transform.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class fleeScript : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (transform.position-target.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
### Output:


<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/e05711b3-07b3-4bc5-a140-700ae801dbb0" />
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/1a6bc76a-7973-4462-98eb-d0e5e0ad5113" />
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/a00f3dec-6afc-4556-8861-aaece270a911" />

<img width="1917" height="1018" alt="image" src="https://github.com/user-attachments/assets/55d831d1-fbb8-4ab0-9f12-12ec0b3f94c9" />
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/034c999a-e6d5-4e14-ba11-e1eb172f09a7" />
<img width="1912" height="1017" alt="image" src="https://github.com/user-attachments/assets/afe21dcc-0028-433e-a459-01710b8468a3" />






### Result:
Thus the simple seek behavior was implemented successfully.
