---
title: 'Lync Server 2013 : configuration de la table des numéros non attribués'
description: 'Lync Server 2013 : configurez la table des numéros non attribués.'
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
ms.openlocfilehash: 8ed8ba6c709311dab791b711d6ba69aaff72a630
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544890"
---
# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="cda67-103">Configuration de la table des numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda67-103">Configure the unassigned number table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cda67-104">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="cda67-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="cda67-105">Dans Lync Server 2013, vous pouvez spécifier le déroulement des appels entrants vers des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone.</span><span class="sxs-lookup"><span data-stu-id="cda67-105">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="cda67-106">Les appelants peuvent écouter un message ou être acheminés vers une autre destination, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="cda67-106">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="cda67-107">La manière dont vous configurez la table des numéros non attribués dépend de la façon dont vous comptez l’utiliser.</span><span class="sxs-lookup"><span data-stu-id="cda67-107">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="cda67-108">Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéros.</span><span class="sxs-lookup"><span data-stu-id="cda67-108">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="cda67-109">La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle appelée uniquement lorsqu’un appelant compose un numéro qui n’est pas attribué.</span><span class="sxs-lookup"><span data-stu-id="cda67-109">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="cda67-110">Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table.</span><span class="sxs-lookup"><span data-stu-id="cda67-110">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="cda67-111">Si vous incluez des extensions non attribuées dans le tableau, vous pouvez modifier l’action qui se produit pour des numéros spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cda67-111">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="cda67-112">Par exemple, si vous modifiez l’extension de votre bureau de service client, vous pouvez inclure l’ancien numéro de service client dans le tableau, puis l’affecter à une annonce qui fournit le nouveau numéro.</span><span class="sxs-lookup"><span data-stu-id="cda67-112">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cda67-113">Avant de configurer la table des numéros non attribués, votre système doit déjà avoir des annonces définies ou un standard automatique de messagerie unifiée Exchange a été configuré.</span><span class="sxs-lookup"><span data-stu-id="cda67-113">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="cda67-114">Lorsqu’une personne appelle un numéro non attribué, Lync Server recherche la table des numéros non attribués de haut en bas et utilise la première plage de correspondance.</span><span class="sxs-lookup"><span data-stu-id="cda67-114">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="cda67-115">Par conséquent, une action que vous souhaitez effectuer en dernier recours doit être spécifiée pour la dernière plage du tableau.</span><span class="sxs-lookup"><span data-stu-id="cda67-115">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cda67-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cda67-116">In This Section</span></span>

<span data-ttu-id="cda67-117">[Création ou modification d’une plage de numéros non attribués dans Lync server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [créer une annonce dans Lync Server 2013](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="cda67-117">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

