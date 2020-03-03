# [Video 20](https://www.udemy.com/course/learn-kubernetes/learn/lecture/9742476#overview)


## YAML
Repräsentiert Daten

### Key value example
Fruit: Apple
Vegetabel: Carrot

Fruit: Apple
Drink: Water
Dessert: Cake
Vegetable: Carrot

### Array/list | ordered (die Reihenfolge ist wichtig)
Frutis:
-orange
-Apple
  Bananna

  Fruits:
  - Apple
  - Banana
  - Orange
  
Vegetables:
  - Carrot
  - Tomato
  - Cucumber


### Dictionary | unordered(reihenfolge egal)
Bananan:
    Calories: 105
    Fat: 0.4g
    carbs: 27g
BSP:
 Employee:
    Name: Jacob
    Sex: Male
    Age: 30
    Title: Systems Engineer



man kann nun eine Liste von Key-Values erstellen...
BSP:

Fruits:

>  - Apple:
 >       Calories: 95
        Fat: 0.3
        Carbs: 25
>  - Banana:
      Calories: 105
      Fat: 0.4
      Carbs: 27
>  - Orange:
        Calories: 45
        Fat: 0.1
        Carbs: 11
    

[Link to Cloud K8S](https://kodekloud.com/p/public-labs?scenario=kubernetes-for-beginners-basiccommands-test)

[OrginalPDFzumKurs](./original.pdf)
<!--![BeispielImages](./img/1.png)-->