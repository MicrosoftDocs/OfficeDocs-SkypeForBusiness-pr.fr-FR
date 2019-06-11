---
title: 'Lync Server 2013: activation du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20cd0f7792f8db2cf1b2d817bfe79ed6d6b16fce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="1aff4-102">Activation du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aff4-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1aff4-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1aff4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1aff4-104">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux qui permettant de définir des restrictions pour les transmissions audio et vidéo en fonction de la bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="1aff4-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="1aff4-105">Après avoir configuré le réseau CAC, vous devez activer le CAC pour appliquer les limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="1aff4-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="1aff4-106">Pour cela, vous pouvez utiliser le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aff4-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="1aff4-107">Pour activer le CAC à partir du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1aff4-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1aff4-108">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1aff4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1aff4-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1aff4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1aff4-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1aff4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1aff4-111">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **Global**.</span><span class="sxs-lookup"><span data-stu-id="1aff4-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="1aff4-112">Dans la page **Global** , cliquez sur configuration **globale** .</span><span class="sxs-lookup"><span data-stu-id="1aff4-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1aff4-113">Un seul réseau peut être configuré pour n’importe quel déploiement de Microsoft Lync Server 2013, de sorte qu’il ne reste jamais plus d’une configuration réseau dans la liste.</span><span class="sxs-lookup"><span data-stu-id="1aff4-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="1aff4-114">Vous ne pouvez pas renommer la configuration globale.</span><span class="sxs-lookup"><span data-stu-id="1aff4-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="1aff4-115">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1aff4-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1aff4-116">Dans la page **modifier le paramètre global** , activez la case à cocher **activer le contrôle d’admission des appels** , puis cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="1aff4-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="1aff4-117">Lorsque vous cliquez sur **valider**, vous effectuez un test de la configuration.</span><span class="sxs-lookup"><span data-stu-id="1aff4-117">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="1aff4-118">La boîte de dialogue **modifier les paramètres globaux** se ferme et vous permet de revenir à la page **globale** .</span><span class="sxs-lookup"><span data-stu-id="1aff4-118">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="1aff4-119">Vous recevez un avertissement en cas d’erreurs ou d’éventuelles incohérences détectées dans votre configuration réseau qui empêche celle-ci de fonctionner correctement (par exemple, si chaque région n’est pas connectée à une autre région par le biais d’un itinéraire interrégion).</span><span class="sxs-lookup"><span data-stu-id="1aff4-119">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="1aff4-120">Si vous apportez des modifications à la configuration de votre réseau, vous pouvez exécuter de nouveau le contrôle de validation en ouvrant la configuration globale et en cliquant sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="1aff4-120">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="1aff4-121">Vous n’avez pas besoin de désactiver le CAC d’abord: laissez la case à cocher activée, puis cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="1aff4-121">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="1aff4-122">Vous pouvez le faire à tout moment sans apporter de modifications à la configuration.</span><span class="sxs-lookup"><span data-stu-id="1aff4-122">You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1aff4-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1aff4-123">See Also</span></span>


[<span data-ttu-id="1aff4-124">Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aff4-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="1aff4-125">Planification du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aff4-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="1aff4-126">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1aff4-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="1aff4-127">Get-Csnetworkconfiguration permettent</span><span class="sxs-lookup"><span data-stu-id="1aff4-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="1aff4-128">Set-Csnetworkconfiguration permettent</span><span class="sxs-lookup"><span data-stu-id="1aff4-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="1aff4-129">Remove-Csnetworkconfiguration permettent</span><span class="sxs-lookup"><span data-stu-id="1aff4-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

