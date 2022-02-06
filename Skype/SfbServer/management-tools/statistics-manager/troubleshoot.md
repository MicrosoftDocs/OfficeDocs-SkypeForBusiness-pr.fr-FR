---
title: Résolution des problèmes du Gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Résumé : Lisez cette rubrique pour résoudre les problèmes de déploiement du Gestionnaire de statistiques pour Skype Entreprise Server.'
---

# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Résolution des problèmes du Gestionnaire de statistiques pour Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour résoudre les problèmes de déploiement du Gestionnaire de statistiques pour Skype Entreprise Server.
  
Cette rubrique décrit comment résoudre les problèmes de déploiement de votre gestionnaire de statistiques en décrivant les événements que vous pouvez voir dans le journal des événements d’application et les actions appropriées que vous pouvez prendre pour rectifier l’événement. Cette rubrique comprend les sections suivantes :
  
- [Événements de l’agent](troubleshoot.md#BKMK_Agent)
    
- [Événements d’écoute](troubleshoot.md#BKMK_Listener)
    
- [Problèmes de site web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Événements de l’agent
<a name="BKMK_Agent"> </a>

- **1000** — Impossible de configurer le limiteur de processeur (objet de travail) — Raison inconnue
    
- **1001** — La limitation des processus n’est pas autorisée sur le processus (probablement déjà à l’intérieur d’un objet Job)
    
    L’agent s’exécute à l’intérieur d’un objet Windows travail pour limiter automatiquement son encombrement mémoire. Si l’agent ne démarre pas et que ces entrées d’événements sont présentes dans le journal des événements, l’objet Job ne peut pas être inséré sur le serveur. Pour contourner ce besoin, vous pouvez supprimer la limite de mémoire supérieure en modifiant une valeur dans le fichier de config :
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Recherchez « MaxProcessMemoryMB » et modifiez la valeur sur « 0 », comme illustré :
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Si cette modification est réalisée, l’agent \< consomme généralement toujours 100 Mo de mémoire, mais il ne sera pas forcément limité à 300 Mo comme c’est le cas par défaut. Si cette modification est réalisée, nous vous recommandons de surveiller attentivement l’utilisation de la mémoire pour vous assurer que l’agent ne consomme pas une grande quantité de mémoire sur son ordinateur hôte. 
  
- **2000** — Échec de l’initialisation du client
    
- **2001** — Aucune connexion au service n’a pu être réalisée sur n’importe quelle adresse IP source
    
    Si l’agent ne peut pas se connecter à l’ordinateur d’écoute, vérifiez ce qui suit :
    
    1. Assurez-vous que le service d’écoute est en cours d’exécution sur l’ordinateur d’écoute. Si ce n’est pas le cas, assurez-vous que Redis est en cours d’exécution sur ce serveur, puis redémarrez le service d’écoute.
        
        Consultez le journal des événements du Gestionnaire de statistiques sur l’ordinateur d’écoute pour vous assurer qu’il n’y a aucun problème avec le service d’écoute du gestionnaire de statistiques lui-même.
        
    2. Utilisez un outil de connectivité tel que telnet pour vérifier la connectivité de l’ordinateur agent à l’écoute sur le port correct.
        
        Si ce n’est pas le cas, assurez-vous que la règle de pare-feu entrant est activée sur l’ordinateur d’écoute pour le type de réseau à qui l’ordinateur d’écoute est connecté (privé/public/domaine). Si l’ordinateur d’écoute n’est pas joint à un domaine, le réseau peut être répertorié comme public et dans ce cas, les règles de pare-feu installées avec le Gestionnaire de statistiques ne s’appliqueront pas par défaut.
    
- **4000 : échec** du téléchargement des informations sur le serveur à partir de l’écoute (raison inconnue)
    
  - **4001** — Serveur in trouvé dans la topologie d’écoute
    
    Cette erreur se produit si le serveur se connecte correctement à l’écoute, mais que le serveur n’a pas été ajouté à la topologie dans le cache de l’écoute. Options de résolution :
    
  - Assurez-vous que vous avez suivi les instructions d’importation de la topologie. Voir [Importer la topologie](deploy.md#BKMK_ImportTopology). 
    
  - Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, les nodes dans un cluster SQL AlwaysOn), vous devez ajouter l’agent manuellement en suivant les instructions de l’importation de la topologie[.](deploy.md#BKMK_ImportTopology)
    
  - **4002** — Mot de passe d’écoute non valide
    
    Le mot de passe chiffré que l’agent tente d’utiliser ne correspond pas au mot de passe du service sur l’écoute lui-même. Désinstallez l’agent et réinstallez-le à l’aide du mot de passe de service correct.
    
  - **4003** — Non-matage de l’empreinte numérique du certificat
    
    L’empreinte numérique du certificat donnée à l’agent au moment de l’installation ne correspond pas à l’empreinte du certificat que l’écoute utilise actuellement et par conséquent, la connexion sera refusée. Désinstallez l’agent et réinstallez-le à l’aide de l’empreinte de certificat correcte.
    
  - **4004** — Réponse non valide ou HttpStatusCode
    
    L’écoute ne répond pas avec un état attendu. 
    
  - Si la connexion est proxy, vérifiez la configuration du proxy.
    
  - Vérifiez le journal StatsMan de l’ordinateur d’écoute pour les problèmes de configuration.
    
  - **4005** — Impossible de désérialiser le XML
    
    Les informations du serveur sur le serveur d’écoute sont endommagées ou il peut y avoir une non-distinction de version entre l’agent et les ordinateurs d’écoute. Vérifiez que les versions correspondent et vérifiez le journal des événements d’écoute pour les problèmes.
    
## <a name="listener-events"></a>Événements d’écoute
<a name="BKMK_Listener"> </a>

- **10000** — Échec du démarrage Pour une raison inconnue (ces erreurs sont irrécables et le service s’arrête/se crashe en conséquence)
    
  - **10001** — Problème de configuration
    
    En règle générale, cela se produit lorsque le fichier [listener_install_location]\PerfAgentListener.exe.config a été modifié à la main et ne peut pas être lu par l’application.
    
  - **10002** — Erreur d’initialisation de l’écoute HTTP
    
    Cet événement est généralement enregistré lorsque la liste decl d’URL n’a pas été correctement définie lors de l’installation ou que le cert SSL n’est pas valide. Assurez-vous que le certificat de votre configuration est valide. Si c’est le cas, réinstallez l’écoute en suivant les instructions de [Deploy Statistics Manager](deploy.md#BKMK_Deploy).
    
  - **10003** — Échec de Redis
    
  - **10004** : défaillance de l’infrastructure de mise en cache
    
  - **10007** — Paramètres (stocké dans redis)
    
    L’écouteur n’a pas pu contacter Redis ou récupérer des données bien formées à partir du cache et n’a pas pu démarrer. Assurez-vous que le service Redis est démarré et configuré correctement sur le serveur.
    
  - **10005 —** Récupération/extraction/extraction des informations du serveur
    
    Les informations de topologie dans le cache Redis ne sont pas valides. Tout d’abord, essayez de redémarrer Redis et l’écoute. Si l’erreur persiste, voir [Importer la topologie](deploy.md#BKMK_ImportTopology) pour recréer les données de topologie.
    
- **10100** — Panne PING Redis
    
  - **10101** — Panne continue de redis PING (toutes les 60 secondes)
    
  - **30100** — Restauration de la panne PING de Redis
    
    Ceux-ci sont enregistrés lorsque l’écoute ne peut pas se connecter à Redis. Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écoute et Redis est disponible.
    
- **10200** — Panne d’écriture de Redis
    
  - **10201** — Panne d’écriture de Redis continue (toutes les 60 secondes)
    
  - **30100** — Panne d’écriture de Redis résolue
    
    Ceux-ci sont enregistrés lorsque l’écoute ne peut pas écrire dans le cache Redis. Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écoute et Redis est disponible.
    
- **30000** — Démarré avec succès
    
    Journalisé chaque fois que l’écoute est démarrée.
    
- **22000** : l’initialisation de l’agent du gestionnaire de statistiques a réussi.
    
- **23000** : l’initialisation de EventLogQueryManager a réussi (première fois ou après un échec)
    
- **24000** : l’initialisation de serverinfo a réussi (première fois ou après échec)
    
- **25000 — L’écoute** est de nouveau en ligne après un échec de publication (ou une première publication réussie)
    
- **5000 : début** de l’écoute hors connexion pour la publication de données
    
- **5001** — L’écoute est toujours hors connexion pendant une période prolongée
    
    Ces événements peuvent être utiles pour surveiller/alerter/effacer les problèmes.
    
## <a name="website-issues"></a>Problèmes de site web
<a name="BKMK_Website"> </a>

- Invites de connexion répétitives dans Chrome : il s’agissait d’un bogue qui a été résolu dans la version 1.1. Assurez-vous que vous avez mis à niveau vers la dernière version du Gestionnaire de statistiques si vous voyez des invites de connexion répétées dans le navigateur Chrome. Pour vérifier la version du site web que vous exécutez :
    
  - Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut)
    
  - Cliquez avec le bouton droit StatsManHubWebSite.dll et affichez ses propriétés.
    
  - Si vous ne pouvez pas trouver un ordinateur dans l’affichage Paysage KHI ou l’affichage Détails du compteur, assurez-vous qu’il est membre d’un site et d’un pool. Si ce n’est pas le cas, il n’apparaîtra pas dans ces affichages. Pour plus d’informations sur la définition d’un site et d’un pool pour un serveur dans la topologie, voir [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - La version du produit s’affiche dans les détails de description.
    
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Website"> </a>

Pour plus d'informations, consultez les articles suivants :
  
- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)
    
- [Déploiement du gestionnaire de statistiques pour Skype Entreprise Server](deploy.md)
    
- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)
