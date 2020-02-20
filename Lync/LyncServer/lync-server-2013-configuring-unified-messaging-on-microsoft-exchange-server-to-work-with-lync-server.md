---
title: 'Lync Server 2013 : configuration de la messagerie unifiée sur Microsoft Exchange Server pour qu’elle fonctionne avec Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Unified Messaging on Microsoft Exchange Server to work with Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398106(v=OCS.15)
ms:contentKeyID: 48183289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25535ee2a2b6a1dfc0cc88202b84fb7e083428c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Configuration de la messagerie unifiée sur Microsoft Exchange Server pour qu’elle fonctionne avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-11_

<div>


> [!IMPORTANT]  
> Si vous souhaitez utiliser la messagerie unifiée Exchange pour fournir des services de répondeur automatique, Outlook Voice Access ou de standard automatique pour les utilisateurs de voix entreprise, lisez la rubrique <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planning for Exchange Unified Messaging Integration in Lync Server 2013</A> dans la documentation de planification, puis suivez les instructions de cette section.



</div>

Pour configurer la messagerie unifiée Exchange de sorte qu’elle fonctionne avec voix entreprise, vous devez effectuer les tâches suivantes :

  - Configurer des certificats sur le serveur exécutant les services de messagerie unifiée (MU) Exchange
    
    <div>
    

    > [!NOTE]  
    > Ajoutez tous les serveurs d’accès au client et de boîtes aux lettres à tous les plans de numérotation URI SIP de messagerie unifiée. Si ce n’est pas le cas, le routage des appels sortants ne fonctionnera pas comme prévu.

    
    </div>

  - Créez un ou plusieurs plans de numérotation URI SIP de messagerie unifiée, ainsi que les numéros de téléphone d’accès abonné, si nécessaire, puis créez les plans de numérotation Lync Server correspondants.

  - Utilisez le script **exchucutil. ps1** pour :
    
      - créer des passerelles IP de messagerie unifiée ;
    
      - créer des groupements de postes de messagerie unifiée ;
    
      - Accordez l’autorisation Lync Server 2013 pour lire les objets des services de domaine Active Directory de messagerie unifiée.

  - Créez un objet de standard automatique de messagerie unifiée.

  - Créez un objet d’accès abonné.

  - Créez un URI SIP pour chaque utilisateur et associez les utilisateurs à un plan de numérotation URI SIP de messagerie unifiée.

<div>

## <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Avant de commencer, la documentation de cette section suppose que vous ayez déployé les rôles Exchange 2013 suivants : accès au client et boîte aux lettres. Dans Microsoft Exchange Server 2013, la messagerie unifiée Exchange s’exécute en tant que service sur ces serveurs.

Pour plus d’informations sur le déploiement d’Exchange 2013, reportez-vous à la bibliothèque TechNet Exchange 2013 à l’adresse[https://go.microsoft.com/fwlink/p/?LinkId=266637](https://go.microsoft.com/fwlink/p/?linkid=266637)

Notez également les points suivants :

  - Si la messagerie unifiée Exchange est installée dans plusieurs forêts, les étapes d’intégration d’Exchange Server doivent être effectuées pour chaque forêt de messagerie unifiée. De plus, chaque forêt de messagerie unifiée doit être configurée pour approuver la forêt dans laquelle Lync Server 2013 est déployé, et la forêt dans laquelle Lync Server 2013 est déployé doit être configurée pour approuver chaque forêt de messagerie unifiée.

  - Les étapes d’intégration sont effectuées sur les rôles serveur Exchange où les services de messagerie unifiée sont en cours d’exécution et sur le serveur exécutant Lync Server 2013. Vous devez effectuer les étapes d’intégration de la messagerie unifiée Exchange Server avant d’effectuer les étapes d’intégration de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Pour connaître les étapes d’intégration qui sont appliquées aux serveurs et aux rôles d’administrateur, voir <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processus de déploiement pour l’intégration de la messagerie unifiée locale et Lync Server 2013</A>.

    
    </div>

Les outils suivants doivent être disponibles sur chaque serveur exécutant la messagerie unifiée Exchange :

  - Environnement de ligne de commande Exchange Management Shell

  - Le script **exchucutil.ps1**, exécute les tâches suivantes :
    
      - Il crée une passerelle IP de messagerie unifiée pour chaque Lync Server 2013.
    
      - Il crée un groupement de postes pour chaque passerelle. L’identificateur pilote de chaque groupement de postes spécifie le plan de numérotation URI SIP de messagerie unifiée utilisé par le pool frontal ou le serveur Standard Edition Server associé à la passerelle.
    
      - Accorde l’autorisation Lync Server 2013 pour lire les objets de messagerie unifiée Exchange dans les services de domaine Active Directory.

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configuration de la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

