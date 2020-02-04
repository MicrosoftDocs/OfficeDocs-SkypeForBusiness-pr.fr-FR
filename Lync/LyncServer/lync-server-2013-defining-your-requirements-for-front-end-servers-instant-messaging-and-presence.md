---
title: 'Lync Server 2013 : Définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La principale tâche de planification de la messagerie instantanée et de la présence consiste à vérifier que vous disposez de suffisamment de serveurs front-end pour vos utilisateurs.

<div>

## <a name="enabling-communication-with-external-users"></a>Activation de la communication avec des utilisateurs externes

Vous pouvez considérablement augmenter les avantages de votre investissement dans Lync Server en permettant aux utilisateurs de communiquer avec des utilisateurs externes. Exemples d’utilisateurs externes :

  - **Utilisateurs distants**   les utilisateurs de votre organisation qui travaillent à l’extérieur de votre pare-feu et qui utilisent leur ordinateur portable ou d’autres appareils Lync Server.

  - **Utilisateurs fédérés utilisateurs**   de sociétés qui travaillent également sur Lync Server. Pour autoriser vos utilisateurs à communiquer facilement avec ces utilisateurs externes, créez des relations fédérées avec ces entreprises.

  - **Utilisateurs publics :**   utilisateurs de services de messagerie instantanée publics, tels que les services de messagerie instantanée fournis par le réseau Windows\!Live de services Internet, Yahoo et AOL, et utilisateurs de fournisseurs et de serveurs utilisant le protocole XMPP (extensible Messaging and Presence Protocol), tel que Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Notez qu’une licence distincte peut être nécessaire pour la connectivité de messagerie instantanée publique avec Windows Live, AOL et Yahoo !

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>À compter du 1er septembre, 2012, le contrat de licence de l’utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») ne sera plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo ! Messenger jusqu’à la date d’arrêt du service. Date de fin de vie du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, voir <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité de messagerie instantanée publique dans Lync Server 2013</A>.</P>
    > <LI>
    > <P>La fonction USL (PIC) est une licence d’abonnement par mois qui est requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonné à la prise en charge de Yahoo !, le contrat sous-jacent pour lequel le son est arrêté.</P>
    > <LI>
    > <P>Plus que jamais, Lync est un outil puissant de connexion entre organisations et de personnes dans le monde entier. La Fédération avec Windows Live Messenger ne nécessite aucune licence d’utilisateur/appareil supplémentaire au-delà de la CAL standard Lync. Skype Federation sera ajouté à cette liste et permettra aux utilisateurs de Lync de joindre des centaines de millions de personnes à la messagerie instantanée et à la voix.</P></LI></UL>

    
    </div>

Pour activer tout ou partie de ces scénarios, vous devez déployer un serveur Edge pour sécuriser les communications entre le déploiement de votre serveur Lync et les utilisateurs externes. Les utilisateurs distants de votre organisation et les utilisateurs d’organisations fédérées seront en mesure de détecter leur présence mutuelle et de communiquer via la messagerie instantanée. Pour plus d’informations sur l’activation de la communication avec des utilisateurs externes, voir [planification de l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.

</div>

<div>

## <a name="archiving-im-content"></a>Archivage de contenu de messagerie instantanée

Lync Server fournit des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les règles de conformité. Vous pouvez utiliser la fonctionnalité d’archivage pour archiver le contenu des messages instantanés soit pour tous les utilisateurs de votre organisation, soit uniquement pour ceux que vous indiquez. Pour plus d’informations, reportez-vous à la rubrique [planification de l’archivage dans Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.

Si Microsoft Exchange Server 2013 est également déployé, vous pouvez intégrer l’archivage de données Exchange avec l’archivage des données de Lync Server et utiliser un seul outil pour effectuer une recherche dans les deux types de données archivées. Pour plus d’informations, reportez-vous [à configuration de Microsoft Lync server 2013 pour l’utilisation de l’archivage Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

