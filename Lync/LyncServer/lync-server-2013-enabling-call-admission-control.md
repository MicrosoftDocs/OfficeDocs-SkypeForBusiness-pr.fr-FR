---
title: 'Lync Server 2013 : activation du contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfe6ae76fd1f6b89178d101337f24ba0089dd35b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500981"
---
# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="5bd4e-102">Activation du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd4e-102">Enabling call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bd4e-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5bd4e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5bd4e-104">Le contrôle d’admission des appels est un réseau de régions, de sites et de sous-réseaux vous permettant de placer des restrictions sur les transmissions audio et vidéo en fonction de la bande passante disponible.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="5bd4e-105">Après avoir configuré le réseau CAC, vous devez l’activer pour qu’il applique les limites de bande passante.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="5bd4e-106">Pour ce faire, vous pouvez utiliser le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="5bd4e-107">Pour activer le contrôle d’admission des communications à partir du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="5bd4e-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5bd4e-108">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5bd4e-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5bd4e-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5bd4e-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5bd4e-111">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Globale**.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="5bd4e-112">Dans la page **Globale**, cliquez sur la configuration **Globale**.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5bd4e-113">Un seul réseau peut être configuré pour un déploiement de Microsoft Lync Server 2013, de sorte qu’il n’y aura jamais plus d’une configuration réseau dans la liste.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="5bd4e-114">Il n’est pas possible de renommer la configuration Globale.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="5bd4e-115">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="5bd4e-116">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer le contrôle d’admission des appels**, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="5bd4e-p104">Lorsque vous cliquez sur **Valider**, un test de la configuration est exécuté. La boîte de dialogue **Modifier la configuration globale** se ferme et vous retournez à la page **Globale**. Vous obtiendrez un message d’avertissement si des erreurs ou des incohérences, qui empêcheront la configuration du réseau de fonctionner correctement, sont détectées (par exemple, si chaque région n’est pas connectée aux autres régions via un itinéraire interrégion).</span><span class="sxs-lookup"><span data-stu-id="5bd4e-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="5bd4e-p105">Si vous modifiez la configuration du réseau, vous pouvez exécuter de nouveau la vérification de validation. Pour cela, ouvrez la configuration globale et cliquez sur **Valider**. Vous n’avez pas besoin de désactiver d’abord le CAC : ne désactivez pas la case à cocher et cliquez sur **Valider**. Vous pouvez lancer la vérification à tout moment même si vous ne modifiez pas la configuration.</span><span class="sxs-lookup"><span data-stu-id="5bd4e-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5bd4e-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5bd4e-123">See Also</span></span>


[<span data-ttu-id="5bd4e-124">Vue d’ensemble du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd4e-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="5bd4e-125">Planification du contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd4e-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="5bd4e-126">Configurer le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bd4e-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="5bd4e-127">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5bd4e-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="5bd4e-128">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5bd4e-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="5bd4e-129">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="5bd4e-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

