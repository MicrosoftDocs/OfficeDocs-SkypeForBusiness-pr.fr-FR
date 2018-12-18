---
title: Résoudre les statistiques du gestionnaire pour Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Résumé : Lisez cette rubrique pour résoudre les problèmes de votre déploiement du Gestionnaire de statistiques de Skype pour Business Server.'
ms.openlocfilehash: 236b109f28de838d626e9c85844b87dc9e9eb20b
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297917"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Résoudre les statistiques du gestionnaire pour Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour résoudre les problèmes de votre déploiement du Gestionnaire de statistiques de Skype pour Business Server.
  
Cette rubrique décrit comment résoudre les problèmes de votre déploiement de gestionnaire de statistiques en décrivant les événements que vous pouvez voir dans le journal des événements et les actions appropriées, que vous pouvez prendre pour résoudre l’événement. Cette rubrique contient les sections suivantes :
  
- [Événements de l’agent](troubleshoot.md#BKMK_Agent)
    
- [Événements de l’écouteur](troubleshoot.md#BKMK_Listener)
    
- [Problèmes de site web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Événements de l’agent
<a name="BKMK_Agent"> </a>

- **1000** : impossible de configurer le limiteur de processeur (objet de traitement) ; raison inconnue
    
- **1001** : limitation des processus n’est pas autorisée sur le processus (probablement déjà à l’intérieur d’un objet de travail)
    
    L’agent s’exécute à l’intérieur d’un objet de traitement Windows pour limiter automatiquement son encombrement mémoire. Si l’agent ne démarre pas et si ces entrées d’événements apparaissent dans le journal d’événements, l’objet de traitement n’a pas pu être instancié sur le serveur. Pour contourner ce problème, la limite maximale de la mémoire peut être supprimée en modifiant une valeur dans le fichier de configuration :
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Rechercher « MaxProcessMemoryMB » et remplacez la valeur « 0 » comme :
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Si ce changement est effectué, l’Agent utilisera toujours généralement \< 100 Mo de mémoire, mais ne sera pas forcé limité à 300 Mo est la valeur par défaut. Néanmoins, si vous effectuez cette modification, nous vous recommandons de surveiller attentivement l’utilisation de la mémoire, afin de vous assurer que l’agent ne consomme pas trop de mémoire sur son ordinateur hôte. 
  
- **2000** : échec de l’initialisation du client
    
- **2001** : impossible de se connecter au service sur n’importe quelle source IP
    
    Si l’agent ne peut pas se connecter à l’ordinateur d’écoute, vérifiez les points suivants :
    
1. Vérifiez que le service d’écoute est en cours d’exécution sur l’ordinateur d’écoute. Si ce n’est pas le cas, assurez-vous que Redis est en cours d’exécution sur ce serveur, puis redémarrez le service d’écoute.
    
    Vérifiez le journal des événements Gestionnaire des statistiques sur l’ordinateur du port d’écoute pour vous assurer qu’aucun problème avec le service de gestionnaire de statistiques le port d’écoute proprement dit.
    
2. Utilisez un outil de connectivité tel que telnet pour vérifier la connectivité entre l’ordinateur de l’agent et l’écouteur sur le port approprié.
    
    Sinon, assurez-vous que la règle de pare-feu pour le trafic entrant est activée sur l’ordinateur d’écoute pour le type de réseau auquel l’ordinateur d’écoute est connecté (privé/public/domaine). Si l’ordinateur de l’écouteur n’est pas lié à un domaine, le réseau peut être répertorié comme public et dans ce cas les règles de pare-feu installés avec le Gestionnaire de statistiques s’appliquera pas par défaut.
    
- **4000** : impossible de télécharger les informations du serveur depuis l’écouteur (raison inconnue)
    
  - **4001** : serveur introuvable dans la topologie de l’écouteur
    
    Cette erreur se produit si le serveur se connecte avec succès le port d’écoute, mais le serveur n’a pas été ajouté à la topologie dans le cache de l’écouteur. Options de résolution :
    
  - 	Assurez-vous que vous avez suivi les instructions pour importer la topologie. Consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).   
    
  - Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, nœuds dans un cluster SQL AlwaysOn), vous devrez ajouter l’agent manuellement en suivant les instructions de la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - **4002** : mot de passe d’écouteur non valide
    
    Le mot de passe chiffré que l’agent essaie d’utiliser ne correspond pas au mot de passe du service sur l’écouteur lui-même. Désinstallez l’agent et réinstallez-le en utilisant le bon mot de passe du service.
    
  - **4003** : incompatibilité de l’empreinte numérique du certificat
    
    L’empreinte de certificat donné à l’Agent au moment de l’installation non correspondance de l’empreinte du certificat du port d’écoute utilise actuellement et par conséquent la connexion est refusé. Désinstaller l’Agent et réinstallez-le à l’aide de l’empreinte numérique du certificat approprié.
    
  - **4004** : HttpStatusCode ou réponse non valide
    
    L’écouteur ne répond pas avec le statut attendu.   
    
  - En cas de connexion par proxy, vérifiez la configuration du proxy.
    
  - Vérifier le port d’écoute journal l’ordinateur StatsMan des problèmes liés à sa configuration.
    
  - **4005** : impossible de désérialiser le XML
    
    Les informations de serveur sur le serveur d’écoute sont corrompues ou les versions des ordinateurs d’écoute et de l’agent sont incompatibles. Vérifiez que ces versions sont compatibles et qu’aucun problème n’apparaît dans le journal d’événements de l’écouteur.
    
## <a name="listener-events"></a>Événements de l’écouteur
<a name="BKMK_Listener"> </a>

- **10000** : échec du démarrage pour une raison inconnue (erreur irrécupérable qui provoque l’arrêt ou le blocage du service)
    
  - **10001** : problème de configuration
    
    En général, ce problème survient lorsque le fichier [listener_install_location]\PerfAgentListener.exe.config a été modifié à la main et ne peut pas être lu par l’application.
    
  - **10002** : erreur d’initialisation de l’écouteur HTTP
    
    Cet événement est généralement enregistré lorsque l’ACL de l’URL n’a pas été définie correctement pendant l’installation ou lorsque le certificat SSL n’est pas valide. Vérifiez que le certificat dans votre configuration est valide. Si c’est le cas, réinstallez l’écouteur en suivant les instructions de la rubrique [Deploy Statistics Manager](deploy.md#BKMK_Deploy).
    
  - **10003** : échec de Redis
    
  - **10004** : échec de l’infrastructure de mise en cache
    
  - **10007** : paramètres (enregistrés dans redis)
    
    L’écouteur n’a pas pu entrer en contact avec Redis ou extraire des données bien formées à partir de la mémoire cache et n’a donc pas pu démarrer. Assurez-vous que le service Redis est démarré et correctement configuré sur le serveur.
    
  - **10005** : analyse/récupération des informations du serveur
    
    Les informations de topologie dans la mémoire cache de Redis ne sont pas valides. Dans un premier temps, essayez de redémarrer Redis et l’écouteur. Si l’erreur persiste, consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology) pour recréer les données de topologie.
    
- **10100** : interruption du test ping de Redis
    
  - **10101** : interruption continue du test ping de Redis (toutes les 60 secondes)
    
  - **30100** : interruption du test ping de Redis restaurée
    
    Ces événements sont consignés lorsque l’écouteur ne peut pas se connecter à Redis. Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écouteur et Redis est disponible.
    
- **10200** : interruption de l’écriture de Redis
    
  - **10201** : interruption continue de l’écriture de Redis (toutes les 60 secondes)
    
  - **30100** : interruption de l’écriture de Redis résolue
    
    Ces événements sont consignés lorsque l’écouteur ne peut pas écrire sur la mémoire cache de Redis. Assurez-vous que Redis est démarré et que la connectivité réseau entre l’écouteur et Redis est disponible.
    
- **30000** : démarrage réussi
    
    Enregistré à chaque démarrage de l’écouteur.
    
- **22000** : l’initialisation de statistiques de le Manager Agent a réussi.
    
- **23000** : initialisation de EventLogQueryManager réussie (la première fois ou après un échec)
    
- **24000** : initialisation des informations de serveur réussie (la première fois ou après un échec)
    
- **25000** : l’écouteur est à nouveau en ligne après un échec de publication (ou première publication réussie)
    
- **5000** : début de la mise hors connexion de l’écouteur pour la publication de données
    
- **5001** : l’écouteur est toujours hors connexion pour une longue période
    
    Ces événements peuvent servir à surveiller/détecter/résoudre des problèmes.
    
## <a name="website-issues"></a>Problèmes de site web
<a name="BKMK_Website"> </a>

- Invites de connexion répétitive chrome : il s’agissait d’un bogue a été résolu dans la version 1.1. Assurez-vous que vous avez mis à niveau vers la dernière version du Gestionnaire de statistiques si vous rencontrez des invites de connexion répétées dans le navigateur Chrome. Pour vérifier la version du site web que vous exécutez, procédez comme suit :
    
  - 	Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut)
    
  - Cliquez avec le bouton droit de la souris sur StatsManHubWebSite.dll pour afficher ses propriétés.
    
  - Si un ordinateur est introuvable dans l’affichage en mode Paysage ou en mode Détails des compteurs des KHI, assurez-vous qu’il est membre d’un site et d’un pool. Si ce n’est pas le cas, il n’apparaîtra pas dans ces affichages. Pour plus d’informations sur la définition dans la topologie d’un site et d’un pool pour un serveur, consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - La version du produit s’affiche dans les détails de la description.
    
## <a name="for-more-information"></a>Pour plus d’informations
<a name="BKMK_Website"> </a>

Pour plus d’informations, voir les articles suivants :
  
- [Planifier Business Server pour le Gestionnaire de statistiques de Skype](plan.md)
    
- [Déployer des statistiques responsable Skype pour Business Server](deploy.md)
    
- [Mise à niveau du Gestionnaire de statistiques pour Skype pour Business Server](upgrade.md)
