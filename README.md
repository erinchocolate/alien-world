# Animation

The program emulates a world with aliens and planets.

Rules:

- Aliens and planets have different technology levels

- Aliens with higher technology level can kill aliens with lower technology level and colonize planets.

- When aliens colonize planets, they can increase their technology level. The increased number depends on the planets' level.

- Different aliens have different moving speed, they can only kill each other or colonize planets when they encounter other aliens or planets.

## Demo

![Animation](https://github.com/erinchocolate/swen502/blob/master/Animation/animationDemo.gif)

## Continued development

```java
public Alien removeAlien() {
		for(Alien a: ufos) {
			deadAlien = a.fight();
		}
		return deadAlien;
	}

timeline = new Timeline();
		keyFrame = new KeyFrame(Duration.millis(100),(ActionEvent event) ->{
			space.moveAlien();	
			//Remove dead aliens and planets
			layout.getChildren().remove(space.removeAlien());
			layout.getChildren().remove(space.removePlanet());
		});
```

Since the alien moving logic and alien image update are triggered in the animation. There is only one Alien or Planet object that gets removed from the scene each keyframe even though there might be more Aliens and Planets colliding with each other.
