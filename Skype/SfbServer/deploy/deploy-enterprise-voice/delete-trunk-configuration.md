---
title: Supprimer une collection existante de paramètres de configuration de Trunk SIP dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Résumé: Découvrez comment supprimer une collection de paramètres de configuration de Trunk en utilisant le panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: 5823c47234f912293c7af2a15bf1fcb87ff23e15
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233210"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8098a-103">Supprimer une collection existante de paramètres de configuration de Trunk SIP dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8098a-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="8098a-104">**Résumé:** Découvrez comment supprimer une collection de paramètres de configuration de Trunk en utilisant le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8098a-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="8098a-p101">Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :</span><span class="sxs-lookup"><span data-stu-id="8098a-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="8098a-107">si la déviation du trafic multimédia doit être activée sur les jonctions ;</span><span class="sxs-lookup"><span data-stu-id="8098a-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="8098a-108">les conditions dans lesquelles les paquets RTCP sont envoyés ;</span><span class="sxs-lookup"><span data-stu-id="8098a-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="8098a-109">si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="8098a-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="8098a-110">Lorsque vous installez Skype entreprise Server, une collection globale de paramètres de configuration SIP Trunk est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="8098a-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="8098a-111">Cette collection globale de paramètres ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="8098a-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="8098a-112">Toutefois, vous pouvez utiliser le panneau de configuration Skype entreprise Server ou l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) pour «réinitialiser» les propriétés de la collection globale à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="8098a-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="8098a-113">Par exemple, si vous avez défini la propriété Enable3pccRefer sur true, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer rétablira sa valeur par défaut false.</span><span class="sxs-lookup"><span data-stu-id="8098a-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="8098a-p103">Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle RTC individuelle). Ces paramètres personnalisés peuvent être supprimés. Lors de la suppression de ces paramètres personnalisés, tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="8098a-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="8098a-p104">Si vous supprimez des paramètres étendus à un service, la jonction SIP (Session Initiation Protocol) gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="8098a-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="8098a-118">Si vous supprimez des paramètres étendus à un site, les jonctions SIP (Session Initiation Protocol) gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="8098a-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="8098a-119">Pour supprimer les paramètres de configuration de Trunk avec le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8098a-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8098a-120">Dans le panneau de configuration Skype entreprise Server, cliquez sur **routage des communications vocales** , puis cliquez sur **configuration de Trunk**.</span><span class="sxs-lookup"><span data-stu-id="8098a-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="8098a-p105">Sous l’onglet **Configuration de la jonction**, sélectionnez la collection de paramètres de configuration de jonction SIP (Session Initiation Protocol) à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée et cliquez sur les autres collections à supprimer.</span><span class="sxs-lookup"><span data-stu-id="8098a-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="8098a-p106">La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="8098a-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="8098a-125">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8098a-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="8098a-126">Dans la boîte de dialogue **panneau de configuration Skype entreprise Server** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8098a-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="8098a-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="8098a-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="8098a-128">Lorsque la boîte de dialogue **panneau de configuration Skype entreprise Server** s’affiche, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8098a-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="8098a-129">Supprimer les paramètres de configuration de ligne à l’aide des applets de applet Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8098a-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="8098a-130">Vous pouvez supprimer des paramètres de configuration de Trunk en utilisant Skype entreprise Server Management Shell et l’applet de passe **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8098a-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="8098a-131">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session à distance de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8098a-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="8098a-132">Pour supprimer une collection de paramètres spécifiée</span><span class="sxs-lookup"><span data-stu-id="8098a-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="8098a-133">La commande ci-dessous supprime les paramètres de configuration de jonction appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="8098a-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="8098a-134">Pour supprimer toutes les collections appliquées dans l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="8098a-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="8098a-135">Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="8098a-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="8098a-136">Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée</span><span class="sxs-lookup"><span data-stu-id="8098a-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="8098a-137">La commande ci-dessous supprime tous les paramètres de configuration de jonction pour lesquels la déviation du trafic multimédia est activée :</span><span class="sxs-lookup"><span data-stu-id="8098a-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="8098a-138">Pour plus d’informations, reportez-vous à la rubrique d’aide relative à l’applet de passe [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8098a-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

