---
title: 'Lync Server 2013 : suppression d’un objet contact de téléphone de partie commune'
description: 'Lync Server 2013 : suppression d’un objet contact de téléphone de partie commune.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e918f7a46269f70577f28b2c3e55297959430721
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566600"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="f89e6-103">Supprimer un objet contact de téléphone de partie commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f89e6-103">Delete a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f89e6-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f89e6-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f89e6-105">Vous pouvez supprimer l’objet contact associé à un téléphone de partie commune.</span><span class="sxs-lookup"><span data-stu-id="f89e6-105">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="f89e6-106">Par exemple, si vous supprimez le téléphone d’une salle d’employés, il n’est pas nécessaire qu’un objet contact soit associé à ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="f89e6-106">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="f89e6-107">L’applet de commande **Remove-CsCommonAreaPhone** vous permet de supprimer des comptes de téléphonie de partie commune.</span><span class="sxs-lookup"><span data-stu-id="f89e6-107">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="f89e6-108">Lorsque vous exécutez cette applet de commande, le téléphone est supprimé de la liste des téléphones de partie commune renvoyée par **Get-CsCommonAreaPhone**.</span><span class="sxs-lookup"><span data-stu-id="f89e6-108">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="f89e6-109">En outre, l’objet contact associé à ce téléphone est supprimé des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f89e6-109">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="f89e6-110">Utilisez **Remove-CsCommonAreaPhone** pour supprimer un téléphone de partie commune ou tous les téléphones de partie commune qui ont un élément commun, comme un nom d’affichage, un pays et un indicatif régional.</span><span class="sxs-lookup"><span data-stu-id="f89e6-110">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="f89e6-111">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f89e6-111">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f89e6-112">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f89e6-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="f89e6-113">Suppression d’un téléphone de partie commune spécifié</span><span class="sxs-lookup"><span data-stu-id="f89e6-113">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="f89e6-114">La commande suivante permet de supprimer le téléphone de partie commune avec l’adresse SIP sip :mainlobby@litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="f89e6-114">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="f89e6-115">Suppression des téléphones de partie commune en fonction de leur nom d’affichage</span><span class="sxs-lookup"><span data-stu-id="f89e6-115">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="f89e6-116">Cette commande permet de supprimer tous les téléphones de partie commune pour lesquels le nom d’affichage inclut la valeur de chaîne « Building 14 » :</span><span class="sxs-lookup"><span data-stu-id="f89e6-116">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="f89e6-117">Suppression des téléphones de partie commune en fonction de leurs indicatifs de pays et de région</span><span class="sxs-lookup"><span data-stu-id="f89e6-117">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="f89e6-118">Cette commande permet de supprimer tous les téléphones de partie commune pour les États-Unis (code pays 1) et l’indicatif régional 425 :</span><span class="sxs-lookup"><span data-stu-id="f89e6-118">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="f89e6-119">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="f89e6-119">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f89e6-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f89e6-120">See Also</span></span>


[<span data-ttu-id="f89e6-121">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="f89e6-121">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

