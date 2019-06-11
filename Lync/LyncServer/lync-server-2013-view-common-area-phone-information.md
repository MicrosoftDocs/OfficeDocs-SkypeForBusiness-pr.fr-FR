---
title: 'Lync Server 2013: afficher les informations sur le téléphone de la zone commune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 900beb4f96fd71e0e6a4ded40d776f1e7d356529
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="5e16b-102">Afficher des informations sur le téléphone de zone commune dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e16b-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e16b-103">_**Dernière modification de la rubrique:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5e16b-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5e16b-104">Vous pouvez afficher des informations sur les téléphones communs configurés pour une utilisation au sein de votre organisation à l’aide de l’applet de passe **Get-CsCommonAreaPhone** .</span><span class="sxs-lookup"><span data-stu-id="5e16b-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="5e16b-105">Utilisé sans paramètre, cette applet de méthode renvoie des informations sur tous les téléphones communs.</span><span class="sxs-lookup"><span data-stu-id="5e16b-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="5e16b-106">Les paramètres facultatifs permettent de filtrer les informations de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="5e16b-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="5e16b-107">Par exemple, vous pouvez retourner tous les téléphones de zone commune qui possèdent des objets de contact dans une unité d’organisation (UO) spécifiée, ou tous les objets de contact situés dans un immeuble spécifié.</span><span class="sxs-lookup"><span data-stu-id="5e16b-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="5e16b-108">Pour plus d’informations sur les paramètres **Get-CsCommonAreaPhone** , voir [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span><span class="sxs-lookup"><span data-stu-id="5e16b-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="5e16b-109">Exécutez **Get-CsCommonAreaPhone** à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e16b-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="5e16b-110">Affichage d’informations sur tous les téléphones de votre zone commune</span><span class="sxs-lookup"><span data-stu-id="5e16b-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="5e16b-111">Pour afficher des informations sur tous les téléphones communs, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="5e16b-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="5e16b-112">Vous obtiendrez des informations similaires à ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="5e16b-112">You’ll get information similar to this:</span></span>
    
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

<span data-ttu-id="5e16b-113">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) .</span><span class="sxs-lookup"><span data-stu-id="5e16b-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

