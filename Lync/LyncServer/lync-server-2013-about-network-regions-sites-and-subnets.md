---
title: 'Lync Server 2013 : À propos des régions réseau, des sites réseau et des sous-réseaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

Les fonctionnalités avancées de voix entreprise décrites dans cette section partagent certaines exigences de configuration pour les zones réseau, les sites réseau et les sous-réseaux. Par exemple, les trois fonctionnalités avancées nécessitent que chaque sous-réseau de votre topologie soit associé à un *site réseau*spécifique et chaque site réseau doit être associé à une *région réseau*.

<div>


> [!IMPORTANT]  
> Avant de commencer la configuration du réseau pour le contrôle d’admission des appels, E9-1-1 ou le contournement multimédia, assurez-vous d’avoir examiné les informations supplémentaires sur les paramètres réseau dans les <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">paramètres réseau pour les fonctionnalités avancées d’Enterprise voix dans Lync Server 2013</A> section de la documentation de planification. Pour plus d’informations sur la configuration du réseau essentiellement sur le contrôle d’admission des appels, voir <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">définir vos exigences de contrôle d’admission des appels dans Lync Server 2013</A> dans la documentation de planification.



</div>

Le contrôle d’admission des appels et E9-1-1 ont des exigences de configuration supplémentaires pour les sites réseau :

  - Le contrôle d’admission des appels nécessite de spécifier un *profil de stratégie de bande passante* pour chaque site soumis à des restrictions de bande passante de réseau étendu (WAN). Si vous envisagez de déployer le contrôle d’admission des appels, vous devez [créer des profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md) avant de configurer les sites de votre réseau.

  - E9-1-1 nécessite de spécifier une *stratégie d’emplacement* pour chaque site. Si vous envisagez de déployer E9-1-1, vous devez [créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md) avant de configurer les sites de votre réseau.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Créer ou modifier des régions, des sites et des sous-réseaux réseau

Les rubriques suivantes décrivent les étapes permettant de créer ou de modifier des zones et des sites réseau, et d’associer des sous-réseaux aux sites réseau. Ces rubriques ne sont pas spécifiques à toutes les fonctionnalités avancées de voix entreprise.

  - [Créer ou modifier une région réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

