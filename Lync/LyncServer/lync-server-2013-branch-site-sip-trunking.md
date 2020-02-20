---
title: 'Lync Server 2013 : jonction SIP de site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch site SIP trunking
ms:assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412974(v=OCS.15)
ms:contentKeyID: 48185350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0e24a0260e6be0bea8d23158f07ffcffcb53cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-sip-trunking-in-lync-server-2013"></a>Jonction SIP de site de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Dans certains cas, vous devrez peut-être implémenter une jonction SIP distribuée sur des sites de succursale sélectionnés. Pour déterminer si une jonction SIP est nécessaire pour un site de succursale, consultez les informations de la [procédure implémentation de la jonction SIP dans Lync Server 2013 ?](lync-server-2013-how-do-i-implement-sip-trunking.md).

Pour plus d’informations sur les options de topologie prises en charge pour le déploiement de jonctions SIP dans les sites de succursale, consultez la rubrique [solutions de résistance de site de succursale dans Lync Server 2013](lync-server-2013-branch-site-resiliency-solutions.md).

<div>

## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Conditions requises pour le déploiement d’une jonction SIP sur un site de succursale : exemple d’analyse

Lorsque vous décidez de déployer une jonction SIP de site de succursale, vous devez effectuer une analyse des coûts propre au site. Par exemple, une entreprise ayant un site central à Redmond, Washington et un site de succursale à New York doit effectuer une analyse pour déterminer s’il faut implémenter une jonction SIP à partir du site de New York vers un fournisseur de services local.

Pour savoir si une jonction SIP distribuée à New York est rentable, identifiez les numéros SDA (Sélection Directe à l’Arrivée) qui doivent utiliser la jonction SIP, puis analysez le nombre d’appels à destination de zones en dehors de Redmond (425) que le site de New York passe. Vous pouvez avoir terminé le site de succursale sur le site central. Par exemple, le site central de Redmond peut héberger des numéros DID pour le site de succursale de New York. Si le coût de mise en œuvre d’une jonction SIP distribuée est inférieur au coût de ces appels, envisagez d’implémenter une jonction SIP sur le site de succursale de New York.

</div>

<div>

## <a name="other-branch-site-sip-trunk-requirements"></a>Autres conditions requises pour le déploiement d’une jonction SIP sur un site de succursale

Pour déterminer si vous devez déployer une jonction SIP ou une passerelle, comparez le coût des appels PSTN (Public Switched Telephone Network, réseau téléphonique commuté) longue distance de ces deux options. Si vous déployez une jonction SIP de site de succursale, vous devez également déterminer les besoins en matière de résistance et de bande passante. Si la liaison entre votre site de succursale et le site central est résiliente et dispose d’une bande passante suffisante, vous pouvez déployer une jonction SIP ou une passerelle. Vous n’avez pas besoin de déployer un Survivable Branch appliance sur le site de succursale. Si la liaison entre votre site de succursale et le site central n’est pas résiliente, déployez un Survivable Branch Appliance ou déployez un serveur Survivable Branch Server avec une jonction passerelle ou SIP sur le site de succursale.

</div>

</div>

<span> </span>

</div>

</div>

</div>

