---
title: Dépannage du gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Résumé: Lisez cette rubrique pour résoudre les problèmes liés à votre déploiement du gestionnaire de statistiques pour Skype entreprise Server.'
ms.openlocfilehash: b85ee6593413cce0aa5b7c76901dbbc6099107fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299694"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Dépannage du gestionnaire de statistiques pour Skype Entreprise Server
 
**Résumé:** Consultez cette rubrique pour dépanner votre déploiement du gestionnaire de statistiques pour Skype entreprise Server.
  
Cette rubrique explique comment résoudre les problèmes de déploiement de votre gestionnaire de statistiques en décrivant des événements que vous pouvez rencontrer dans le journal des événements de l’application, ainsi que les actions appropriées pour corriger l’événement. Cette rubrique contient les sections suivantes :
  
- [Événements de l’agent](troubleshoot.md#BKMK_Agent)
    
- [Événements de l’écouteur](troubleshoot.md#BKMK_Listener)
    
- [Problèmes de site web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Événements de l’agent
<a name="BKMK_Agent"> </a>

- **1000** : impossible de configurer le limiteur de processeur (objet de traitement) ; raison inconnue
    
- **1001** : le processus de limitation de processus n’est pas autorisé sur le processus (probablement déjà dans un objet de travail).
    
    L’agent s’exécute à l’intérieur d’un objet de traitement Windows pour limiter automatiquement son encombrement mémoire. Si l’agent ne démarre pas et si ces entrées d’événements apparaissent dans le journal d’événements, l’objet de traitement n’a pas pu être instancié sur le serveur. Pour contourner ce problème, la limite maximale de la mémoire peut être supprimée en modifiant une valeur dans le fichier de configuration :
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Recherchez «MaxProcessMemoryMB» et attribuez la valeur «0» comme suit:
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Si cette modification est apportée, l’agent utilisera \< généralement 100 Mo de mémoire, mais il ne sera pas limité de force à 300 Mo par défaut. Néanmoins, si vous effectuez cette modification, nous vous recommandons de surveiller attentivement l’utilisation de la mémoire, afin de vous assurer que l’agent ne consomme pas trop de mémoire sur son ordinateur hôte. 
  
- **2000** : échec de l’initialisation du client
    
- **2001** : impossible de se connecter au service sur n’importe quelle source IP
    
    Si l’agent ne peut pas se connecter à l’ordinateur d’écoute, vérifiez les points suivants :
    
1. Vérifiez que le service d’écoute est en cours d’exécution sur l’ordinateur d’écoute. Si ce n’est pas le cas, assurez-vous que Redis est en cours d’exécution sur ce serveur, puis redémarrez le service d’écoute.
    
    Pour vérifier qu’il n’y a aucun problème avec le service d’écouteur de statistiques, consultez le journal des événements du gestionnaire de statistiques sur l’ordinateur de l’écouteur.
    
2. Utilisez un outil de connectivité tel que telnet pour vérifier la connectivité entre l’ordinateur de l’agent et l’écouteur sur le port approprié.
    
    Sinon, assurez-vous que la règle de pare-feu pour le trafic entrant est activée sur l’ordinateur d’écoute pour le type de réseau auquel l’ordinateur d’écoute est connecté (privé/public/domaine). S’il n’est pas joint à un domaine, il est possible que le réseau soit répertorié comme public et, dans ce cas, les règles de pare-feu installées avec le gestionnaire de statistiques ne s’appliquent pas par défaut.
    
- **4000** : impossible de télécharger les informations du serveur depuis l’écouteur (raison inconnue)
    
  - **4001** : serveur introuvable dans la topologie de l’écouteur
    
    Cette erreur se produit si le serveur parvient à se connecter à l’écouteur, mais que le serveur n’a pas été ajouté à la topologie dans le cache de l’écouteur. Options de résolution :
    
  - 	Assurez-vous que vous avez suivi les instructions pour importer la topologie. Consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).   
    
  - Si l’agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, nœuds dans un cluster SQL AlwaysOn), vous devrez ajouter l’agent manuellement en suivant les instructions de la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - **4002** : mot de passe d’écouteur non valide
    
    Le mot de passe chiffré que l’agent essaie d’utiliser ne correspond pas au mot de passe du service sur l’écouteur lui-même. Désinstallez l’agent et réinstallez-le en utilisant le bon mot de passe du service.
    
  - **4003** : incompatibilité de l’empreinte numérique du certificat
    
    Le certificat d’empreinte numérique fourni pour l’agent au moment de l’installation ne correspond pas à l’empreinte digitale du certificat utilisé par l’écouteur et par conséquent, la connexion est refusée. Désinstallez et réinstallez-le à l’aide de l’empreinte numérique de certificat appropriée.
    
  - **4004** : HttpStatusCode ou réponse non valide
    
    L’écouteur ne répond pas avec le statut attendu.   
    
  - En cas de connexion par proxy, vérifiez la configuration du proxy.
    
  - Pour plus d’informations sur les problèmes liés à la configuration, consultez le journal des statistiques de l’ordinateur de l’écouteur.
    
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
    
- **22000** -échec de l’initialisation de l’agent Statistics Manager.
    
- **23000** : initialisation de EventLogQueryManager réussie (la première fois ou après un échec)
    
- **24000** : initialisation des informations de serveur réussie (la première fois ou après un échec)
    
- **25000** : l’écouteur est à nouveau en ligne après un échec de publication (ou première publication réussie)
    
- **5000** : début de la mise hors connexion de l’écouteur pour la publication de données
    
- **5001** : l’écouteur est toujours hors connexion pour une longue période
    
    Ces événements peuvent servir à surveiller/détecter/résoudre des problèmes.
    
## <a name="website-issues"></a>Problèmes de site web
<a name="BKMK_Website"> </a>

- Invites de connexion répétitives dans Chrome-il s’agit d’un bogue résolu dans la version 1,1. Vérifiez que vous avez effectué la mise à niveau vers la dernière version de Statistic Manager si vous voyez des invites de connexion répétées dans le navigateur Chrome. Pour vérifier la version du site web que vous exécutez, procédez comme suit :
    
  - 	Dans l’Explorateur de fichiers, ouvrez (répertoire par défaut)
    
  - Cliquez avec le bouton droit de la souris sur StatsManHubWebSite.dll pour afficher ses propriétés.
    
  - Si un ordinateur est introuvable dans l’affichage en mode Paysage ou en mode Détails des compteurs des KHI, assurez-vous qu’il est membre d’un site et d’un pool. Si ce n’est pas le cas, il n’apparaîtra pas dans ces affichages. Pour plus d’informations sur la définition dans la topologie d’un site et d’un pool pour un serveur, consultez la rubrique [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - La version du produit s’affiche dans les détails de la description.
    
## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Website"> </a>

Pour plus d'informations, voir les articles suivants :
  
- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)
    
- [Déploiement du gestionnaire de statistiques pour Skype Entreprise Server](deploy.md)
    
- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)
