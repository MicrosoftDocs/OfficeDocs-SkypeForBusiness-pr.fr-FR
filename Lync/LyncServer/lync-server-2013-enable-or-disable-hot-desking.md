---
title: 'Lync Server 2013 : activation ou désactivation de l’assistance à chaud'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42da4f35c78e182ac988b1185bf797e3cb88ddd5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="07d5d-102">Activation ou désactivation de la connexion à chaud dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07d5d-102">Enable or disable hot desking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07d5d-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="07d5d-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="07d5d-104">Vous pouvez configurer des téléphones de partie commune en tant que *téléphones de bureau à chaud*.</span><span class="sxs-lookup"><span data-stu-id="07d5d-104">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="07d5d-105">Avec les téléphones de bureau à chaud, les utilisateurs peuvent se connecter à leur propre compte d’utilisateur et, une fois qu’ils sont connectés, utiliser les fonctionnalités de Lync Server et leurs propres paramètres de profil utilisateur.</span><span class="sxs-lookup"><span data-stu-id="07d5d-105">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="07d5d-106">La gestion de l’accès à chaud est gérée à l’aide de stratégies de client : pour activer ou désactiver la connexion à chaud, vous devez modifier les stratégies client utilisées par vos téléphones de partie commune.</span><span class="sxs-lookup"><span data-stu-id="07d5d-106">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="07d5d-107">Pour plus d’informations sur la façon de déterminer les stratégies de conférence qui ont été affectées à vos téléphones de partie commune, voir [View Common Area Phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="07d5d-107">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="07d5d-108">Vous utilisez le paramètre EnableHotdesking de la cmdlet **New-CSClientPolicy** ou l’applet de commande **Set-CSClientPolicy** pour activer ou désactiver la connexion à chaud sur un téléphone, comme suit.</span><span class="sxs-lookup"><span data-stu-id="07d5d-108">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="07d5d-109">Exécutez ces applets de commande à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07d5d-109">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="07d5d-110">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="07d5d-110">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="07d5d-111">Activation de l’assistance à chaud</span><span class="sxs-lookup"><span data-stu-id="07d5d-111">Enabling hot desking</span></span>

  - <span data-ttu-id="07d5d-112">Pour activer la gestion d’urgence pour un téléphone de partie commune, vous devez modifier la stratégie de client qui a été attribuée à ce téléphone (ou à la collection de téléphones).</span><span class="sxs-lookup"><span data-stu-id="07d5d-112">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="07d5d-113">Une fois que vous avez identifié la stratégie qui doit être modifiée, l’étape suivante consiste à utiliser l’applet de commande **Set-CsClientPolicy** pour définir le paramètre EnableHotdesking sur true.</span><span class="sxs-lookup"><span data-stu-id="07d5d-113">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="07d5d-114">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="07d5d-114">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="07d5d-115">Vous pouvez également utiliser la cmdlet **New-CsClientPolicy** pour créer une nouvelle stratégie client qui permet la connexion à chaud.</span><span class="sxs-lookup"><span data-stu-id="07d5d-115">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="07d5d-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="07d5d-116">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="07d5d-117">Une fois cette stratégie créée, vous devez l’affecter aux téléphones de la partie commune appropriés.</span><span class="sxs-lookup"><span data-stu-id="07d5d-117">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="07d5d-118">Pour plus d’informations, consultez <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">la rubrique Assign Policies in Lync Server 2013 à un téléphone de partie commune</A>.</span><span class="sxs-lookup"><span data-stu-id="07d5d-118">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="07d5d-119">Désactivation de l’assistance à chaud</span><span class="sxs-lookup"><span data-stu-id="07d5d-119">Disabling hot desking</span></span>

  - <span data-ttu-id="07d5d-120">Pour désactiver la connexion à chaud pour un téléphone de partie commune, réinitialisez le paramètre EnableHotdesking de la cmdlet **Set-CsClientPolicy** sur la valeur par défaut false.</span><span class="sxs-lookup"><span data-stu-id="07d5d-120">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="07d5d-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="07d5d-121">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="07d5d-122">Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) et la cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="07d5d-122">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

