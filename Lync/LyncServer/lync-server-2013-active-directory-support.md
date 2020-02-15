---
title: Prise en charge d’Active Directory dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory support
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425756(v=OCS.15)
ms:contentKeyID: 48183679
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ded5de5500778559efe632c5272db50b0eadbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-support-in-lync-server-2013"></a>Prise en charge d’Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-04_

Les topologies locales des services de domaine Active Directory prises en charge par Lync Server 2013 sont les suivantes :

  - Forêt unique avec domaine unique

  - Forêt unique avec un arbre unique et plusieurs domaines

  - Forêt unique avec plusieurs arbres et des espaces de noms disjoints

  - Plusieurs forêts dans une topologie de forêt centrale

  - Plusieurs forêts dans une topologie de forêt de ressources

<div>


> [!NOTE]  
> Lync Server 2013 ne prend pas en charge les domaines en une seule partie. Par exemple, une forêt avec un domaine racine nommé <STRONG>contoso. local</STRONG> est prise en charge, mais un domaine racine à une seule étiquette nommé <STRONG>local</STRONG> n’est pas pris en charge. Pour plus d’informations, consultez l’article 300684 de la base de connaissances Microsoft, « informations sur la configuration de Windows pour les domaines avec <A href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</A>des noms DNS en une seule partie », à l’adresse.



</div>

<div>


> [!NOTE]  
> Lync Server 2013 ne prend pas en charge le changement de nom des domaines. Si vous devez renommer un domaine où Lync Server est déployé, vous devez d’abord désinstaller Lync Server, renommer le domaine, puis réinstaller Lync Server.



</div>

Pour plus d’informations sur les topologies et les exigences prises en charge pour les déploiements sur site, voir [Active Directory Domain Services Requirements, support et topologies dans Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) dans la documentation de planification.

</div>

<span> </span>

</div>

</div>

</div>

