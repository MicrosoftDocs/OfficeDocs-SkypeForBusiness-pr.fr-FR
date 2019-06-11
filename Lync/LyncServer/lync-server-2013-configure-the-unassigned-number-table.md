---
title: 'Lync Server 2013 : Configuration de la table des numéros non attribués'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59b44b31eececd002434b74085be85eaec9cbec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>Configuration de la table des numéros non attribués dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-30_

Dans Lync Server 2013, vous pouvez spécifier ce qu’il advient des appels entrants vers des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Les appelants peuvent entendre un message, peut être acheminé vers une autre destination, ou les deux.

La manière dont vous configurez la table des numéros non attribués dépend de l’utilisation envisagée. Vous pouvez configurer la table avec tous les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéro. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle n’est appelée que lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez modifier la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.

<div>


> [!IMPORTANT]  
> Avant de configurer la table des numéros non attribués, votre système doit déjà disposer d’annonces définies ou un standard automatique de messagerie unifiée (UM) est configuré.



</div>

<div>


> [!TIP]  
> Lorsque quelqu’un appelle un numéro non attribué, Lync Server effectue une recherche dans la table des numéros non attribués, de haut en bas, et utilise la première plage correspondante. Par conséquent, une action que vous voulez voir effectuée en dernier ressort doit être spécifiée pour la dernière plage de la table.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

[Créer ou modifier une plage de nombres non affectées dans Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Créer une annonce dans Lync Server 2013](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

