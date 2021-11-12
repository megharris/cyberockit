Shifat's comment
- Do we need separate process for HA and Supervisor? If so they must have a trust boundary or different previlege levels as far as I remember from the lectures
- Interner boundary should separe user and HA process because of remote access abilities.
- Other than config.yml HA must have a DB of existing add-ons and connected devices. They could be combined into a single database.
- Boundary between Application provider and Supervisor 

Noah's comments
- Based on Shifat's comments maybe we can have one process with just supervisor, since the core lives inside supervisor? 
