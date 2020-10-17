---
title: Activer le contrôle d’appel distant
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9aa81c938d69aedbc599194c1d820fa4c40e3337
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502891"
---
# <a name="enable-remote-call-control"></a>Activer le contrôle d’appel distant

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-02_

Le contrôle d’appel distant permet aux utilisateurs de contrôler leurs téléphones PBX (Private Branch Exchange) de bureau à l’aide de Lync Server 2013. Si vous avez déployé le contrôle d’appel distant dans votre environnement hérité et que vous souhaitez migrer Lync Server 2013, vous devez effectuer les tâches suivantes :

1.  Installez une passerelle SIP/CSTA et configurez-la de façon à communiquer avec votre PBX. Vous devez effectuer cette étape lorsque vous déployez votre pool pilote Lync Server 2013.

2.  Après avoir fusionné votre topologie et migré vos stratégies et paramètres, configurez Lync Server 2013 pour acheminer les demandes CSTA vers la passerelle SIP/CSTA. Il s’agit d’une étape manuelle qui suit la migration automatisée. Pour configurer le routage pour les demandes CSTA, procédez comme suit :
    
      - Supprimez les entrées d’hôte autorisé héritées (connues sous le nom d' *entrées de serveur de confiance* dans Lync Server 2013). Si vous migrez des utilisateurs à partir de votre déploiement hérité, veillez à supprimer toutes les entrées d’hôte autorisé que vous avez créées pour la passerelle SIP/CSTA avant de configurer de nouvelles entrées d’applications approuvées sur le pool pilote Lync Server 2013. Pour plus d’informations sur la suppression des entrées d’hôte autorisé héritées, consultez la rubrique [supprimer une entrée d’hôte autorisé](remove-an-authorized-host-entry.md).
    
      - Configurez un itinéraire statique pour le contrôle d’appel distant. Vous pouvez configurer un itinéraire statique pour les pools qui doivent prendre en charge le contrôle d’appel distant ou vous pouvez configurer un itinéraire statique global de sorte que chaque pool qui n’est pas configuré avec un itinéraire statique au niveau du pool utilise cet itinéraire statique global. Pour plus d’informations sur la configuration de l’itinéraire statique, voir [configurer un itinéraire statique pour le contrôle d’appel distant dans Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) dans la documentation de déploiement.
    
      - Configurez une entrée d’application approuvée pour le contrôle d’appel distant sur chaque pool où vous souhaitez prendre en charge le contrôle d’appel distant. Pour plus d’informations sur la configuration d’une entrée d’application approuvée, voir [Configure a Trusted application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) dans la documentation de déploiement.

3.  Si vous avez déployé une passerelle SIP/CSTA qui utilise le protocole TCP (Transmission Control Protocol) pour se connecter à Lync Server 2013, définissez l’adresse IP de la passerelle dans le générateur de topologie. Pour plus d’informations sur la définition de l’adresse IP, reportez-vous à [définir une adresse IP de passerelle SIP/CSTA dans Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) dans la documentation de déploiement.

4.  Configurez les utilisateurs de Lync 2013 pour le contrôle d’appel distant en activant le contrôle d’appel distant et en affectant un URI (Uniform Resource Identifier) de serveur de ligne et un URI de ligne. Lorsque vous migrez des utilisateurs de votre déploiement hérité vers Lync Server 2013, les paramètres de contrôle d’appel distant sont migrés avec les autres paramètres utilisateur.

5.  Si vous avez personnalisé vos règles de normalisation des numéros de téléphone du Carnet d’adresses dans votre déploiement hérité, vous devez effectuer certaines tâches manuelles une fois que la migration automatisée des stratégies et des paramètres est terminée, afin d’achever la migration des règles de normalisation personnalisées. Si vous n’avez pas personnalisé de règles de normalisation, le Carnet d’adresses est migré en même temps que le reste de votre topologie. Pour plus de détails sur la migration manuelle des règles de normalisation personnalisées,voir [Migrate Address Book](migrate-address-book_1.md).

</div>

<span> </span>

</div>

</div>

</div>

