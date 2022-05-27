---
title: Résolution des problèmes du Gestionnaire de statistiques pour Skype Entreprise Server
ms.reviewer: ''
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
description: 'Résumé : Lisez cette rubrique pour résoudre les problèmes de déploiement de Statistics Manager pour Skype Entreprise Server.'
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675276"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Résolution des problèmes du Gestionnaire de statistiques pour Skype Entreprise Server

**Résumé:** Lisez cette rubrique pour résoudre les problèmes de déploiement de Statistics Manager pour Skype Entreprise Server.

Cette rubrique explique comment résoudre les problèmes de déploiement de Statistics Manager en décrivant les événements que vous pouvez voir dans le journal des événements de l’application et les actions appropriées que vous pouvez prendre pour corriger l’événement. Cette rubrique comprend les sections suivantes :

- [Événements de l’agent](troubleshoot.md#BKMK_Agent)

- [Événements de l’écouteur](troubleshoot.md#BKMK_Listener)

- [Problèmes de site web](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>Événements de l’agent
<a name="BKMK_Agent"> </a>

- **1000** — Impossible de configurer le limiteur de processeur (objet Job) — Raison inconnue

- **1001** — La limitation des processus n’est pas autorisée sur le processus (probablement déjà à l’intérieur d’un objet job)

    L’Agent s’exécute à l’intérieur d’un objet job Windows pour limiter automatiquement son empreinte mémoire. Si l’agent ne démarre pas et que ces entrées d’événement sont présentes dans le journal des événements, l’objet Job ne peut pas être instancié sur le serveur. Pour contourner ce problème, vous pouvez supprimer la limite de mémoire supérieure en modifiant une valeur dans le fichier de configuration :

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Recherchez « MaxProcessMemoryMB » et remplacez la valeur par « 0 », comme indiqué :

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Si cette modification est effectuée, l’Agent consomme \< généralement toujours 100 Mo de mémoire, mais il ne sera pas forcément limité à 300 Mo comme c’est le cas par défaut. Si cette modification est effectuée, nous vous recommandons de surveiller étroitement l’utilisation de la mémoire pour vous assurer que l’Agent ne consomme pas une grande quantité de mémoire sur son ordinateur hôte.

- **2000** — Échec de l’initialisation du client

- **2001** : Aucune connexion au service n’a pu être établie sur une adresse IP source

  Si l’agent ne peut pas se connecter à l’ordinateur écouteur, vérifiez ce qui suit :

  1. Vérifiez que le service d’écouteur est en cours d’exécution sur l’ordinateur écouteur. Si ce n’est pas le cas, vérifiez que Redis s’exécute sur ce serveur, puis redémarrez le service Écouteur.

     Vérifiez le journal des événements du Gestionnaire de statistiques sur l’ordinateur écouteur pour vous assurer qu’il n’y a aucun problème avec le service d’écouteur du Gestionnaire de statistiques lui-même.

  2. Utilisez un outil de connectivité tel que telnet pour vérifier la connectivité de l’ordinateur Agent à l’écouteur sur le port approprié.

     Si ce n’est pas le cas, vérifiez que la règle de pare-feu entrante est activée sur l’ordinateur écouteur pour le type de réseau auquel l’ordinateur de l’écouteur est connecté (privé/public/domaine). Si l’ordinateur écouteur n’est pas joint à un domaine, le réseau peut être répertorié comme public et, dans ce cas, les règles de pare-feu installées avec le Gestionnaire de statistiques ne s’appliquent pas par défaut.

- **4000** — Échec du téléchargement des informations du serveur à partir de l’écouteur (raison inconnue)

  - **4001** — Serveur introuvable dans la topologie de l’écouteur

    Cette erreur se produit si le serveur se connecte correctement à l’écouteur, mais que le serveur n’a pas été ajouté à la topologie dans le cache de l’écouteur. Options de résolution :

  - Veillez à suivre les instructions d’importation de la topologie. Voir [Importer la topologie](deploy.md#BKMK_ImportTopology).

  - Si l’Agent se trouve sur un serveur qui n’est pas répertorié dans la topologie (par exemple, les nœuds d’un cluster SQL AlwaysOn), vous devez ajouter l’Agent manuellement en suivant les instructions fournies dans [Importer la topologie](deploy.md#BKMK_ImportTopology).

  - **4002** — Mot de passe de l’écouteur non valide

    Le mot de passe chiffré que l’agent tente d’utiliser ne correspond pas au mot de passe de service sur l’écouteur lui-même. Désinstallez l’Agent et réinstallez-le à l’aide du mot de passe de service approprié.

  - **4003** — Incompatibilité de l’empreinte numérique du certificat

    L’empreinte numérique du certificat donnée à l’Agent au moment de l’installation ne correspond pas à l’empreinte numérique sur le certificat que l’écouteur utilise actuellement et, par conséquent, la connexion sera refusée. Désinstallez l’Agent et réinstallez-le à l’aide de l’empreinte numérique du certificat appropriée.

  - **4004** — Réponse non valide ou HttpStatusCode

    L’écouteur ne répond pas avec un état attendu.

  - Si la connexion est établie, vérifiez la configuration du proxy.

  - Vérifiez dans le journal StatsMan de l’écouteur les problèmes liés à sa configuration.

  - **4005** — Impossible de désérialiser le code XML

    Les informations du serveur sur le serveur d’écoute sont endommagées ou il peut y avoir une incompatibilité de version entre l’agent et les ordinateurs de l’écouteur. Vérifiez que les versions correspondent et recherchez les problèmes dans le journal des événements de l’écouteur.

## <a name="listener-events"></a>Événements de l’écouteur
<a name="BKMK_Listener"> </a>

- **10000** — Échec du démarrage : raison inconnue (celles-ci ne sont pas récupérables et le service s’arrête/se bloque par conséquent)

  - **10001** — Problème de configuration

    En règle générale, cela se produit lorsque le fichier [listener_install_location]\PerfAgentListener.exe.config a été modifié manuellement et ne peut pas être lu par l’application.

  - **10002** — Erreur d’initialisation de l’écouteur HTTP

    Cet événement est généralement journalisé lorsque la liste de contrôle d’accès d’URL n’a pas été définie correctement pendant l’installation ou que le certificat SSL n’est pas valide. Vérifiez que le certificat dans votre configuration est valide. Si c’est le cas, réinstallez l’écouteur conformément aux instructions de [Deploy Statistics Manager](deploy.md#BKMK_Deploy).

  - **10003** — Échec de Redis

  - **10004** — Échec de mise en cache de l’infrastructure

  - **10007** — Paramètres (stocké dans redis)

    L’écouteur n’a pas pu contacter Redis ou récupérer des données bien formées à partir du cache et n’a pas pu démarrer. Vérifiez que le service Redis est démarré et configuré correctement sur le serveur.

  - **10005** — Récupération/analyse des informations serveur

    Les informations de topologie dans le cache Redis ne sont pas valides. Tout d’abord, essayez de redémarrer Redis et l’écouteur. Si l’erreur persiste, consultez [Importer la topologie](deploy.md#BKMK_ImportTopology) pour recréer les données de topologie.

- **10100** — Panne ping redis

  - **10101** — Redis PING continue sa panne (toutes les 60 secondes)

  - **30100** — Restauration d’une panne PING Redis

    Ceux-ci sont enregistrés lorsque l’écouteur ne peut pas se connecter à Redis. Vérifiez que Redis est démarré et que la connectivité réseau entre l’écouteur et Redis est disponible.

- **10200** — Panne d’écriture Redis

  - **10201** — La panne d’écriture Redis s’est poursuivie (toutes les 60 secondes)

  - **30100** — Panne d’écriture Redis résolue

    Ceux-ci sont enregistrés lorsque l’écouteur ne peut pas écrire dans le cache Redis. Vérifiez que Redis est démarré et que la connectivité réseau entre l’écouteur et Redis est disponible.

- **30000** — Démarrage réussi

    Journalisé chaque fois que l’écouteur est démarré.

- **22000** — L’initialisation de Statistics Manager Agent a réussi.

- **23000** — L’initialisation d’EventLogQueryManager a réussi (première fois ou après échec)

- **24000** — L’initialisation de serverinfo a réussi (première fois ou après échec)

- **25000** — L’écouteur est de retour en ligne après l’échec de la publication (ou la première publication réussie)

- **5000** — Démarrage de l’écouteur hors connexion pour la publication de données

- **5001** — L’écouteur est toujours hors connexion pendant une période prolongée

    Ces événements peuvent être utiles pour surveiller/alerter/effacer les problèmes.

## <a name="website-issues"></a>Problèmes de site web
<a name="BKMK_Website"> </a>

- Invites de connexion répétitives dans Chrome : il s’agit d’un bogue résolu dans la version 1.1. Assurez-vous d’avoir effectué une mise à niveau vers la dernière version de Statistics Manager si vous voyez des invites de connexion répétées dans le navigateur Chrome. Pour vérifier la version du site web que vous exécutez :

  - Dans Explorateur de fichiers, ouvrez (répertoire par défaut)

  - Cliquez avec le bouton droit sur StatsManHubWebSite.dll et affichez ses propriétés.

  - Si un ordinateur est introuvable en mode Paysage KHI ou en mode Détails du compteur, assurez-vous qu’il est membre d’un site et d’un pool. Si ce n’est pas le cas, il n’apparaîtra pas dans ces vues. Pour plus d’informations sur la définition d’un site et d’un pool pour un serveur dans la topologie, consultez [Importer la topologie](deploy.md#BKMK_ImportTopology).

  - La version du produit s’affiche dans les détails de la description.

## <a name="for-more-information"></a>Pour plus d'informations
<a name="BKMK_Website"> </a>

Pour plus d'informations, consultez les articles suivants :

- [Planifier le gestionnaire de statistiques pour Skype Entreprise Server](plan.md)

- [Déploiement du gestionnaire de statistiques pour Skype Entreprise Server](deploy.md)

- [Mise à niveau du gestionnaire de statistiques pour Skype Entreprise Server](upgrade.md)
