---
title: 'Lync Server 2013 : configurer les numéros d’accès aux conférences rendez-vous'
description: 'Lync Server 2013 : configurer les numéros d’accès aux conférences rendez-vous.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0edb3492c243b36b69c4b48df8c22adc4ece7999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565079"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="e904f-103">Configurer les numéros d’accès aux conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e904f-103">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e904f-104">_**Dernière modification de la rubrique :** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="e904f-104">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="e904f-p101">Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros apparaissent dans les invitations à une réunion et sur la page Web des paramètres de configuration des conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="e904f-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="e904f-107">Avant de créer des numéros d’accès aux conférences rendez-vous, vous devez planifier vos régions de conférences rendez-vous puis configurer les plans de numérotation correspondants.</span><span class="sxs-lookup"><span data-stu-id="e904f-107">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="e904f-108">Pour plus d’informations sur les régions, voir Configuration requise pour les conférences rendez [-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="e904f-108">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="e904f-109">Pour plus d’informations sur la configuration des plans de numérotation pour les conférences rendez-vous, voir [configurer des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="e904f-109">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e904f-110">Vous ne pouvez pas utiliser un nouveau numéro d’accès entrant tant que la réplication des services de domaine Active Directory (AD &nbsp; DS) de ce numéro d’accès n’est pas terminée.</span><span class="sxs-lookup"><span data-stu-id="e904f-110">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="e904f-111">La réplication peut durer plusieurs heures.</span><span class="sxs-lookup"><span data-stu-id="e904f-111">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e904f-112">Une fois que vous avez créé les numéros d’accès aux conférences rendez-vous, vous pouvez modifier le nom complet des objets contact Active Directory pour permettre aux utilisateurs d’identifier plus facilement le numéro d’accès approprié.</span><span class="sxs-lookup"><span data-stu-id="e904f-112">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="e904f-113">Utilisez la cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> pour modifier le nom complet.</span><span class="sxs-lookup"><span data-stu-id="e904f-113">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="e904f-114">Vous ne devez pas modifier manuellement les objets Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e904f-114">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="e904f-115">Pour plus d’informations sur la modification d’un numéro d’accès, reportez-vous à la documentation Lync Server Management Shell pour la cmdlet <STRONG>Set-applet csdialinconferencingaccessnumber</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="e904f-115">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e904f-116">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e904f-116">In This Section</span></span>

[<span data-ttu-id="e904f-117">Création ou modification d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e904f-117">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e904f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e904f-118">See Also</span></span>


[<span data-ttu-id="e904f-119">Exigences en matière de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e904f-119">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="e904f-120">Configurer des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e904f-120">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

