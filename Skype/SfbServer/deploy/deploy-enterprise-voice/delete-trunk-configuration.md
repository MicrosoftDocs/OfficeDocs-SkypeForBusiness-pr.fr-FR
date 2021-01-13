---
title: Supprimer une collection existante de paramètres de configuration de la configuration de la trunk SIP dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Résumé : Découvrez comment supprimer une collection de paramètres de configuration de trunk à l’aide du Panneau de configuration de Skype Entreprise Server.'
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836974"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d03cc-103">Supprimer une collection existante de paramètres de configuration de la configuration de la trunk SIP dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d03cc-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d03cc-104">**Résumé :** Découvrez comment supprimer une collection de paramètres de configuration de trunk à l’aide du Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d03cc-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="d03cc-105">Les paramètres de configuration de la trunk SIP définissent la relation et les fonctionnalités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (PSTN), un PBX (IP-Public Branch eXchange) ou un contrôleur SBC (Session Border Controller) chez le fournisseur de services.</span><span class="sxs-lookup"><span data-stu-id="d03cc-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="d03cc-106">Ces paramètres permettent de spécifier ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d03cc-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="d03cc-107">L’activation ou non du contournement de média sur les jonctions.</span><span class="sxs-lookup"><span data-stu-id="d03cc-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="d03cc-108">Conditions dans lesquelles les paquets RTCP (Realtime Transport Control Protocol) sont envoyés.</span><span class="sxs-lookup"><span data-stu-id="d03cc-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="d03cc-109">Si le chiffrement SRTP (Secure Realtime Transport Protocol) est requis sur chaque trunk.</span><span class="sxs-lookup"><span data-stu-id="d03cc-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="d03cc-110">Lorsque vous installez Skype Entreprise Server, une collection globale de paramètres de configuration de la trunk SIP est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="d03cc-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="d03cc-111">Cette collection globale de paramètres ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="d03cc-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="d03cc-112">Toutefois, vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server ou l';cmdlet [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) pour « réinitialiser » les valeurs par défaut des propriétés de la collection globale.</span><span class="sxs-lookup"><span data-stu-id="d03cc-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="d03cc-113">Par exemple, si vous avez définie la propriété Enable3pccRefer sur True, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer rétablit sa valeur par défaut false.</span><span class="sxs-lookup"><span data-stu-id="d03cc-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="d03cc-p103">Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle PSTN individuelle) ; ces paramètres personnalisés peuvent être supprimés. Au moment de supprimer ces paramètres personnalisés, tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="d03cc-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="d03cc-p104">Si vous supprimez des paramètres étendus à un service, la jonction SIP gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="d03cc-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="d03cc-118">Si vous supprimez des paramètres étendus à un site, les jonctions SIP gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="d03cc-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="d03cc-119">Pour supprimer les paramètres de configuration de la trunk avec le Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="d03cc-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="d03cc-120">Dans le Panneau de configuration de Skype Entreprise Server, cliquez **sur Routage** des voix, puis cliquez sur **Configuration de la configuration de la configuration de la ligne.**</span><span class="sxs-lookup"><span data-stu-id="d03cc-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="d03cc-p105">Sous l’onglet **Configuration de la jonction**, sélectionnez la collection de paramètres de configuration de jonction SIP à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée, puis cliquez sur les autres collections à supprimer.</span><span class="sxs-lookup"><span data-stu-id="d03cc-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="d03cc-p106">La propriété **État** de la collection est mise à jour et présente la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="d03cc-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="d03cc-125">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d03cc-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="d03cc-126">Dans la boîte de dialogue Panneau de contrôle Skype **Entreprise Server,** cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="d03cc-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="d03cc-127">Si vous changez d’avis et décidez de ne pas supprimer la collection, cliquez sur **Valider**, puis sur **Annuler toutes les modifications non validées**.</span><span class="sxs-lookup"><span data-stu-id="d03cc-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="d03cc-128">Lorsque la **boîte de dialogue Panneau de contrôle** Skype Entreprise Server s’affiche, cliquez sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="d03cc-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="d03cc-129">Suppression des paramètres de configuration de la trunk à l’aide des cmdlets Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d03cc-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="d03cc-130">Vous pouvez supprimer les paramètres de configuration de la connexion à l’aide de Skype Entreprise Server Management Shell et de l’cmdlet **Remove-CsTrunkConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="d03cc-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="d03cc-131">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d03cc-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="d03cc-132">Pour supprimer une collection spécifiée de paramètres</span><span class="sxs-lookup"><span data-stu-id="d03cc-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="d03cc-133">La commande suivante supprime les paramètres de configuration de jonction appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="d03cc-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="d03cc-134">Pour supprimer toutes les collections appliquées à l’étendue Site</span><span class="sxs-lookup"><span data-stu-id="d03cc-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="d03cc-135">Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="d03cc-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="d03cc-136">Pour supprimer toutes les collections où le contournement de média est activé</span><span class="sxs-lookup"><span data-stu-id="d03cc-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="d03cc-137">La commande suivante supprime tous les paramètres de configuration de jonction dès lors que le contournement de média est activé :</span><span class="sxs-lookup"><span data-stu-id="d03cc-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="d03cc-138">Pour plus d’informations, consultez la rubrique d’aide de l';cmdlet [Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d03cc-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

