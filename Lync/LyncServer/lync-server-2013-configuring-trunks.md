---
title: 'Lync Server 2013 : configuration des jonctions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c2fd4a79937477edbe01f5550a81e92a663d3d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517341"
---
# <a name="configuring-trunks-in-lync-server-2013"></a>Configuration des jonctions dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Dans le cadre du déploiement de voix entreprise, vous pouvez configurer une jonction entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et les appareils voix entreprise de votre organisation :

  - Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet

  - Passerelle PSTN

  - Autocommutateur privé (PBX)

Pour plus d’informations, reportez-vous à la rubrique [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) dans la documentation de planification.

<div>


> [!IMPORTANT]  
> Avant de commencer la configuration des jonctions, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés l’un à l’autre. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">définition d’une passerelle dans le générateur de topologie dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>


> [!NOTE]  
> Dans le cadre de la configuration de jonction, vous pouvez activer la fonctionnalité de contournement de média Lync Server 2013, qui permet aux médias de contourner le serveur de médiation. Vous pouvez configurer les jonctions sans activer le contournement de média mais nous vous conseillons vivement de l’activer. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-planning-for-media-bypass.md">Planning for Media Bypass in Lync Server 2013</A> dans la documentation de planification.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Prise en charge de plusieurs tronçons dans Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Routage entre les jonctions dans Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Afficher les informations de configuration de jonction dans Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Créer une collection de paramètres de configuration de jonction dans Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Supprimer une collection existante de paramètres de configuration de jonction SIP dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modifier les paramètres de configuration de jonction SIP dans Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Tester les paramètres de configuration de jonction SIP dans Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Afficher des informations sur les jonctions SIP individuelles dans Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Définition d’une passerelle dans le générateur de topologies dans Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Planification de la connectivité PSTN dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

