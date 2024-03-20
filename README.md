import random

class Kingdom:
    def __init__(self, name):
        self.name = name
        self.army_size = random.randint(50, 100)
        self.resources = random.randint(100, 200)
        self.defense = random.randint(20, 50)

class Battle:
    def __init__(self, attacker, defender):
        self.attacker = attacker
        self.defender = defender

    def simulate_battle(self):
        attacker_strength = self.attacker.army_size * random.uniform(0.8, 1.2)
        defender_strength = self.defender.army_size * random.uniform(0.8, 1.2)

        if attacker_strength > defender_strength:
            print(f"{self.attacker.name} wins the battle!")
            self.defender.army_size = max(0, self.defender.army_size - random.randint(10, 30))
        else:
            print(f"{self.defender.name} wins the battle!")
            self.attacker.army_size = max(0, self.attacker.army_size - random.randint(10, 30))

# Örnek krallıklar oluşturalım
kingdom1 = Kingdom("Kingdom 1")
kingdom2 = Kingdom("Kingdom 2")

# Savaş simülasyonu yapalım
battle = Battle(kingdom1, kingdom2)
battle.simulate_battle()

# Sonuçları yazdıralım
print(f"{kingdom1.name} army size: {kingdom1.army_size}")
print(f"{kingdom2.name} army size: {kingdom2.army_size}")
