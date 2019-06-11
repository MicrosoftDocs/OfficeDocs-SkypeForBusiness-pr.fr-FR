---
title: 'Lync Server 2013: tâches au besoin'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e96fd6e73e043c5ea7c476f939b3a3e06eadbdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Tâches selon les besoins dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-08-18_

Effectuez les tâches suivantes si nécessaire. Ils sont souvent couverts par des procédures standard:

  - **Contrôle total   ** de la sécurité Vous pouvez effectuer ce contrôle régulièrement, en réponse à une mise à niveau ou une nouvelle conception du système de messagerie, ou en réponse à une faille de sécurité lancée (ou réussie). Cette procédure est susceptible de nécessiter des analyses de port sur les serveurs et les pare-feu, d’audit des correctifs de sécurité et de tests de pénétration de tiers.

  - **Remplacer les certificats concernant pour**   expirer vérification le certificat de serveur Lync est l’une des tâches hebdomadaires normales et dans le cadre de la procédure qu’un administrateur doit avoir un enregistrement de la date d’expiration de tous les certificats. Cet enregistrement permet à un administrateur de créer une notification lorsqu’un certificat particulier est sur le lieu d’avoir expiré et remplacé selon les besoins.

  - ****   Mise à jour des résultats de performance mettez à jour les références de performance suite à une mise à niveau ou modification de la configuration. Votre organisation peut utiliser des plannings de référence pour mesurer les changements de performances et détecter les problèmes qui affectent les performances du système.

  - **La gestion**   de la configuration initiale du pool d’entreprise, des serveurs Standard Edition et de tout autre serveur dans l’environnement de votre organisation, s’est effectuée lors du déploiement de chaque serveur. La gestion après le déploiement de serveurs et de pools pour les serveurs Standard Edition et les pools d’entreprise inclut les tâches suivantes:
    
      - Gestion des serveurs frontaux
    
      - Gestion des conférences Web
    
      - Gestion des conférences
    
      - Modification des informations d’identification d’un compte de service
    
      - Gestion des bases de données
    
      - Démarrage et arrêt des services et désactivation des rôles de serveur
    
      - Suppression de serveurs et de rôles de serveur, suppression de pools et désaffectation de serveurs et de pools

  - **Gestion de l’utilisation**   vous pouvez configurer Lync Server 2013 pour proposer les fonctionnalités et fonctionnalités qui conviennent le mieux à votre organisation. Il s’agit notamment de ce qui suit :
    
      - Gestion de la prise en charge des réunions locales de conférences sur le Web
    
      - Gestion de l’utilisation des groupes de distribution pour envoyer des messages instantanés
    
      - Gestion des contacts, de la présence et des requêtes
    
      - Configuration du filtrage des versions du client
    
      - Configuration du filtrage du message instantané intelligent
    
      - Configuration de l’archivage, de l’enregistrement des détails des appels et de la conformité aux réunions

  - ****   Gestion en continu de la connectivité Edge Server les serveurs et les paramètres requis pour fournir une connectivité externe incluent les éléments suivants:
    
      - Gestion de la connectivité entre les serveurs internes et les serveurs Edge
    
      - Configuration d’interfaces et de certificats internes et externes pour les serveurs Edge
    
      - Gestion de l’accès des partenaires fédérés

  - **L’administration du carnet d'**   adresses qui administre les serveurs du carnet d’adresses inclut les éléments suivants:
    
      - Configuration de la normalisation du téléphone du serveur du carnet d’adresses
    
      - Gestion du serveur du carnet d’adresses à partir de la ligne de commande

  - ****   La gestion des comptes d’utilisateur pour la gestion des comptes d’utilisateurs comprend les éléments suivants:
    
      - Activation de comptes d’utilisateur pour Lync Server
    
      - Configuration des utilisateurs de Lync Server à l’aide de l’Assistant
    
      - Configuration de propriétés de compte d’utilisateur Lync Server individuelles
    
      - Rechercher des utilisateurs de Lync Server
    
      - Déplacement des utilisateurs de Lync Server
    
      - Supprimer des utilisateurs de Lync Server

  - ****   Pour résoudre les problèmes, l’outil de journalisation de Lync Server 2013 est décrit en détail dans [l’article utilisation de l’outil journal](http://technet.microsoft.com/en-us/library/gg558599.aspx)de Lync Server 2013.2013

Dans la mesure où l’outil journalisation génère des fichiers journaux (sur la base du serveur), ces fichiers journaux peuvent être affichés et analysés à l’aide de l’outil Snoop, si les outils du kit de ressources Microsoft Office Server 12 sont installés sur l’ordinateur. Dans le cas contraire, les journaux peuvent également être analysés à l’aide d’un éditeur de texte, qui est beaucoup moins transparent et plus complexe que l’utilisation de l’utilitaire Snoop.

Pour afficher et analyser les messages de protocole

Dans l’outil journalisation, une fois que vous avez terminé la session de débogage, cliquez sur analyse des fichiers journaux pour afficher les fichiers journaux à l’aide de l’outil de vérification de l’utilisation. Vous pouvez analyser les journaux de protocole pour les composants suivants:

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Trafic de signalisation des conférences Lync Server (C3P), y compris MCU infra C3P et Focus C3P

  - Trafic de conférence Web Lync Server (PSOM)

  - Client de plate-forme client de communications unifiées Lync Server (UCCP)

  - Rapports d’erreur de la base de données d’archivage

Pour vous aider à organiser les performances des tâches au besoin, voir liste de contrôle des opérations selon les besoins.

<div>


> [!IMPORTANT]  
> Pour obtenir des instructions d’administration et de gestion détaillées, voir le Guide d’administration de Microsoft Lync Server 2013.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Backup (and Restore) ou paramètres de configuration

Lync Server 2013 vous permet de sauvegarder et de restaurer tout le système. IIF vous voulez sauvegarder (et peut-être restaurer une seule action) une seule stratégie ou une collection unique de paramètres de configuration, récupérer la stratégie appropriée, puis canalr cet objet vers l’applet de passe Export-Clixml, qui enregistre les informations de stratégie sous forme de fichier XML:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Vous pouvez maintenant tester RedmondClientPolicy et modifier de nombreux paramètres. Si vous préférez procéder à la restauration de l’ancienne stratégie, entrez:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Notez que cette approche fonctionne pour la plupart des stratégies et des paramètres, mais qu’elle ne fonctionne pas avec certains éléments plus complexes, c’est-à-dire des éléments contenant plusieurs sous-objets (par exemple, les paramètres de configuration de routage, qui contiennent de nombreux itinéraires vocaux différents).

</div>

</div>

<span> </span>

</div>

</div>

</div>

