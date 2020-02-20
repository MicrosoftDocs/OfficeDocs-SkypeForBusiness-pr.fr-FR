---
title: 'Lync Server 2013 : définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence'
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
ms.openlocfilehash: 703ca1ab069101a7266c779aa21ff3f587b93f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Définition de la configuration requise pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-10-07_

La principale tâche de planification pour la messagerie instantanée et la présence est de vous assurer que vous disposez de suffisamment de serveurs frontaux pour vos utilisateurs.

<div>

## <a name="enabling-communication-with-external-users"></a>Activation des communications avec les utilisateurs externes

Vous pouvez grandement augmenter les avantages de votre investissement dans Lync Server en permettant à vos utilisateurs de communiquer avec des utilisateurs externes. Les utilisateurs externes peuvent inclure les catégories suivantes :

  - **Utilisateurs distants**   les utilisateurs de votre organisation, lorsqu’ils travaillent à l’extérieur de vos pare-feu et qu’ils utilisent leur ordinateur portable ou d’autres appareils Lync Server.

  - **Utilisateurs fédérés**   utilisateurs de sociétés avec qui exécutent également Lync Server. Pour autoriser vos utilisateurs à contacter facilement ces utilisateurs, créez des relations fédérées avec ces entreprises.

  - **Utilisateurs publics utilisateurs**   de services de messagerie instantanée publics, tels que les services de messagerie instantanée fournis par le réseau Windows Live\!des services Internet, Yahoo et AOL, ainsi que les utilisateurs de fournisseurs et de serveurs qui utilisent le protocole XMPP (extensible Messaging and Presence Protocol), comme Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Veuillez noter qu’une licence distincte peut être requise pour la connectivité de la messagerie instantanée publique avec Windows Live, AOL et Yahoo!

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement. Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !. Messenger jusqu’à la date d’arrêt du service. Date de fin du 2014 juin pour AOL et Yahoo ! a été annoncé. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</P>
    > <LI>
    > <P>La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo ! Messenger. La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</P>
    > <LI>
    > <P>Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier. La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard. La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</P></LI></UL>

    
    </div>

Pour activer un ou l’ensemble de ces scénarios, vous devez déployer un serveur Edge pour permettre la sécurisation des communications entre votre déploiement Lync Server et les utilisateurs externes. Les utilisateurs distants de votre organisation et les utilisateurs d’organisations fédérées seront en mesure de détecter leur présence mutuelle et de communiquer via la messagerie instantanée. Pour plus d’informations sur l’activation de la communication avec des utilisateurs externes, voir [Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) dans la documentation de planification.

</div>

<div>

## <a name="archiving-im-content"></a>Archivage du contenu de la messagerie instantanée

Lync Server offre des fonctionnalités que vous pouvez utiliser si votre organisation doit respecter les réglementations en matière de conformité. Vous pouvez utiliser l’archivage pour archiver le contenu des messages INSTANTANÉs pour tous les utilisateurs de votre organisation ou uniquement pour certains utilisateurs que vous spécifiez. Pour plus d’informations, reportez-vous à la rubrique [Planning for Archiving in Lync Server 2013](lync-server-2013-planning-for-archiving.md) dans la documentation de planification.

Si vous avez également déployé Microsoft Exchange Server 2013, vous pouvez intégrer l’archivage des données Exchange avec l’archivage des données Lync Server et utiliser un seul outil pour effectuer des recherches dans les deux types de données archivées. Pour plus d’informations, reportez-vous à la rubrique [configuration de Microsoft Lync server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

