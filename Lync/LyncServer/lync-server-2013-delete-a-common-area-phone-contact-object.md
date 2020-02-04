---
title: 'Lync Server 2013 : supprimer un objet de contact de téléphone de zone commune'
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
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="7f0a0-102">Supprimer un objet de contact de téléphone pour les zones communes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f0a0-102">Delete a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f0a0-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7f0a0-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7f0a0-104">Vous souhaiterez peut-être supprimer l’objet contact associé à un téléphone de zone commune.</span><span class="sxs-lookup"><span data-stu-id="7f0a0-104">You might want to delete the contact object associated with a common area phone.</span></span> <span data-ttu-id="7f0a0-105">Par exemple, si vous supprimez le téléphone d’une salon d’employé, il est inutile d’avoir un objet de contact associé à ce téléphone.</span><span class="sxs-lookup"><span data-stu-id="7f0a0-105">For example, if you remove the phone from an employee lounge, there’s no need to have a contact object associated with that phone.</span></span> <span data-ttu-id="7f0a0-106">L’applet de passe **Remove-CsCommonAreaPhone** vous permet de supprimer les comptes de téléphone de zone commune.</span><span class="sxs-lookup"><span data-stu-id="7f0a0-106">The **Remove-CsCommonAreaPhone** cmdlet provides a way for you to delete common area phone accounts.</span></span> <span data-ttu-id="7f0a0-107">Lorsque vous exécutez cette cmdlet, le téléphone est supprimé de la liste des téléphones communs renvoyés par **Get-CsCommonAreaPhone**.</span><span class="sxs-lookup"><span data-stu-id="7f0a0-107">When you run this cmdlet, the phone is deleted from the list of common area phones returned by **Get-CsCommonAreaPhone**.</span></span> <span data-ttu-id="7f0a0-108">Par ailleurs, l’objet contact associé à ce téléphone est supprimé des services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="7f0a0-108">In addition, the contact object associated with that phone is deleted from Active Directory Domain Services.</span></span>

<span data-ttu-id="7f0a0-109">Utilisez **Remove-CsCommonAreaPhone** pour supprimer un téléphone standard ou tous les téléphones communs qui possèdent un élément commun, comme un nom d’affichage ou un indicatif de pays ou de région.</span><span class="sxs-lookup"><span data-stu-id="7f0a0-109">Use **Remove-CsCommonAreaPhone** to remove one common area phone or all common area phones that have a common element, such as a display name or country and area code.</span></span> <span data-ttu-id="7f0a0-110">Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f0a0-110">You can run this cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7f0a0-111">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="7f0a0-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a><span data-ttu-id="7f0a0-112">Suppression d’un téléphone commun spécifié</span><span class="sxs-lookup"><span data-stu-id="7f0a0-112">Removing a Specified Common Area Phone</span></span>

  - <span data-ttu-id="7f0a0-113">La commande suivante permet de supprimer le téléphone de zone commune avec l’adresse SIP sip :mainlobby@litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="7f0a0-113">The following command removes the common area phone with the SIP address sip:mainlobby@litwareinc.com:</span></span>
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a><span data-ttu-id="7f0a0-114">Suppression de téléphones communs en fonction de leur nom d’affichage</span><span class="sxs-lookup"><span data-stu-id="7f0a0-114">Removing Common Area Phones Based on Their Display Name</span></span>

  - <span data-ttu-id="7f0a0-115">Cette commande supprime tous les téléphones de surface courants dans lesquels le nom d’affichage inclut la valeur de chaîne « bâtiment 14 » :</span><span class="sxs-lookup"><span data-stu-id="7f0a0-115">This command removes all the common area phones where the display name includes the string value "Building 14":</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a><span data-ttu-id="7f0a0-116">Supprimer des téléphones communs en fonction de leur indicatif national et de leur région</span><span class="sxs-lookup"><span data-stu-id="7f0a0-116">Removing Common Area Phones Based on Their Country and Area Codes</span></span>

  - <span data-ttu-id="7f0a0-117">Cette commande supprime tous les téléphones de surface commune pour les États-Unis (code pays 1) et l’indicatif régional 425 :</span><span class="sxs-lookup"><span data-stu-id="7f0a0-117">This command removes all the common area phones for the United States (country code 1) and the area code 425:</span></span>
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

<span data-ttu-id="7f0a0-118">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="7f0a0-118">For details, see the Help topic for the [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f0a0-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f0a0-119">See Also</span></span>


[<span data-ttu-id="7f0a0-120">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="7f0a0-120">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

