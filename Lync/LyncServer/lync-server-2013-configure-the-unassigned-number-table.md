---
title: 'Lync Server 2013 : configuration de la table des numéros non attribués'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef82a5976769543f83dc4656cf09eb64b94d7571
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Configuration de la table des numéros non attribués dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-30_

Dans Lync Server 2013, vous pouvez spécifier le déroulement des appels entrants vers des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Les appelants peuvent écouter un message ou être acheminés vers une autre destination, ou les deux.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous incluez des extensions non attribuées dans le tableau, vous pouvez modifier l’action qui se produit pour des numéros spécifiques. Par exemple, si vous modifiez l’extension de votre bureau de service client, vous pouvez inclure l’ancien numéro de service client dans le tableau, puis l’affecter à une annonce qui fournit le nouveau numéro.

<div>


> [!IMPORTANT]  
> Avant de configurer la table des numéros non attribués, votre système doit déjà avoir des annonces définies ou un standard automatique de messagerie unifiée Exchange a été configuré.



</div>

<div>


> [!TIP]  
> Lorsqu’une personne appelle un numéro non attribué, Lync Server recherche la table des numéros non attribués de haut en bas et utilise la première plage de correspondance. Par conséquent, une action que vous souhaitez effectuer en dernier recours doit être spécifiée pour la dernière plage du tableau.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

[Création ou modification d’une plage de numéros non attribués dans Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [créer une annonce dans Lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

