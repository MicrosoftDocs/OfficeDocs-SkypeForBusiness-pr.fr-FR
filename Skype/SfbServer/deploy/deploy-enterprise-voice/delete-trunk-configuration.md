---
title: Supprimer une collection existante de paramètres de configuration jonction SIP dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 'Résumé : Découvrez comment supprimer une collection de paramètres de configuration de jonction à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: da86cbaf45afa47de580c02ab74e3b0b9bb344bf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223154"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="8d7c0-103">Supprimer une collection existante de paramètres de configuration jonction SIP dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="8d7c0-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="8d7c0-104">**Résumé :** Découvrez comment supprimer une collection de paramètres de configuration de jonction à l’aide de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="8d7c0-p101">Les paramètres de configuration de jonction SIP (Session Initiation Protocol) définissent la relation et les possibilités entre un serveur de médiation et la passerelle du réseau téléphonique commuté (RTC), un autocommutateur privé IP (PBX) ou le contrôleur SBC (Session Border Controller) du côté fournisseur de services. Ces paramètres spécifient, par exemple :</span><span class="sxs-lookup"><span data-stu-id="8d7c0-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="8d7c0-107">si la déviation du trafic multimédia doit être activée sur les jonctions ;</span><span class="sxs-lookup"><span data-stu-id="8d7c0-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="8d7c0-108">les conditions dans lesquelles les paquets RTCP sont envoyés ;</span><span class="sxs-lookup"><span data-stu-id="8d7c0-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="8d7c0-109">si le chiffrement SRTP (Secure Real-Time Protocol ) est requis ou non sur chaque jonction.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="8d7c0-110">Lorsque vous installez Skype pour Business Server, une collection de paramètres de configuration de jonction SIP globale est créée pour vous.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="8d7c0-111">Cette collection de paramètres globale ne peuvent pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="8d7c0-112">Toutefois, vous pouvez utiliser la Skype pour le panneau de configuration serveur Business ou l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) « réinitialiser » les propriétés dans la collection globale à leurs valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="8d7c0-113">Par exemple, si vous avez défini la propriété Enable3pccRefer la valeur True, lorsque vous réinitialisez la collection globale, la propriété Enable3pccRefer est rétabli à sa valeur par défaut False.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="8d7c0-p103">Les administrateurs peuvent aussi créer des paramètres de configuration de jonction personnalisés étendus à un site ou un service (pour une passerelle RTC individuelle). Ces paramètres personnalisés peuvent être supprimés. Lors de la suppression de ces paramètres personnalisés, tenez compte des points suivants :</span><span class="sxs-lookup"><span data-stu-id="8d7c0-p103">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed. When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="8d7c0-p104">Si vous supprimez des paramètres étendus à un service, la jonction SIP (Session Initiation Protocol) gérée par ces paramètres est gérée par les paramètres appliqués à son site, le cas échéant. En l’absence de paramètres de site, la jonction est gérée par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-p104">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist. If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="8d7c0-118">Si vous supprimez des paramètres étendus à un site, les jonctions SIP (Session Initiation Protocol) gérées par ces paramètres sont alors gérées par la collection globale de paramètres de configuration de jonction.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="8d7c0-119">Pour supprimer les paramètres de configuration de jonction avec Skype pour le panneau de configuration serveur Business</span><span class="sxs-lookup"><span data-stu-id="8d7c0-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="8d7c0-120">Dans Skype pour Business Server le panneau de configuration, cliquez sur **Routage des communications vocales** , puis cliquez sur **Configuration de jonction**.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="8d7c0-p105">Sous l’onglet **Configuration de la jonction**, sélectionnez la collection de paramètres de configuration de jonction SIP (Session Initiation Protocol) à supprimer, cliquez sur **Modifier**, puis sur **Supprimer**. Pour supprimer plusieurs collections en une seule opération, cliquez sur la première collection à supprimer, maintenez la touche Ctrl enfoncée et cliquez sur les autres collections à supprimer.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-p105">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**. To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="8d7c0-p106">La propriété **État** de la collection est définie sur la valeur **Non validé**. Pour valider les modifications et supprimer la collection, cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-p106">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="8d7c0-125">Dans la boîte de dialogue **Paramètres de configuration de la voix non validés**, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="8d7c0-126">Dans la boîte de dialogue **Skype pour Business Server le panneau de configuration** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="8d7c0-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="8d7c0-128">Lorsque la boîte de dialogue **Skype pour le panneau de configuration serveur Business** s’affiche, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="8d7c0-129">Suppression des paramètres de Configuration de jonction à l’aide de Skype pour les applets de commande Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8d7c0-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="8d7c0-130">Vous pouvez supprimer les paramètres de configuration de jonction à l’aide de Skype pour Business Server Management Shell et l’applet de commande **Remove-CsTrunkConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8d7c0-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="8d7c0-131">Vous pouvez exécuter cette applet de commande que ce soit par le Skype pour Business Server Management Shell ou d’une session à distance de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8d7c0-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="8d7c0-132">Pour supprimer une collection de paramètres spécifiée</span><span class="sxs-lookup"><span data-stu-id="8d7c0-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="8d7c0-133">La commande ci-dessous supprime les paramètres de configuration de jonction appliqués au site Redmond :</span><span class="sxs-lookup"><span data-stu-id="8d7c0-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="8d7c0-134">Pour supprimer toutes les collections appliquées dans l’étendue du site</span><span class="sxs-lookup"><span data-stu-id="8d7c0-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="8d7c0-135">Cette commande supprime tous les paramètres de configuration de jonction appliqués dans l’étendue du site :</span><span class="sxs-lookup"><span data-stu-id="8d7c0-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="8d7c0-136">Pour supprimer toutes les collections pour lesquelles la déviation du trafic multimédia est activée</span><span class="sxs-lookup"><span data-stu-id="8d7c0-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="8d7c0-137">La commande ci-dessous supprime tous les paramètres de configuration de jonction pour lesquels la déviation du trafic multimédia est activée :</span><span class="sxs-lookup"><span data-stu-id="8d7c0-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="8d7c0-138">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8d7c0-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

