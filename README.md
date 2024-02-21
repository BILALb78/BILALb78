- 👋 Hi, I’m @BILALb78
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
BILALb78/BILALb78 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
class Translation:
    def __init__(self, x=0, y=0):
        self.x = x
        self.y = y

    def __str__(self):
        return f"Translation: ({self.x}, {self.y})"


class LinearTranslation(Translation):
    def __init__(self, x=0, y=0, speed=1):
        super().__init__(x, y)
        self.speed = speed

    def apply_translation(self, delta_time):
        self.x += self.speed * delta_time
        self.y += self.speed * delta_time


class CircularTranslation(Translation):
    def __init__(self, x=0, y=0, radius=1, angular_speed=1):
        super().__init__(x, y)
        self.radius = radius
        self.angular_speed = angular_speed
        self.angle = 0

    def apply_translation(self, delta_time):
        self.angle += self.angular_speed * delta_time
        self.x = self.radius * math.cos(self.angle)
        self.y = self.radius * math.sin(self.angle)


# Exemple d'utilisation
import math

linear_translation = LinearTranslation(0, 0, 2)
circular_translation = CircularTranslation(0, 0, 5, 1)

# Appliquer les translations pendant 5 secondes
delta_time = 0.1
for _ in range(50):
    linear_translation.apply_translation(delta_time)
    circular_translation.apply_translation(delta_time)
    print(linear_translation)
    print(circular_translation)
