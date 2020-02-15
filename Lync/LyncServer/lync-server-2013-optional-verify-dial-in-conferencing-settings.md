---
title: 'Lync Server 2013 : (facultatif) vérifier les paramètres de conférence rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86ec4e4852594e7e4748213de994b6b4f471d460
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="cfdba-102">Module Vérifier les paramètres de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfdba-102">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfdba-103">_**Dernière modification de la rubrique :** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="cfdba-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="cfdba-p101">Pour terminer la vérification de votre configuration de conférence rendez-vous, vous pouvez chercher des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès et des numéros d’accès que vous n’avez pas spécifiés dans une région de conférence rendez-vous.   Cette étape est facultative.</span><span class="sxs-lookup"><span data-stu-id="cfdba-p101">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region. This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="cfdba-106">Pour trouver des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès</span><span class="sxs-lookup"><span data-stu-id="cfdba-106">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="cfdba-107">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="cfdba-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="cfdba-108">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cfdba-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cfdba-109">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="cfdba-109">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="cfdba-110">Cette applet de commande retourne tous les plans de numérotation dont la région de conférence rendez-vous n’est pas utilisée par un numéro d’accès.</span><span class="sxs-lookup"><span data-stu-id="cfdba-110">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="cfdba-111">Pour trouver des numéros d’accès sans régions affectées</span><span class="sxs-lookup"><span data-stu-id="cfdba-111">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="cfdba-112">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="cfdba-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="cfdba-113">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cfdba-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cfdba-114">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="cfdba-114">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="cfdba-115">Cette applet de commande retourne tous les numéros d’accès de conférences rendez-vous qui ne sont pas associés à une région.</span><span class="sxs-lookup"><span data-stu-id="cfdba-115">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

