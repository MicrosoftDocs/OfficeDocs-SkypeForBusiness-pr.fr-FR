---
title: 'Lync Server 2013 : Octroi d’autorisations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Octroi d’autorisations dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-15_

Dans le cas de l’installation, vous pouvez accorder des autorisations au groupe universel RTCUniversalServerAdmins pour une unité d’organisation Active Directory spécifique (UO), ce qui permet aux membres du groupe RTCUniversalServerAdmins dans cette UO d’installer Lync Server 2013 dans le domaine spécifié. Lorsque vous accordez des autorisations sur une unité d’organisation, les autorisations suivantes sont octroyées:

  - Suit

  - Écrits

  - ReadSPN

  - WriteSPN

Dans le cas d’une administration, vous pouvez ajouter des autorisations à des UO spécifiques de sorte que les membres des groupes universels RTC créés par la préparation de la forêt puissent accéder aux UO sans avoir besoin d’être membres du groupe administrateurs de domaine. Les autorisations ajoutées à l’unité d’organisation spécifiée sont les mêmes que celles apportées par l’applet de passe **Enable-CsAdDomain** aux ordinateurs et aux conteneurs d’UO des utilisateurs.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Octroi d’autorisations de configuration dans Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Octroi d’autorisations d’unité organisationnelle dans Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

