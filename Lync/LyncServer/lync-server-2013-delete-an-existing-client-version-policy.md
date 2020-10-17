---
title: 'Lync Server 2013 : suppression d’une stratégie de version de client existante'
description: 'Lync Server 2013 : suppression d’une stratégie de version de client existante.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1328d54790b2a7856fa2776bb59feeb515bab1cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553660"
---
# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="25514-103">Supprimer une stratégie de version de client existante dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25514-103">Delete an existing client version policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25514-104">_**Dernière modification de la rubrique :** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="25514-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="25514-105">Si vous souhaitez supprimer une stratégie de version de client précédemment configurée, vous pouvez la supprimer du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="25514-105">If you want to delete a client version policy that was previously configured, you can delete it from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="25514-106">Pour supprimer des stratégies de version du client à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="25514-106">To delete client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="25514-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="25514-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="25514-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25514-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="25514-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="25514-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="25514-110">Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **stratégie de version du client** .</span><span class="sxs-lookup"><span data-stu-id="25514-110">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="25514-111">Sur la page **stratégie de version du client** , sélectionnez la ou les stratégies de version du client que vous souhaitez supprimer, cliquez sur **modifier**, puis sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="25514-111">On the **Client Version Policy** page, select the client version policy or policies you want to delete, click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="25514-112">Suppression des stratégies de version du client à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="25514-112">Deleting Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="25514-113">Vous pouvez supprimer des stratégies de version du client à l’aide de l’applet de commande **Remove-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="25514-113">You can delete client version policies by using the **Remove-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="25514-114">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25514-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="25514-115">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="25514-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-client-version-policy"></a><span data-ttu-id="25514-116">Pour supprimer une stratégie de version de client spécifique</span><span class="sxs-lookup"><span data-stu-id="25514-116">To remove a specific client version policy</span></span>

  - <span data-ttu-id="25514-117">Cette commande supprime la stratégie de version du client appliquée au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="25514-117">This command deletes the client version policy applied to the Redmond site:</span></span>
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a><span data-ttu-id="25514-118">Pour supprimer toutes les stratégies de version du client appliquées à l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="25514-118">To remove all the client version policies applied to the site scope</span></span>

  - <span data-ttu-id="25514-119">Cette commande permet de supprimer toutes les stratégies de version des clients configurées au niveau de l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="25514-119">This command removes all the client version policies configured at the site scope:</span></span>
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a><span data-ttu-id="25514-120">Pour supprimer des stratégies de version du client qui n’incluent pas d’agent utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="25514-120">To remove client version policies that do not include a specific user agent</span></span>

  - <span data-ttu-id="25514-121">Cette commande supprime toutes les stratégies de version du client qui n’incluent pas de règle pour l’agent utilisateur Windows Phone Lync (WPLync) :</span><span class="sxs-lookup"><span data-stu-id="25514-121">And this command removes any client version policies that do not include a rule for the Windows Phone Lync (WPLync) user agent:</span></span>
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

<span data-ttu-id="25514-122">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="25514-122">For details, see the Help topic for the [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

