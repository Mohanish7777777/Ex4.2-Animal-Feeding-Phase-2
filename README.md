# Ex4.2-Animal-Feeding-Phase-2

## Aim :

To develop a animal feeding game-Phase-2 using unity.

## Algorithm :

## Player Control :

### Step 1 :

Extract the package and in unity , asserts -> Import packages -> Custom packages and select the package. When we go to Assets folders we can see the course library which we extracted.

### Step 2 :

If you want, drag a different material from Course Library > Materials onto the Ground object.

### Step 3 :

Drag 1 Human, 3 Animals, and 1 Food object into the Hierarchy.

### Step 4 :

Rename the character “Player”, then reposition the animals and food so you can see them

### Step 5 :

Adjust the XYZ scale of the food (2,2,2) so you can easily see it from above.

### Step 6 :

In your Assets folder, create a “Scripts” folder, and a “PlayerController” script inside.Attach the script to the Player by dragging the c# file to the player and open in the inspector and check whether it is attached.

## Moving Forward :

### Step 1 :

Create a new “MoveForward” script, attach script to the Food Pizza by dragging the c# file to the pizza and open in the inspector and check whether it is attached

### Step 2 :

Create a new “Prefabs” folder, drag your food (Pizza) into Prefab folder, and a pop up raises-> choose Original Prefab

### Step 3 :

Select the Player in the hierarchy, then drag the pizza from your Prefabs folder onto the new Projectile Prefab box in the inspector

### Step 4 :

Rotate all animals on the Y axis by 180 degrees to face down

### Step 5 :

Select all three animals in the hierarchy and Add Component > Drag the Move Forward script from the Scripts into inspector

### Step 6 :

Edit their speed values and test to see how it looks. Drag all three animals into the Prefabs folder, choosing “Original Prefab”

## PROGRAM :

### DEVELOPED BY : ABRIN NISHA A
### REG NO : 212222230005

## SPAWN MANAGER :

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SpawnManager : MonoBehaviour
{
    public GameObject[] animalPrefabs;
    private float spawnRangeX = 1;
    private float spawnPosZ = 1;
    private float startDelay = 2f;
    private float spawnInterval = 1.5f;

    void Start()
    {
        InvokeRepeating("SpawnRandomAnimal", startDelay, spawnInterval);
    }

    // Update is called once per frame
    void Update()
    {

    }

    void SpawnRandomAnimal()
    {
        int animalIndex = Random.Range(0, animalPrefabs.Length);
        Vector3 spawnPos = new Vector3(Random.Range(-spawnRangeX, spawnRangeX), 0, spawnPosZ);
        Instantiate(animalPrefabs[animalIndex], spawnPos, animalPrefabs[animalIndex].transform.rotation);
    }
}

       
```

## DETECT COLLIDER :

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class DetectCollider : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {

    }
    private void OnTriggerEnter(Collider other)
    {
        Destroy(other);
        Destroy(other.gameObject);
    }
}


```
## OUTPUT :

![animal-1](https://github.com/Brindha77/Ex4.1-Animal-Feeding-Phase1/assets/118889143/85279186-c6a2-475b-8c02-678188f1f58d)

## RESULT :

Animal feeding game-Phase-2 using unity is developed successfully.
