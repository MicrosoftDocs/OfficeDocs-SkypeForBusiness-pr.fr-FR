---
title: 'Lync Server 2013: trunking SIP site de filiale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 955e920138021941db0e75832d56d06499738edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Branch site SIP trunking in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Dans certains cas, il est possible que vous deviez implémenter une agrégation SIP distribuée sur des sites de succursales sélectionnés. Pour déterminer si un Trunk SIP est requis pour un site de succursale, voir les informations de la mise en œuvre de l' [agrégation SIP dans Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Pour plus d’informations sur les options de topologie prises en charge pour le déploiement de Trunks SIP dans les sites de succursales, voir [solutions de résilience de sites de succursales dans Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse

Lorsque vous décidez de déployer un Trunk SIP de site de succursale, vous devez effectuer une analyse de coûts spécifique au site. Par exemple, une entreprise disposant d’un site central dans Redmond, Washington et sur une succursale à New York doit effectuer une analyse pour déterminer s’il est nécessaire de mettre en œuvre un Trunk SIP à partir du site de New York vers un fournisseur de services local.

Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe. Vous pouvez avoir terminé le site de succursale sur le site central. Par exemple, le site central de Redmond peut héberger des numéros ayant été importés pour le site de succursale de New York. Si le coût de l’implémentation d’un Trunk SIP distribué est inférieur au coût de ces appels, envisagez d’implémenter une ligne SIP sur le site de la succursale de New York.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale

Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options. Si vous déployez une ligne SIP site de succursale, vous devez également déterminer votre tolérance de panne et vos besoins en bande passante. Si le lien entre votre site de succursale et votre site central est résilient et dispose d’une bande passante suffisante, vous pouvez déployer une passerelle SIP. Vous n’avez pas besoin de déployer une unité de branchement survivant sur le site de la succursale. Si le lien entre votre site de succursale et votre site central n’est pas résilient, déployez une application de succursale survivant ou déployez un serveur de succursales survivant avec une passerelle ou une ligne SIP sur le site de la succursale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

