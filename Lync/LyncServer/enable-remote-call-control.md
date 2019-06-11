---
title: Activer le contrôle d’appel distant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 310a140d3497a77ddcaeb8ba32403aa8f28b68e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>Activer le contrôle d’appel distant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-02_

Le contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX (Private Branch Exchange) à l’aide de Lync Server 2013. Si vous avez déployé le contrôle d’appel distant dans votre environnement hérité et souhaitez le migrer vers Lync Server 2013, vous devez effectuer les tâches suivantes:

1.  Installez une passerelle SIP/CSTA et configurez-la pour communiquer avec votre système PBX. Vous devez effectuer cette étape lors du déploiement de votre pool de pilotes Lync Server 2013.

2.  Après avoir fusionné votre topologie et effectué la migration de vos stratégies et paramètres, configurez Lync Server 2013 pour acheminer les demandes CSTA vers la passerelle SIP/CSTA. Cette étape est une étape manuelle qui suit la migration automatique. Pour configurer le routage des requêtes CSTA, procédez comme suit:
    
      - Supprimer les entrées d’hébergement d’ancienne génération (connues sous le nom d' *entrées de serveurs de confiance* dans Lync Server 2013). Si vous migrez des utilisateurs à partir de votre déploiement hérité, assurez-vous que vous avez supprimé toutes les entrées d’hôtes approuvées que vous avez créées pour la passerelle SIP/CSTA avant de configurer de nouvelles entrées de l’application fiable sur le pool de pilotes de Lync Server 2013. Pour plus d’informations sur la façon de supprimer des entrées d’hébergement héritées, voir [supprimer une entrée d’hôte autorisé](remove-an-authorized-host-entry.md).
    
      - Configurer un itinéraire statique pour le contrôle d’appel distant. Vous pouvez configurer un itinéraire statique pour les pools individuels que vous voulez prendre en charge le contrôle d’appel distant, ou vous pouvez configurer un itinéraire statique global de telle sorte que chaque liste qui n’est pas configuré avec un itinéraire statique au niveau du pool utilise l’itinéraire statique global. Pour plus d’informations sur la configuration de l’itinéraire statique, voir [configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) dans la documentation de déploiement.
    
      - Configurez une entrée d’application fiable pour le contrôle d’appel distant de chaque pool pour lequel vous souhaitez prendre en charge le contrôle d’appel distant. Pour plus d’informations sur la configuration d’une entrée d’application fiable, voir [configurer une entrée d’application fiable pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) dans la documentation de déploiement.

3.  Si vous avez déployé une passerelle SIP/CSTA qui utilise le protocole TCP (Transmission Control Protocol) pour vous connecter à Lync Server 2013, définissez l’adresse IP de la passerelle dans le générateur de topologie. Pour plus d’informations sur la définition de l’adresse IP, voir [définir une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) dans la documentation de déploiement.

4.  Configurez les utilisateurs de Lync 2013 pour le contrôle d’appel distant en activant le contrôle d’appel distant et en assignant un URI (Uniform Resource Identifier) et un URI de ligne. Lorsque vous migrez des utilisateurs de votre déploiement hérité vers Lync Server 2013, les paramètres de contrôle des appels distants sont migrés avec les paramètres d’autres utilisateurs.

5.  Si vous personnalisez les règles de normalisation des numéros de téléphone de votre carnet d’adresses dans votre déploiement hérité, vous devez effectuer certaines tâches manuelles après la migration automatique de stratégies et de paramètres pour migrer les règles de normalisation personnalisées. Si vous n’avez pas personnalisé de règles de normalisation, le carnet d’adresses est migré avec le reste de votre topologie. Pour plus d’informations sur la migration manuelle de règles de normalisation personnalisées, voir migrer le [carnet d’adresses](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

