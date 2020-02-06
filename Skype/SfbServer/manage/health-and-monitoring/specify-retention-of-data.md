---
title: Spécifier la conservation des données CDR dans Skype entreprise Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Résumé : Découvrez comment gérer les données d’enregistrement des détails des appels pour Skype entreprise Server.'
ms.openlocfilehash: 7cb9926ee8ec124b2fc75a69653c43c0150b6446
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817673"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="9f14e-103">Spécifier la conservation des données CDR dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9f14e-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="9f14e-104">**Résumé :** Apprenez à gérer les données d’enregistrement des détails des appels pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9f14e-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="9f14e-p101">Par défaut, les données d’enregistrement des détails des appels sont vidées après un délai de 60 jours. Vous pouvez utiliser les paramètres de la page **Enregistrement des détails des appels** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez la fonctionnalité d’enregistrement des détails des appels, les données capturées avant l’enregistrement seront également vidées.</span><span class="sxs-lookup"><span data-stu-id="9f14e-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9f14e-p102">Vous devez configurer l’enregistrement des détails des appels et la qualité de l’expérience (QoE) afin de conserver les données pendant le même nombre de jours. Chaque appel dans les rapports des détails des appels (disponibles à partir de la page web Rapports du serveur de surveillance) comprend des informations d’enregistrement des détails des appels et QoE. Si la durée de vidage pour les données d’enregistrement des détails des appels et de QoE est différente, certains appels peuvent inclure uniquement des données d’enregistrement des détails des appels et d’autres exclusivement des données QoE.</span><span class="sxs-lookup"><span data-stu-id="9f14e-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="9f14e-111">Utilisez les procédures suivantes pour configurer les paramètres de vidage des données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="9f14e-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="9f14e-112">Pour spécifier la conservation des données d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="9f14e-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="9f14e-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Skype entreprise Server. .</span><span class="sxs-lookup"><span data-stu-id="9f14e-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="9f14e-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9f14e-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9f14e-115">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="9f14e-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="9f14e-116">Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9f14e-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="9f14e-117">Pour activer le vidage, sélectionnez **Activer le vidage des enregistrements des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="9f14e-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="9f14e-118">Dans **Conserver les enregistrements des détails des appels pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les enregistrements des détails des appels sont à conserver.</span><span class="sxs-lookup"><span data-stu-id="9f14e-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="9f14e-119">Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.</span><span class="sxs-lookup"><span data-stu-id="9f14e-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="9f14e-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9f14e-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9f14e-121">Spécification de la rétention CDR en utilisant des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f14e-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9f14e-122">Vous pouvez créer des paramètres de rétention CDR à l’aide de Windows PowerShell et de l’applet de cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9f14e-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="9f14e-123">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f14e-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9f14e-124">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Skype entreprise Server, voir l’article sur le blog [« démarrage rapide : gestion de Microsoft Lync Server 2010 à l’aide de Remote PowerShell »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9f14e-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9f14e-125">Le processus est le même dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9f14e-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="9f14e-126">Pour spécifier la conservation des enregistrements des détails des appels pour un emplacement particulier</span><span class="sxs-lookup"><span data-stu-id="9f14e-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="9f14e-127">Cette commande vide les enregistrements des détails des appels pour le site de Redmond, et configure ce site pour qu’il conserve les enregistrements des détails des appels et les données de signalement d’erreurs pendant 20 jours.</span><span class="sxs-lookup"><span data-stu-id="9f14e-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="9f14e-128">Pour spécifier la conservation des enregistrements des détails des appels pour plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="9f14e-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="9f14e-129">Cette commande configure la conservation des enregistrements des détails des appels pour tous les paramètres de configuration des enregistrements des détails des appels actuellement appliqués dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="9f14e-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="9f14e-130">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9f14e-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9f14e-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f14e-131">See also</span></span>

[<span data-ttu-id="9f14e-132">Enregistrement des détails des appels (CDR) dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9f14e-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
