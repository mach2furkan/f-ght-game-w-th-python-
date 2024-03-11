      # f-ght-game-w-th-python-
    import random

    class Player:
    def __init__(self, name):
        self.name = name
        self.health = 100
        self.damage = 20

    def attack(self, enemy):
        damage = random.randint(1, self.damage)
        enemy.take_damage(damage)
        print(f"{self.name} attacks {enemy.name} and deals {damage} damage.")

    def take_damage(self, damage):
        self.health -= damage
        if self.health <= 0:
            print(f"{self.name} has been defeated!")

    class Enemy(Player):
    def __init__(self, name):
        super().__init__(name)
        self.damage = 15

    def main():
    player_name = input("Enter your name: ")
    player = Player(player_name)
    enemy = Enemy("Goblin")

    print("A wild Goblin appears!")

    while player.health > 0 and enemy.health > 0:
        print("\n" + "="*20)
        print(f"{player.name}'s Health: {player.health}")
        print(f"{enemy.name}'s Health: {enemy.health}")
        print("="*20 + "\n")

        action = input("Do you want to [a]ttack or [r]un? ").lower()

        if action == 'a':
            player.attack(enemy)
            if enemy.health > 0:
                enemy.attack(player)
        elif action == 'r':
            print("You run away from the battle!")
            break
        else:
            print("Invalid action! Choose again.")

    print("Game Over")

    if __name__ == "__main__":
    main()
      22222

