---
title: 'Lync Server 2013 : configurer les numéros de téléphone non affectés'
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
ms.openlocfilehash: 02dd4f71b3bc9d53fcbd65f4e143fec550c6a528
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="3e2ea-102">Configurer les numéros de téléphone non affectés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e2ea-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e2ea-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3e2ea-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3e2ea-104">Lync Server vous permet de configurer ce qu’il advient des appels entrants vers des numéros de téléphone valides pour votre organisation, mais qui ne sont pas attribués à un utilisateur ou à un téléphone.</span><span class="sxs-lookup"><span data-stu-id="3e2ea-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="3e2ea-105">Pour configurer la gestion de ces appels, vous avez configuré une table de numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="3e2ea-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="3e2ea-106">Vous pouvez utiliser le tableau pour acheminer les appels vers une application d’annonce ou vers un serveur de messagerie unifiée Exchange.</span><span class="sxs-lookup"><span data-stu-id="3e2ea-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="3e2ea-p102">La manière dont vous configurez la table des numéros non attribués dépend de l’utilisation envisagée. Vous pouvez configurer la table avec toutes les numéros de poste valides de votre organisation, avec uniquement les numéros de poste non attribués ou avec une combinaison des deux types de numéro. La table des numéros non attribués peut comporter des numéros attribués et des numéros non attribués, mais elle n’est appelée que lorsqu’un appelant compose un numéro qui n’est pas attribué. Si vous intégrez tous les numéros de poste valides dans la table des numéros non attribués, vous pouvez spécifier la réponse si une personne quitte l’organisation, sans avoir à reconfigurer la table. Si vous intégrez des numéros de poste non attribués à la table, vous pouvez personnaliser la réponse à certains numéros. Par exemple, si vous modifiez le numéro de poste de votre bureau de service client, vous pouvez inclure l’ancien numéro dans la table et l’attribuer à une annonce qui indique le nouveau numéro.</span><span class="sxs-lookup"><span data-stu-id="3e2ea-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3e2ea-113">Avant de configurer la table des numéros non attribués, vous devez disposer d’une ou plusieurs annonces définies ou d’un standard automatique de messagerie unifiée configuré.</span><span class="sxs-lookup"><span data-stu-id="3e2ea-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="3e2ea-114">Pour plus d’informations sur la création d’annonces, voir <A href="lync-server-2013-create-an-announcement.md">créer une annonce dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3e2ea-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="3e2ea-115">Pour savoir si vous avez configuré les paramètres de messagerie unifiée Exchange, exécutez l’applet <STRONG>de passe Get-CsExUmContact</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="3e2ea-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="3e2ea-116">Pour plus d’informations, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span><span class="sxs-lookup"><span data-stu-id="3e2ea-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e2ea-117">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3e2ea-117">In This Section</span></span>

  - [<span data-ttu-id="3e2ea-118">Créer ou modifier une plage de nombres non affectées dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e2ea-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="3e2ea-119">Supprimer une plage de numéros non attribués dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e2ea-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

