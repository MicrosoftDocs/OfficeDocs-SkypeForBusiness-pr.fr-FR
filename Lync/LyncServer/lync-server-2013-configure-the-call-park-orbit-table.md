---
title: 'Lync Server 2013 : Configuration de la table d’orbites de parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b306733c42e125a97c6bee4a4a42c4d96b7ebd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Configuration de la table d’orbites de parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-10_

Le parc d’appels utilise des orbites pour les appels en stationnement. Pour que les utilisateurs puissent parcer et récupérer des appels, vous devez configurer la table d’orbite du parc d’appels. Vous devez spécifier les plages de numéros d’extension (orbites) que votre organisation va réserver pour les appels de parking et définir le routage de ces plages en spécifiant le pool de parc d’appels qui gère chaque plage. Lorsque vous définissez des plages d’orbites, l’objectif est de disposer de suffisamment d’orbites pour ne pas avoir à réutiliser trop rapidement une orbite, mais sans que leur nombre soit trop élevé afin de pouvoir limiter le nombre de postes disponibles pour les utilisateurs ou d’autres services. Vous pouvez créer plusieurs plages d’orbite de parking pour chaque pool de serveurs Lync dans lequel l’application de parc d’appels est déployée. Chaque gamme de parking d’appel doit avoir un nom globalement unique et un ensemble unique d’extensions.

<div>


> [!IMPORTANT]  
> Une plage d’orbites comprend généralement au moins 100 orbites. Chaque plage peut être plus importante à condition qu’elle contienne moins de 10 000 orbites et que chaque pool comporte moins de 50 000 orbites. Si une plage est trop petite, les orbites sont réutilisées plus rapidement.



</div>

Utilisez des blocs de postes virtuels (postes attribués à aucun utilisateur ni téléphone) pour vos plages d’orbites.

<div>


> [!NOTE]  
> L’attribution de numéros de numérotation directe à l’intérieur de la table du parking d’appel n’est pas prise en charge.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

[Créer ou modifier une gamme de parc d’appels dans Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

