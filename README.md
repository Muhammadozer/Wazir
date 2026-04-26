# human_builder.py
class Human:
    def __init__(self):
        self.organs = []
        self.speed = 0
    
    def add_organ(self, organ):
        self.organs.append(organ)
        print(f"➕ {organ} added.")
    
    def start_running(self):
        self.speed = 10
        print("🏃‍♂️ Human is now RUNNING at full speed!")

me = Human()
me.add_organ("🧠 brain")
me.add_organ("❤️ heart")
me.add_organ("💪 muscles")
me.start_running()
