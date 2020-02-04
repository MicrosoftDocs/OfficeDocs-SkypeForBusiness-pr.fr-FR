---
title: 'Lync Server 2013 : Configuration de la messagerie unifiée sur Microsoft Exchange Server de sorte qu’elle fonctionne avec Lync Server'
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
ms.openlocfilehash: 5e2bc41d4fa0411c4184c0edda35d6d0cd98df9a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-unified-messaging-on-microsoft-exchange-server-to-work-with-lync-server-2013"></a>Configuration de la messagerie unifiée sur Microsoft Exchange Server de sorte qu’elle fonctionne avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-11_

<div>


> [!IMPORTANT]  
> Si vous souhaitez utiliser la messagerie unifiée Exchange pour fournir des services de réponse d’appel, Outlook Voice Access ou de standard automatique pour les utilisateurs voix entreprise, consultez la rubrique <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013</A> dans la documentation de planification, puis suivez les instructions de cette section.



</div>

Pour configurer la messagerie unifiée (MU) Exchange pour qu’elle fonctionne avec la voix entreprise, vous devez effectuer les tâches suivantes :

  - Configurer des certificats sur le serveur exécutant les services de messagerie unifiée Exchange
    
    <div>
    

    > [!NOTE]  
    > Ajoutez tous les serveurs d’accès client et de boîte aux lettres à toutes les offres de numérotation URI SIP UM. Si ce n’est pas le cas, le routage des appels sortants ne fonctionne pas comme prévu.

    
    </div>

  - Créez un ou plusieurs plans de numérotation URI SIP UM, ainsi que les numéros de téléphone d’accès d’abonné, le cas échéant, puis créez les plans de numérotation de serveur Lync correspondants.

  - Utilisez le script **exchucutil. ps1** pour effectuer les opérations suivantes :
    
      - Créer des passerelles IP de messagerie unifiée.
    
      - Créer des groupes de recherche de MU.
    
      - Accordez l’autorisation Lync Server 2013 pour lire les objets services de domaine Active Directory de messagerie unifiée.

  - Créer un objet de standard automatique de messagerie unifiée.

  - Créer un objet d’accès abonné.

  - Créer un URI SIP pour chaque utilisateur et en associant les utilisateurs à l’aide d’un plan de numérotation URI SIP UM.

<div>

## <a name="requirements-and-recommendations"></a>Conditions requises et recommandations

Avant de commencer, la documentation de cette section suppose que vous avez déployé les rôles Exchange 2013 suivants : accès client et boîte aux lettres. Dans Microsoft Exchange Server 2013, la messagerie unifiée Exchange s’exécute en tant que service sur ces serveurs.

Pour plus d’informations sur le déploiement d’Exchange 2013, voir la bibliothèque TechNet Exchange 2013 sur[http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Notez également ce qui suit :

  - Si Exchange UM est installé dans plusieurs forêts, vous devez effectuer les étapes d’intégration d’Exchange Server pour chaque forêt de messagerie unifiée. De plus, chaque forêt de messagerie unifiée doit être configurée pour approuver la forêt dans laquelle Lync Server 2013 est déployé et la forêt dans laquelle Lync Server 2013 est déployée doit être configurée pour approuver chaque forêt de messagerie unifiée.

  - Des étapes d’intégration sont effectuées à la fois sur les rôles de serveur Exchange et sur le serveur exécutant Lync Server 2013. Vous devez effectuer les étapes d’intégration de la messagerie unifiée Exchange Server avant d’effectuer les étapes d’intégration de Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > Pour savoir quelles étapes d’intégration sont exécutées sur les serveurs et quels rôles d’administrateur, voir <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</A>.

    
    </div>

Les outils suivants doivent être disponibles sur chaque serveur exécutant la messagerie unifiée Exchange :

  - Exchange Management Shell

  - Le script **exchucutil. ps1**, qui effectue les tâches suivantes :
    
      - Crée une passerelle IP de MU pour chaque serveur Lync Server 2013.
    
      - Crée un groupe de recherche pour chaque passerelle. L’identificateur pilote de chaque groupe de recherche spécifie le plan de numérotation d’URI SIP de MU utilisé par le pool frontal ou le serveur Standard Edition associé à la passerelle.
    
      - Octroie à Lync Server 2013 une autorisation de lecture d’objets de messagerie unifiée Exchange dans les services de domaine Active Directory.

</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configurer des certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

