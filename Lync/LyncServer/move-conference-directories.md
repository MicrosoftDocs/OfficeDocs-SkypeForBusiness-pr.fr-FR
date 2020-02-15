---
title: Déplacer les annuaires des conférences
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4897df817c4392779169c535199579ac04d9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="f6fd2-102">Déplacer les annuaires des conférences</span><span class="sxs-lookup"><span data-stu-id="f6fd2-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6fd2-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f6fd2-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f6fd2-104">Avant de désaffecter un pool, vous devez effectuer la procédure suivante pour chaque annuaire des conférences de votre pool Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f6fd2-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="f6fd2-105">Pour déplacer un annuaire des conférences vers Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6fd2-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="f6fd2-106">Ouvrez Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f6fd2-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f6fd2-107">Pour obtenir l’identité des annuaires de conférence dans votre organisation, exécutez les commandes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f6fd2-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="f6fd2-p101">Étant donné que l’applet de commande renvoie tous les annuaires des conférences dans votre organisation, vous pouvez limiter les résultats au seul pool que vous voulez désaffecter. Par exemple, si vous souhaitez désaffecter un pool avec le nom de domaine complet (FQDN) pool01.contoso.net :</span><span class="sxs-lookup"><span data-stu-id="f6fd2-p101">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="f6fd2-110">Cette applet de commande renvoie tous les annuaires des conférences où l’ID de service contient le FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="f6fd2-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="f6fd2-111">Pour déplacer les annuaires des conférences, exécutez ce qui suit pour chaque annuaire des conférences dans le pool :</span><span class="sxs-lookup"><span data-stu-id="f6fd2-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="f6fd2-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f6fd2-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="f6fd2-113">Il se peut que vous rencontriez une erreur, comme indiqué ci-dessous, qui est causée par Lync Server Management Shell nécessitant un jeu d’autorisations mis à jour à partir d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6fd2-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="f6fd2-114">Pour résoudre l’erreur, fermez la fenêtre active et ouvrez un nouveau Lync Server Management Shell et exécutez à nouveau la commande.</span><span class="sxs-lookup"><span data-stu-id="f6fd2-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="f6fd2-115">![Sortie d’erreur Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Sortie d’erreur Move-CsConferenceDirectory")</span><span class="sxs-lookup"><span data-stu-id="f6fd2-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

