---
title: 'Lync Server 2013 : suppression d’un site ou d’une stratégie utilisateur pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce2f822bb1fc42d385cec762b86c5a674d50c872
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516321"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="461fa-102">Supprimer une stratégie d’utilisateur ou de site pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="461fa-102">Delete a site or user policy for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="461fa-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="461fa-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="461fa-104">Vous pouvez supprimer n’importe quelle stratégie d’utilisateur ou de site figurant dans le panneau de configuration Lync Server sur la page **stratégie d’accès externe** .</span><span class="sxs-lookup"><span data-stu-id="461fa-104">You can delete any site or user policy that is listed in Lync Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="461fa-105">La suppression de la stratégie globale ne la supprime pas, mais la rétablit uniquement aux paramètres par défaut, qui ne prennent pas en charge les options d’accès des utilisateurs externes.</span><span class="sxs-lookup"><span data-stu-id="461fa-105">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="461fa-106">Pour plus d’informations sur la réinitialisation de la stratégie globale, voir [Réinitialiser la stratégie globale pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="461fa-106">For details about resetting the global policy, see [Reset the global policy for external user access in Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).</span></span>

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="461fa-107">Pour supprimer une stratégie d’utilisateur ou de site pour l’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="461fa-107">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="461fa-108">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="461fa-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="461fa-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="461fa-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="461fa-110">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="461fa-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="461fa-111">Cliquez sur **accès des utilisateurs externes**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="461fa-111">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="461fa-112">Sous l’onglet **stratégie d’accès externe** , cliquez sur la stratégie de site ou d’utilisateur à supprimer, cliquez sur **modifier**, puis cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="461fa-112">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="461fa-113">À l’invite de confirmation de la suppression, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="461fa-113">When prompted to confirm the deletion, click **OK**.</span></span>

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="461fa-114">Suppression de stratégies de code confidentiel à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="461fa-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="461fa-115">Les stratégies d’accès externe peuvent être supprimées à l’aide de Windows PowerShell et de l’applet de commande Remove-CsExternalAccessPolicy.</span><span class="sxs-lookup"><span data-stu-id="461fa-115">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="461fa-116">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="461fa-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="461fa-117">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="461fa-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="461fa-118">Pour supprimer une stratégie d’accès externe spécifique</span><span class="sxs-lookup"><span data-stu-id="461fa-118">To remove a specific external access policy</span></span>

  - <span data-ttu-id="461fa-119">Cette commande supprime la stratégie d’accès externe appliquée au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="461fa-119">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="461fa-120">Pour supprimer toutes les stratégies d’accès externe appliquées à l’étendue par utilisateur</span><span class="sxs-lookup"><span data-stu-id="461fa-120">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="461fa-121">Cette commande permet de supprimer toutes les stratégies d’accès externe configurées au niveau de l’étendue utilisateur :</span><span class="sxs-lookup"><span data-stu-id="461fa-121">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="461fa-122">Pour supprimer toutes les stratégies d’accès externe dans lesquelles l’accès des utilisateurs externes est désactivé</span><span class="sxs-lookup"><span data-stu-id="461fa-122">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="461fa-123">Cette commande supprime toutes les stratégies d’accès externe dans lesquelles l’accès des utilisateurs extérieurs a été désactivé :</span><span class="sxs-lookup"><span data-stu-id="461fa-123">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

<span data-ttu-id="461fa-124">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .</span><span class="sxs-lookup"><span data-stu-id="461fa-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

