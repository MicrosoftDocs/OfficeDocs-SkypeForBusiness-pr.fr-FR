---
title: 'Lync Server 2013 : afficher les informations relatives au téléphone de la zone commune'
description: 'Lync Server 2013 : afficher les informations relatives au téléphone de la zone commune.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4debe9a76118ac0bf1ca711426ce5487009a053
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572470"
---
# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="090aa-103">Afficher les informations de téléphone de partie commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="090aa-103">View common area phone information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="090aa-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="090aa-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="090aa-105">Vous pouvez afficher des informations sur les téléphones de partie commune configurés pour être utilisés dans votre organisation à l’aide de la cmdlet **Get-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="090aa-105">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="090aa-106">Utilisée sans aucun paramètre, cette applet de commande renvoie des informations sur tous vos téléphones de partie commune.</span><span class="sxs-lookup"><span data-stu-id="090aa-106">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="090aa-107">Les paramètres facultatifs vous permettent de filtrer les informations de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="090aa-107">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="090aa-108">Par exemple, vous pouvez renvoyer tous les téléphones de partie commune qui ont des objets contact dans une unité d’organisation (UO) spécifique ou tous les objets contacts se trouvant dans un immeuble spécifié.</span><span class="sxs-lookup"><span data-stu-id="090aa-108">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="090aa-109">Pour plus d’informations sur les paramètres **Get-CsCommonAreaPhone** , voir [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="090aa-109">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="090aa-110">Exécutez **Get-CsCommonAreaPhone** à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="090aa-110">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="090aa-111">Affichage des informations sur tous vos téléphones de partie commune</span><span class="sxs-lookup"><span data-stu-id="090aa-111">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="090aa-112">Pour afficher des informations sur tous vos téléphones de partie commune, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="090aa-112">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="090aa-113">Vous obtiendrez des informations semblables à celles-ci :</span><span class="sxs-lookup"><span data-stu-id="090aa-113">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="090aa-114">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="090aa-114">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

