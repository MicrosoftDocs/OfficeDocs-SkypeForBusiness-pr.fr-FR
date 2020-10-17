---
title: 'Lync Server 2013 : suppression des profils de stratégie de bande passante réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6f43f8c6aae2dec5ea55463c1896f327f008980
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525351"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="0a1ee-102">Suppression des profils de stratégie de bande passante réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a1ee-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a1ee-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a1ee-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a1ee-104">La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="0a1ee-105">Dans Microsoft Lync Server 2013, seules les modalités audio et vidéo peuvent se voir affecter des limites de bande passante.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="0a1ee-106">Vous pouvez définir des restrictions de bande passante et de session globales.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="0a1ee-107">Vous pouvez utiliser le panneau de configuration Lync Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="0a1ee-108">Utilisez les procédures suivantes pour supprimer des profils de stratégies de bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="0a1ee-109">Pour plus d’informations sur la création ou la modification d’un profil de stratégie de bande passante réseau, consultez la rubrique [création ou modification de profils de stratégie de bande passante dans Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0a1ee-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="0a1ee-110">Pour supprimer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="0a1ee-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="0a1ee-111">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a1ee-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a1ee-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a1ee-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a1ee-114">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="0a1ee-115">Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a1ee-p103">Vous pouvez supprimer plusieurs profils à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs profils. Pour sélectionner tous les profils, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-p103">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="0a1ee-119">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0a1ee-120">Vous ne pouvez pas supprimer un profil de stratégie de bande passante associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="0a1ee-121">Vous devez d’abord supprimer l’association au site réseau avant de supprimer le profil.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="0a1ee-122">Pour plus d’informations sur la modification du site réseau, reportez-vous à la rubrique <A href="lync-server-2013-creating-or-modifying-network-sites.md">création ou modification de sites réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0a1ee-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a1ee-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a1ee-123">See Also</span></span>


[<span data-ttu-id="0a1ee-124">Création ou modification des profils de stratégie de bande passante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a1ee-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="0a1ee-125">Affichage des informations de profil de stratégie de bande passante réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a1ee-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="0a1ee-126">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a1ee-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="0a1ee-127">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="0a1ee-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

