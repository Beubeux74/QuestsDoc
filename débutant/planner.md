# Plannificateur

Une fois que vous vous êtes familliarisé avec Once l'[Editeur de quête](https://pikamug.gitbook.io/quests/v/french-francais/configuration/quests-editor), vous devez vous questionner à propos du menu 'Editer le plannificateur'. Ce sous-menu contient les paramètres pour déterminer quand votre quête devrait être disponible, basée sur le temps réel:

![](https://camo.githubusercontent.com/07cea0e4af2b6bde23df1ada96f63d46b090cfe97a32b8889eb3599245245ff8/68747470733a2f2f692e696d6775722e636f6d2f7743374134396a2e706e67)

Pour une meilleur compréhension, nous utliseront et expliront les exemples ci-dessous:

**Quête journalière**

Dans le monde réel, la plupart des marchands ne sont ouverts que durant les heures de pointes. Sur ce modèle, vous souhaitez que votre quête ne soit disponible qu'a certains moments de la journée.
Voici comment une telle quête peut apparaître dans quests.yml

```text
custom1:
    name: Une fois par jour
    ...
    planner:
      start: 11:1:2020:9:0:0:SystemV/EST5
      end: 11:1:2020:17:0:0:SystemV/EST5
      repeat: 86400
      cooldown: 32400
      override: true
```
La  **date de départ** (Start) est définis sur le 11 Janvier 2020 à 9.00h (matin) EST. La **date de fin** (end) est définis sur le 11 janvier 2020 à 17h00 EST. Cela signifie que la quête ne sera disponible que pendant huit heures.

Puisque que nous voulons que les joueurs puissent prendre leurs quête chaque jours, Le **Cycle de répétition** (repeat) est définis sur 86400 secondes \(24 heures\). Ce temps est basé sur la date de départ, donc la quête sera de nouveau disponible le lendemain, puis le 13 janvier, etc... Tout comme les horaire du premier jour, elle restera active entre 9.00h et 17h quotidiennement

Plus tard, nous voulons ajouter **Délais aux joueurs** (cooldown) de 32400 secondes \(9 heures\) car nous ne voulons pas que les joueurs puissent prendre leur quête une seconde fois si elle est terminé avant 17h00. Cela garantit que même les joueurs les plus rapides seront incapable de refaire la quête à nouveau avant le lendemain. Si vous souhaitez que les joueurs puissent effectuer la quête à 9h00 le lendemain, que leur temps de recharge ait expiré ou non, vous pouvez définir la priorité **ignore cooldown after repeat** (ignorer le temps de recharge après répétition) sur _true_.

**Célébration de la nouvelle année**

Allez c'est parti !! Nous allons crée une quête pour fêter la nouvelle année. Observons l'exemple suivant telle qu'il apparraîtrait dans quests.yml:

```text
custom1:
    name: PréparartionDuNouvelAn
    ...
    planner:
      start: 31:12:2020:23:0:0:SystemV/EST5
      end: 1:1:2021:0:0:0:SystemV/EST5
      repeat: 31536000
      cooldown: 3600
      override: false
```

La **date de départ** est définis sur le 31 décembre 2020 à 23h00 EST. La **date de fin** est le 1 janvier 2021 à 00h00 . TCela signifie que la quête ne sera disponible que pendant une heure.

Si nous voulons le célébrer _chaque année_, le **cycle de répétition** est définis sur 31536000 seconds \(Une année\). Puisque le temps est basé sur la date de départ, la quête sera donc à nouveau disponible le 31 décembre 2021 à 23h00 EST, ainsi qu'en 2022, etc... Elle ne sera disponible que durant une heure, comme la durée initialement prévue.

Plus tard, nous voulons mettre un **Délais de joueur** de 3600 secondes \(une heure\) car nous ne voulons pas que le joueur refasse la quête à nouveau si il la termine avant la date de fin de l'évènement. Cela assura que le joueur ne sera pas capable de refaire à nouveau la quête avant l'année suivante.
