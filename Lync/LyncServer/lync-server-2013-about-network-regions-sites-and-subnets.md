---
title: 'Lync Server 2013 : à propos des régions réseau, des sites et des sous-réseaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fe7b93f00ce7af6354fa8a1bc94c104f3af14f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523211"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>À propos des régions réseau, des sites et des sous-réseaux dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Les fonctionnalités Voix Entreprise avancées qui sont décrites dans cette section partagent certaines exigences de configuration pour les régions réseau, sites réseau et sous-réseaux. Par exemple, les trois fonctionnalités avancées nécessitent que chaque sous-réseau de votre topologie soit associé à un *site réseau* spécifique, et que chaque site réseau soit associé à une *région réseau*.

<div>


> [!IMPORTANT]  
> Avant de commencer la configuration réseau pour le contrôle d’admission des appels, E9-1-1 ou la déviation du trafic multimédia, veillez à consulter des informations supplémentaires sur les paramètres réseau dans la rubrique <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">paramètres réseau pour les fonctionnalités avancées de voix entreprise dans Lync Server 2013</A> dans la documentation de planification. Pour plus d’informations sur la configuration réseau principalement sur le contrôle d’admission des appels, voir définition de la configuration <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">requise pour le contrôle d’admission des appels dans Lync Server 2013</A> dans la documentation de planification.



</div>

Le contrôle d’admission des appels et E9-1-1 ont des exigences de configuration supplémentaires pour les sites réseau :

  - Le contrôle d’admission des appels nécessite de spécifier un *profil de stratégie de bande passante* pour chaque site soumis à des restrictions de bande passante de réseau étendu (WAN). Si vous envisagez de déployer le contrôle d’admission des appels, vous devez [créer des profils de stratégie de bande passante dans Lync Server 2013 avant de](lync-server-2013-create-bandwidth-policy-profiles.md) configurer vos sites réseau.

  - E9-1-1 nécessite de spécifier une *stratégie d’emplacement* pour chaque site. Si vous envisagez de déployer E9-1-1, vous devez [créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md) avant de configurer vos sites réseau.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Créer ou modifier des régions réseau, sites réseau et sous-réseaux

Les rubriques suivantes décrivent la procédure permettant de créer ou de modifier des régions réseau et des sites réseau, mais aussi d’associer des sous-réseaux à des sites réseau. Ces rubriques ne sont pas spécifiques à une fonctionnalité Voix Entreprise avancée particulière.

  - [Création ou modification d’une région réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

