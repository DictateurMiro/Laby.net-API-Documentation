# Laby.net-API-Documentation

### Obtenir l'UUID d'un joueur minecraft via son pseudo:

> GET **`https://laby.net/api/v3/user/[pseudo]/uuid`**

Réponse :

```
{
  "uniqueId": "61db9350-fb40-4c9e-8ff8-8e4adda18ce1",
  "username": "CapVert",
  "uuid": "61db9350-fb40-4c9e-8ff8-8e4adda18ce1",
  "name": "CapVert"
}
```

---

### Obtenir le nombre de visite sur le profile d'un joueur minecraft via son UUID:

> GET **`https://laby.net/api/v3/user/[uuid]/views`**

Réponse :

```
{
  "views": 2
}
```

### Obtenir la liste d'amis d'un joueur minecraft via son UUID:

> GET **`https://laby.net/api/v3/user/[uuid]/friends`**

Réponse (si le joueur a des amis, Status code : 200):

```
[
  {
    "uuid": "0acff262-2724-4ee1-b73c-83d21ac4e544",
    "user_name": "einJona",
    "name": "einJona",
    "role_color": "4"
  },
  {
    "uuid": "199b1f41-869e-4769-b4dc-8c21487b112c",
    "user_name": "JakobHere",
    "name": "JakobHere",
    "role_color": "4"
  }
]
```

Réponse (si le joueur n'a pas d'amis, Status code : 403):

```
{
  "message": "Forbidden"
}
```

---

### Obtenir la date de premiere connexion et derniere connexion sur LabyMod via son UUID:

> GET **`https://laby.net/api/v3/user/[uuid]/game-stats`**

Réponse (si le joueur n'a jamais utilisé LabyMod, Status code : 204):

*Pas de réponse (No content)*

Réponse (si le joueur à déja utilisé, Status code : 200):

```
{
  "first_joined": "2017-11-06T19:53:15+00:00",
  "last_online": "2019-09-14T20:01:20+00:00"
}
```

---

### Voir si le joueur est actuellement connecté sur un serveur via LabyMod via son UUID:

> GET **`https://laby.net/api/v3/user/[uuid]/online-status`**

Réponse (si le joueur n'est pas connecté via LabyMod, Status code : 204):

*Pas de réponse (No content)*

Réponse (si le joueur a désactivé la fonction dans son profile, Status code : 403)

```
{
  "message": "Forbidden"
}
```

Réponse (si le joueur est connecté via LabyMod, Status code : 200):

```
{
  "online": true,
  "status": "ONLINE",
  "server": {
    "hostname": "griefergames.net",
    "port": 25565,
    "gamemode": "GrieferGames CityBuild 21"
  }
}
```

---

### Obtenir les badges d'un joueur via son UUID:

> GET **`https://laby.net/api/v3/user/[uuid]/badges`**

Réponse :

```
[
  {
    "uuid": "2aaaaec5-b64d-4f11-8e15-5bf7b866c0ff",
    "name": "Alpha Account",
    "description": "User bought the game during the ALPHA development phase of Minecraft (2010-06-30 - 2010-12-19)",
    "received_at": "2021-07-17T01:31:07+00:00"
  }
]
```

---

### Obtenir les likes du profile d'un joueur via son UUID:

> GET **`https://laby.net/api/v3/user/[uuid]/heart`**

Réponse :

```
{
  "count": 1,
  "status": null
}
```

---

### Obtenir la description d'un joueur via son UUID:

> GET **`https://laby.net/api/v3/user/[uuid]/status`**

Réponse :

```
{
  "status": "Daniel | Java Developer, Founder and Head Administrator of LabyMod\nWorking with @e0276ad9-1cd6-4c8d-b8f7-ff97e75c5982 on laby.net"
}
```
