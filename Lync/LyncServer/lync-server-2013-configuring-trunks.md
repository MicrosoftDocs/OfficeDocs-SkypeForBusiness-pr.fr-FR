---
title: 'Lync Server 2013 : Configuration des jonctions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d40a290f75ae48b73a4695e04ea2934b0c4d695
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Configuration des jonctions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Dans le cadre d’un déploiement voix entreprise, vous pouvez configurer un Trunk entre un serveur de médiation et un ou plusieurs des homologues suivants pour fournir une connectivité PSTN (réseau téléphonique commuté) pour les clients et périphériques vocaux d’entreprise au sein de votre organisation:

  - Connexion de jonction SIP vers un fournisseur de services de téléphonie Internet

  - Passerelle RTC

  - Autocommutateur privé (PBX)

Pour plus d’informations, reportez-vous à [planification de la connectivité PSTN dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) dans la documentation de planification.

<div>


> [!IMPORTANT]  
> Avant de commencer la configuration de Trunk, vérifiez que la topologie a été créée et que le serveur de médiation et son homologue ont été configurés et associés entre eux. Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">définir une passerelle dans le générateur de topologie de Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>


> [!NOTE]  
> Dans le cadre de la configuration de Trunk, vous pouvez activer la fonctionnalité de contournement de média Lync Server 2013, qui permet aux éléments multimédias d’ignorer le serveur de médiation. Les Trunks peuvent être configurés avec ou sans Bypass multimédia activé, mais nous vous recommandons vivement de l’activer. Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-planning-for-media-bypass.md">planification de la dérivation multimédia dans Lync Server 2013</A> dans la documentation de planification.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Prise en charge de plusieurs Trunks dans Lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Routage inter-Trunk dans Lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Afficher les informations de configuration de Trunk dans Lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Configurer un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Créer une collection de paramètres de configuration de Trunk dans Lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Supprimer une collection existante de paramètres de configuration de Trunk SIP dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Modifier les paramètres de configuration de Trunk SIP dans Lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Tester les paramètres de configuration du Trunk SIP dans Lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Afficher des informations sur les lignes SIP individuelles dans Lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Définir une passerelle dans le générateur de topologies de Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Planification de la connectivité PSTN dans Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

