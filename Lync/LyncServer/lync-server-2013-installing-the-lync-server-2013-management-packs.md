---
title: 'Lync Server 2013 : installation des packs d’administration Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a6cd3ca0c58a6101d6e46e253e3edf09dec025
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a>Installation des packs d’administration Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Par lui-même, System Center Operations Manager a la possibilité de surveiller uniquement une petite partie du système d’exploitation Windows. Toutefois, vous pouvez étendre les fonctionnalités de System Center Operations Manager en installant les packs d’administration, les logiciels qui déterminent les éléments que System Center Operations Manager peut surveiller, y compris la façon dont ces éléments doivent être surveillés et la façon dont les alertes doivent être déclenchés et signalés. Microsoft Lync Server 2013 comprend deux packs d’administration System Center Operations Manager qui offrent les fonctionnalités suivantes :

  - Le pack d’administration des composants et des utilisateurs (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) effectue le suivi des problèmes Lync Server enregistrés dans les journaux des événements, enregistrés par des compteurs de performance ou consignés dans les enregistrements des détails des appels ou sur la qualité de l’expérience (QoE). bases. Pour les problèmes critiques, System Center Operations Manager peut être configuré pour informer immédiatement les administrateurs via la messagerie électronique, la messagerie instantanée ou la messagerie SMS (Short Message Service). La technologie des SMS est utilisée pour envoyer des messages texte d’un appareil mobile à un autre.
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur la configuration de la notification Operations Manager, voir Configuration de la notification <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>dans la bibliothèque TechNet à l’adresse.

    
    </div>

  - Le Pack de surveillance active (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) teste de manière proactive les principaux composants de Lync Server, tels que la connexion au système, l’échange de messages instantanés ou l’appel à un téléphone situé sur le téléphone commuté public. réseau téléphonique commuté (RTC). Ces tests sont effectués à l’aide des applets de commande de transaction synthétique Lync Server. Par exemple, l’applet de commande **Test-CsIM** est utilisée pour simuler une conversation de messagerie instantanée entre deux utilisateurs de test. Si la conversation de messagerie simulée échoue, une alerte est générée.

Les deux packs d’administration fournis avec Lync Server 2013 incluent un grand nombre d’améliorations par rapport aux packs d’administration utilisés avec Microsoft Lync Server 2010. Par exemple, le pack d’administration des composants Lync Server 2013 n’est pas limité à la surveillance de Lync Server lui-même. Outre la surveillance des journaux d’événements et des compteurs de performance pour Lync Server, le pack d’administration des composants peut également suivre les performances des alertes et émettre des alertes pour les éléments cruciaux tels que :

  - **Des alertes Internet Information Services (IIS)**   sont émises si Internet Information Services est mis en mode hors connexion. Ceci est important, car les services Web Lync Server s’appuient sur IIS.

  - ****   Les alertes d’utilisation de processus sont émises si les ressources système (telles que la mémoire disponible) commencent à manquer. Ces alertes seront émises même si Lync Server n’est pas responsable de l’utilisation élevée du système.

  - **Événements de défaillance d’ordinateur**   les alertes seront émises en cas de problème matériel ou logiciel susceptible de menacer la viabilité d’un serveur. Par exemple, les administrateurs Lync Server seront avertis si un serveur semble être menacé par une défaillance du disque dur.

Les nouveaux packs d’administration proposent également une création de rapports améliorée. Les nouveaux rapports pour Lync Server 2013 sont les suivants :

  - **Rapport de disponibilité des scénarios de bout en bout**   ce rapport présente la disponibilité/temps de fonctionnement des services Lync Server clés tels que l’inscription ou la présence.

  - **Rapport de capacité**   à l’aide des informations des compteurs de performance, ce rapport affiche les tendances des composants système, notamment la disponibilité de la mémoire et l’utilisation du processeur.

  - **Rapport de composants**   ce rapport répertorie les principaux générateurs d’alertes regroupés par composant Lync Server.

En plus de ces rapports prédéfinis, les packs d’administration de Lync Server 2013 signalent automatiquement les alertes pour la fiabilité des appels (mesures mesurées par l’enregistrement des détails des appels) et les États de QoE (mesures mesurées par qualité de l’expérience). Si vous avez activé l’enregistrement des détails des appels, vous pouvez passer en revue les alertes de fiabilité des appels en effectuant la procédure suivante à partir de la console System Center Operations Manager :

  - Développez **Surveillance**, **Intégrité de Microsoft Lync Server 2013** et **Fiabilité des appels et qualité des médias**, puis cliquez sur **Fiabilité des appels**.

Pour afficher les alertes de qualité de l’expérience, effectuez cette procédure à partir de la console System Center Operations Manager :

  - Développez **Surveillance**, **Intégrité de Microsoft Lync Server 2013** et **Fiabilité des appels et qualité des médias**, puis cliquez sur **Qualité des médias**.

Les packs d’administration de Lync Server 2013 utilisent désormais la découverte au niveau de l’ordinateur au lieu du mécanisme de découverte central utilisé dans Microsoft Lync Server 2010. Cela signifie que chaque agent System Center se trouve essentiellement et rend compte de son existence au serveur de gestion centralisée. L’utilisation de la découverte au niveau de l’ordinateur simplifie l’administration de votre infrastructure System Center et permet également différentes versions des packs d’administration Lync Server (par exemple, les packs d’administration pour Lync Server 2010 et les packs d’administration pour Lync Server 2013) pour exister.

</div>

<span> </span>

</div>

</div>

</div>

