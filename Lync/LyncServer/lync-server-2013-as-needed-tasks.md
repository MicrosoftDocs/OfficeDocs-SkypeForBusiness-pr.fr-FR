---
title: 'Lync Server 2013 : tâches en fonction des besoins'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a819fad54bbd19be842f7ae28f655186135b50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Tâches nécessaires dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-18_

Effectuez les tâches suivantes si nécessaire. Ils sont souvent également couverts par les procédures standard :

  - **Audit de sécurité complet   ** Vous pouvez effectuer cet audit régulièrement, en réponse à une mise à niveau ou à une nouvelle conception du système de messagerie, ou en réponse à une violation de sécurité. La procédure peut impliquer des analyses de ports sur les serveurs et pare-feu, des audits de correctifs de sécurité et des tests de pénétration tiers.

  - **Remplacer les certificats sur le terme de l’expiration**   de la vérification les certificats Lync Server sont l’une des tâches hebdomadaires normales et, dans le cadre de la procédure, un administrateur doit disposer d’un enregistrement de la date d’expiration de tous les certificats. Cet enregistrement permet à un administrateur de créer une notification lorsqu’un certificat particulier est sur le sujet de la date d’expiration et remplacé si nécessaire.

  - ****   Mise à jour des lignes de base des performances mettez à jour les lignes de base des performances après une modification ou une modification de la configuration. Votre organisation peut utiliser des lignes de base pour mesurer les changements de performances et détecter les problèmes qui affectent les performances du système.

  - **La gestion**   de la configuration initiale des pools d’entreprise des pools d’entreprise, des serveurs Standard Edition et de tous les autres serveurs de l’environnement de votre organisation a été réalisée lors du déploiement des serveurs individuels. La gestion post-déploiement des serveurs et des pools pour les serveurs Standard Edition et les pools d’entreprise comprend les tâches suivantes :
    
      - Gestion de serveurs frontaux
    
      - Gestion des conférences Web
    
      - Gestion des conférences
    
      - Modification des informations d’identification du compte de service
    
      - Gestion des bases de données
    
      - Démarrage et arrêt des services et désactivation des rôles serveur
    
      - Suppression des serveurs et des rôles serveur, suppression des pools et mise hors service des serveurs et pools

  - **Gestion de l’utilisation**   vous pouvez configurer Lync Server 2013 pour fournir les fonctionnalités les plus appropriées pour votre organisation. Les voici :
    
      - Gestion de la prise en charge des réunions de conférence Web sur site
    
      - Gestion de l’utilisation des groupes de distribution pour envoyer des messages instantanés
    
      - Gestion des contacts, de la présence et des requêtes
    
      - Configuration du filtrage de version du client
    
      - Configuration du filtrage de messagerie instantanée intelligent
    
      - Configuration de l’archivage, de l’enregistrement des détails des appels et de la conformité aux réunions

  - **Gestion**   de la connectivité de serveur Edge la gestion continue des serveurs et des paramètres requis pour fournir la connectivité externe inclut les éléments suivants :
    
      - Gestion de la connectivité entre les serveurs internes et les serveurs Edge
    
      - Configuration des interfaces internes et externes et des certificats pour les serveurs Edge
    
      - Gestion de l’accès des partenaires fédérés

  - **Administrer le carnet d'**   adresses les serveurs de carnets d’adresses incluent les éléments suivants :
    
      - Configuration de la normalisation des téléphones du serveur de carnet d’adresses
    
      - Gestion du serveur de carnet d’adresses à partir de la ligne de commande

  - ****   La gestion des comptes d’utilisateur pour la gestion des comptes d’utilisateurs comprend les éléments suivants :
    
      - Activation des comptes d’utilisateur pour Lync Server
    
      - Configuration des utilisateurs de Lync Server à l’aide de l’Assistant
    
      - Configuration des propriétés de compte d’utilisateur Lync Server individuelles
    
      - Recherche d’utilisateurs Lync Server
    
      - Migration des utilisateurs de Lync Server
    
      - Suppression d’utilisateurs Lync Server

  - **Analyse des fichiers**   journaux Lync Server 2013 un outil très utile, généralement utilisé pour la résolution des problèmes, est l’outil de journalisation Lync Server 2013 décrit en détail dans [utilisation de l’outil de journalisation Lync Server 2013](https://technet.microsoft.com/library/gg558599.aspx).

Étant donné que l’outil de journalisation génère des fichiers journaux (par serveur), ces fichiers journaux peuvent être affichés et analysés à l’aide de l’outil Snooper, si les outils du kit de ressources Microsoft Office Server 12 sont installés sur l’ordinateur. Dans le cas contraire, les journaux peuvent également être analysés à l’aide d’un éditeur de texte, ce qui est bien moins transparent et plus complexe que l’utilisation de l’utilitaire de surveillance.

Pour afficher et analyser les messages de protocole

Dans l’outil de journalisation, lorsque vous avez terminé la session de débogage, cliquez sur analyser les fichiers journaux pour afficher les fichiers journaux à l’aide de l’outil Snooper. Vous pouvez analyser les journaux de protocole pour les composants suivants :

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Trafic de signalisation de conférence Lync Server (C3P), y compris le trafic MCU C3P et le focus C3P

  - Trafic de conférence Web Lync Server (PSOM)

  - Client de plateforme de communications unifiées Lync Server (UCCP)

  - Rapports d’erreur de la base de données d’archivage

Pour vous aider à organiser les performances des tâches selon vos besoins, voir liste de vérification des opérations selon vos besoins.

<div>


> [!IMPORTANT]  
> Pour plus d’informations sur les procédures d’administration et de gestion, consultez le Guide d’administration de Microsoft Lync Server 2013.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Stratégies de sauvegarde (et restauration) ou paramètres de configuration

Lync Server 2013 permet de sauvegarder et de restaurer l’ensemble du système. IIF que vous souhaitez sauvegarder (et éventuellement effectuer une restauration à un jour) une seule stratégie ou une seule collection de paramètres de configuration, récupérez la stratégie appropriée, puis dirigez cet objet vers la cmdlet Export-Clixml, qui enregistre les informations de stratégie sous la forme d’un fichier XML :

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Vous pouvez maintenant expérimenter RedmondClientPolicy et modifier un grand nombre de paramètres. Si, au lieu de cela, vous décidez de restaurer l’ancienne stratégie, entrez :

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Notez que cette approche fonctionnera pour la plupart des stratégies et des paramètres, mais elle ne fonctionnera pas avec certains des éléments plus complexes : les éléments qui contiennent plusieurs sous-objets (par exemple, les paramètres de configuration de routage, qui contiennent un grand nombre d’itinéraires vocaux distincts).

</div>

</div>

<span> </span>

</div>

</div>

</div>

