---
title: Suppression d’une collection existante de paramètres de configuration de jonction SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. '
ms.openlocfilehash: 09f5e7fda03c5e0e5221661f87482b67192ce302
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045056"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b1f10-103">Suppression d’une collection existante de paramètres de configuration de jonction SIP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b1f10-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="b1f10-p101">Les paramètres de configuration de jonction SIP définissent la relation et les capacités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un autocommutateur privé IP (PBX) ou un contrôleur SBC du côté fournisseur de services. Ces paramètres permettent de spécifier ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b1f10-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="b1f10-106">L’activation ou non du contournement de média sur les jonctions.</span><span class="sxs-lookup"><span data-stu-id="b1f10-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="b1f10-107">Les conditions d’envoi des paquets RTCP (Real-time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="b1f10-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="b1f10-108">L’application ou non du chiffrement SRTP (Secure Real-Time Protocol) sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="b1f10-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b1f10-109">Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration de jonction SIP est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="b1f10-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b1f10-110">Cette collection globale de paramètres ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="b1f10-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="b1f10-111">Toutefois, vous pouvez utiliser le panneau ServerControl de Skype entreprise ou l’applet de commande [Remove-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) pour réinitialiser les propriétés de la collection globale à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="b1f10-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="b1f10-112">Par exemple, si vous avez défini la propriété Enable3pccRefer sur true, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer reprend sa valeur par défaut false.</span><span class="sxs-lookup"><span data-stu-id="b1f10-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="b1f10-p103">Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle PSTN individuelle) ; ces paramètres personnalisés peuvent être supprimés. Au moment de supprimer ces paramètres personnalisés, tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="b1f10-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="b1f10-p104">Si vous supprimez des paramètres étendus à un service, la jonction SIP gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="b1f10-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="b1f10-117">Si vous supprimez des paramètres étendus à un site, les jonctions SIP gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="b1f10-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="b1f10-118">**Pour supprimer les paramètres de configuration de jonction à l’aide du panneau de configuration Skype entreprise Server**</span><span class="sxs-lookup"><span data-stu-id="b1f10-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="b1f10-119">Dans le panneau de configuration de Skype entreprise Server, cliquez sur **routage des communications vocales**, puis sur Configuration de la **jonction**.</span><span class="sxs-lookup"><span data-stu-id="b1f10-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="b1f10-120">Dans l’onglet Configuration de la **jonction** , sélectionnez la collection de paramètres de configuration de jonction SIP à supprimer, cliquez sur **modifier**, puis sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b1f10-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="b1f10-121">Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres collections à supprimer.</span><span class="sxs-lookup"><span data-stu-id="b1f10-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="b1f10-p106">La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="b1f10-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="b1f10-124">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1f10-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="b1f10-125">Dans la boîte de dialogue **panneau de configuration de Skype entreprise Server** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1f10-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="b1f10-126">Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **valider**, puis sur **Annuler toutes les modifications non validées**.</span><span class="sxs-lookup"><span data-stu-id="b1f10-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="b1f10-127">Lorsque la boîte de dialogue **panneau de configuration de Skype entreprise Server** s’affiche, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1f10-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b1f10-128">Suppression des paramètres de configuration de jonction à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b1f10-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="b1f10-129">Vous pouvez supprimer les paramètres de configuration de jonction à l’aide de Windows PowerShell et de l’applet de commande **Remove-applet cstrunkconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b1f10-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="b1f10-130">Vous pouvez exécuter cette cmdlet à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b1f10-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="b1f10-131">**Pour supprimer une collection de paramètres spécifiée**</span><span class="sxs-lookup"><span data-stu-id="b1f10-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="b1f10-132">La commande suivante supprime les paramètres de configuration de jonction appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="b1f10-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="b1f10-133">**Pour supprimer toutes les collections appliquées à l’étendue site**</span><span class="sxs-lookup"><span data-stu-id="b1f10-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="b1f10-134">Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="b1f10-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="b1f10-135">**Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée**</span><span class="sxs-lookup"><span data-stu-id="b1f10-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="b1f10-136">La commande suivante supprime tous les paramètres de configuration de jonction dès lors que le contournement de média est activé :</span><span class="sxs-lookup"><span data-stu-id="b1f10-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="b1f10-137">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="b1f10-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
