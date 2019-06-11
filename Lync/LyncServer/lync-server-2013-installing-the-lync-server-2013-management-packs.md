---
title: 'Lync Server 2013: installation des packs d’administration de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Installation des packs d’administration de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-22_

Le gestionnaire des opérations de System Center a la possibilité de surveiller uniquement une petite partie du système d’exploitation Windows. Toutefois, vous pouvez développer les fonctionnalités de System Center Operations Manager en installant des packs d’administration, des logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, y compris la façon dont ces éléments doivent être surveillés et la façon dont les alertes doivent être déclenché et signalé. Microsoft Lync Server 2013 inclut deux packs d’administration System Center Operations Manager qui fournissent les fonctionnalités suivantes:

  - Le Pack de gestion des utilisateurs et des composants (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes du serveur Lync enregistrés dans les journaux d’événements, inscrits par des compteurs de performance ou enregistrés dans les enregistrements des détails des appels ou sur la qualité de l’utilisation (QoE). bases de données. Pour les problèmes critiques, System Center Operations Manager peut être configuré pour notifier immédiatement les administrateurs par courrier électronique, message instantané ou messagerie de courte durée de réception de messages. SMS est la technologie utilisée pour envoyer des messages texte d’un appareil mobile à un autre.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur la configuration de la notification Operations Manager, consultez la rubrique Configuration de <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>la notification dans la bibliothèque TechNet à l’adresse.

    
    </div>

  - Le pack d’analyse actif (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) vérifie de manière proactive les principaux composants du serveur Lync tels que la connexion au système, l’échange de messages instantanés ou l’appel d’appels vers un téléphone situé sur le téléphone public commuté réseau commuté (RTC). Ces tests sont effectués à l’aide des cmdlets de transaction synthétique de Lync Server. Par exemple, l’applet de **contrôle test-CsIM** est utilisée pour simuler une conversation par messagerie instantanée entre deux utilisateurs de test. Si cette conversation de messagerie simulée échoue, une alerte est générée.

Les deux packages d’administration inclus dans Lync Server 2013 incluent un grand nombre d’améliorations sur les packs de gestion utilisés avec Microsoft Lync Server 2010. Par exemple, le Pack de gestion des composants de Lync Server 2013 n’est pas limité à la surveillance de Lync Server. Outre le suivi des journaux d’événements et des compteurs de performance pour Lync Server, le Pack de gestion des composants peut également suivre les performances des éléments cruciaux et en émettre des alertes, tels que:

  - **Des alertes d’Internet Information Services (IIS)**   seront émises si Internet Information Services se déconnecte. C’est important, car les services Web de Lync Server dépendent d’IIS.

  - ****   Les alertes d’utilisation du processus sont émises si les ressources système (telles que la mémoire disponible) commencent à s’exécuter faiblement. Ces alertes sont émises même si Lync Server n’est pas responsable de l’utilisation importante du système.

  - ****   Les alertes d’événements d’échec d’ordinateur sont émises en cas de problème matériel ou logiciel qui menace la viabilité d’un serveur. Par exemple, les administrateurs du serveur Lync seront avertis si un serveur semble être menacé par une défaillance de disque dur.

Les nouveaux modules de gestion permettent également d’améliorer la création de rapports. Les nouveaux rapports pour Lync Server 2013 incluent:

  - **Rapport de disponibilité du scénario de bout en bout**   ce rapport décrit en détail la disponibilité des services principaux de Lync Server tels que l’inscription ou la présence.

  - **Rapport de capacité**   utilisant des informations de compteurs de performance, ce rapport affiche des tendances pour les composants système tels que la disponibilité de la mémoire et l’utilisation du processeur.

  - **Rapport de composant**   ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.

Outre ces rapports prédéfinis, les packs de gestion pour Lync Server 2013 signalent automatiquement les alertes pour la fiabilité des appels (métriques mesurées par enregistrement des détails des appels) et les États QoE (métriques mesurées par qualité d’expérimentation). Si vous avez activé l’enregistrement des détails des appels, vous pouvez passer en revue les alertes de fiabilité des appels en effectuant les étapes suivantes à partir de la console System Center Operations Manager:

  - Développez **analyse**, développez **État de Microsoft Lync Server 2013**, développez **fiabilité des appels et qualité multimédia**, puis cliquez sur **fiabilité des appels**.

Pour afficher des alertes de qualité de l’utilisation, procédez comme suit dans la console System Center Operations Manager:

  - Développez **analyse**, développez **État de Microsoft Lync Server 2013**, développez **fiabilité des appels et qualité multimédia**, puis développez **qualité multimédia**.

Les packs de gestion pour Lync Server 2013 utilisent désormais une découverte au niveau de l’ordinateur au lieu du mécanisme de découverte centralisé utilisé dans Microsoft Lync Server 2010. En d’autres termes, chacun de ses agents s’en charge et signale son existence au serveur de gestion central. L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure de centre système et permet également d’utiliser différentes versions des packs de gestion Lync Server (par exemple, les packs d’administration de Lync Server 2010 et les modules de gestion pour Lync Server 2013) sur coexister.

</div>

<span> </span>

</div>

</div>

</div>

