# RoomLight - domain model

This is a simple map of how the hotel lighting control works. 

## 1. how it looks

```text
[ Admin ] --manages--> [ Profile ]
                          |
                          | (syncs to)
                          v
[ Group ] --contains--> [ Room ] --has--> [ Light ]
                          ^
                          | (controls)
                      [ Guest ]
```

## 2. what are they
- Admin: staff user who manages hotel settings
- Profile: saved light color and brightness
- Group: floor or room type to control areas easily
- Room: physical hotel room that groups lights
- Light: the light bulb being controlled
- Guest: person staying in a room who can override settings

## 3. how they talk to each other

- admin creates a profile with specific brightness and color
- admin syncs the profile to a group of rooms at once
- each room has one or more lights
- a guest can change the light in their own room without affecting others