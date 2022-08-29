# Stockage

{% hint style="info" %}
**Attention:** Ces informations sont destinées aux utilisateurs avancés. Procéder avec prudence!
{% endhint %}

Depuis Quests 4.0.0-rc.3, vous pouvez choisir de modifier votre option de stockage via le paramètre `storage-method` (méthode de stockage) du [fichier de configuration des quêtes](https://github.com/PikaMug/Quests/wiki/2-%E2%80%90-Configuration#configyml). Les choix disponibles sont décrits ci-dessous. Si vous souhaitez modifier votre méthode de stockage ultérieurement sans perdre de données, utilisez d'abord [QuestsConverter](https://github.com/PikaMug/QuestsConverter).

### YAML

Il s'agit de la sélection par défaut qui enregistrera les données du joueur dans des fichiers .yml séparés sous le dossier _/Quests/data_. Il est recommandé pour les utilisateurs débutants et occasionnels car il fonctionne "prêt à l'emploi" sans aucune configuration supplémentaire requise.

### MySQL

Cela enregistrera les données du joueur dans une base de données MySQL locale ou distante que vous avez configurée à l'avance. Les paramètres de table et de connexion peuvent être spécifiés via les paramètres `storage-data`. Un exemple d'une telle configuration pourrait ressembler à :

```text
storage-data:
  address: localhost
  database: minecraft
  username: root
  password: myComplexPassword
  table_prefix: quests_
  pool-settings:
    max-pool-size: 10
    min-idle: 10
    max-lifetime: 1800000
    connection-timeout: 5000
```

Notez que HikariCP a été _shaded_ en interne pour maximiser la vitesse de connexion sur les serveurs très peuplés.

### Customisée

Un développeur peut choisir d'utiliser une option de stockage personnalisée. Voir [lien actuellement indisponible]().

