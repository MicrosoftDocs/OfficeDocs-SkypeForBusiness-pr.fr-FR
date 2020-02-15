---
title: 'Lync Server 2013 : configuration des numéros de téléphone non attribués'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d7fdbbca81ecd0dd42a9b5198f266b9a63d793e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>Configurer les numéros de téléphone non attribués dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Lync Server vous permet de configurer le déroulement des appels entrants vers des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone. Pour gérer ces appels, vous devez configurer une table de numéros non assignée. Vous pouvez utiliser le tableau pour acheminer les appels vers une application d’annonce ou vers un serveur de messagerie unifiée Exchange.

La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.

<div>


> [!IMPORTANT]  
> Avant de configurer la table des numéros non attribués, vous devez déjà avoir défini une ou plusieurs annonces ou configuré un standard automatique de messagerie unifiée Exchange. Pour plus d’informations sur la création d’annonces, voir <A href="lync-server-2013-create-an-announcement.md">créer une annonce dans Lync Server 2013</A>. Pour savoir si vous avez configuré les paramètres de messagerie unifiée Exchange, exécutez la cmdlet <STRONG>Get-CsExUmContact</STRONG> . Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Création ou modification d’une plage de numéros non attribués dans Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Supprimer une plage de numéros non attribués dans Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

