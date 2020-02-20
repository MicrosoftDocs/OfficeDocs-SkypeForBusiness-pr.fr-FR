---
title: 'Lync Server 2013 : configuration de la table d’orbites de parcage d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cb3556ab0111d7bc61de6bc0914b5a3514a7cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Configuration de la table d’orbites de parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-10_

Le parcage d’appel utilise des orbites pour les appels de parking. Avant que les utilisateurs puissent parkiser et récupérer des appels, vous devez configurer la table des orbites de parcage d’appel. Vous devez spécifier les plages de numéros de poste (orbites) que votre organisation réservera pour les appels de parking et définir le routage de ces plages en spécifiant le pool de parcage d’appel qui gère chaque plage. Lorsque vous définissez des plages d’orbites, l’objectif est de disposer de suffisamment d’orbites pour éviter d’avoir à réutiliser trop rapidement une orbite, mais sans que leur nombre soit trop élevé afin de pouvoir limiter le nombre de postes disponibles pour les utilisateurs ou d’autres services. Vous pouvez créer plusieurs plages d’orbites de parcage d’appel pour chaque pool Lync Server où l’application de parcage d’appel est déployée. Chaque plage d’orbites de parcage d’appel doit avoir un nom global unique et un ensemble unique d’extensions.

<div>


> [!IMPORTANT]  
> Une plage d’orbites comprend généralement au moins 100 orbites. Chaque plage peut être plus importante à condition qu’elle contienne moins de 10 000 orbites et que chaque pool comporte moins de 50 000 orbites. Si une plage est trop petite, les orbites sont réutilisées plus rapidement.



</div>

Utilisez des blocs de postes virtuels (postes attribués à aucun utilisateur ni téléphone) pour vos plages d’orbites.

<div>


> [!NOTE]  
> L’affectation de numéros DID (appels directs vers l’intérieur) sous forme de numéros d’orbites dans la table des orbites de parcage d’appel n’est pas prise en charge.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

[Création ou modification d’une plage d’orbites de parcage d’appel dans Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

