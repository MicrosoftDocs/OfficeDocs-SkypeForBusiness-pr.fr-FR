---
title: Spécifier la conservation des données CDR dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Résumé : Découvrez comment gérer des détails des appels (CDR) des données d’enregistrements pour Skype pour Business Server.'
ms.openlocfilehash: 70fa015978b9b72d020fb52cf62ef749fabb4702
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898051"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="520b9-103">Spécifier la conservation des données CDR dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="520b9-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="520b9-104">**Résumé :** Découvrez comment gérer des détails des appels (CDR) des données d’enregistrements pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="520b9-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="520b9-p101">Par défaut, les données d’enregistrement des détails des appels sont vidées après un délai de 60 jours. Vous pouvez utiliser les paramètres de la page **Enregistrement des détails des appels** pour conserver les données pendant une période plus longue ou plus courte. Si vous désactivez la fonctionnalité d’enregistrement des détails des appels, les données capturées avant l’enregistrement seront également vidées.</span><span class="sxs-lookup"><span data-stu-id="520b9-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="520b9-p102">Vous devez configurer l’enregistrement des détails des appels et la qualité de l’expérience (QoE) afin de conserver les données pendant le même nombre de jours. Chaque appel dans les rapports des détails des appels (disponibles à partir de la page web Rapports du serveur de surveillance) comprend des informations d’enregistrement des détails des appels et QoE. Si la durée de vidage pour les données d’enregistrement des détails des appels et de QoE est différente, certains appels peuvent inclure uniquement des données d’enregistrement des détails des appels et d’autres exclusivement des données QoE.</span><span class="sxs-lookup"><span data-stu-id="520b9-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="520b9-111">Utilisez les procédures suivantes pour configurer les paramètres de vidage des données d’enregistrement des détails des appels.</span><span class="sxs-lookup"><span data-stu-id="520b9-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="520b9-112">Pour spécifier la conservation des données d’enregistrement des détails des appels</span><span class="sxs-lookup"><span data-stu-id="520b9-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="520b9-113">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="520b9-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="520b9-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="520b9-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="520b9-115">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Enregistrement des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="520b9-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="520b9-116">Dans la page **Enregistrement des détails des appels**, cliquez sur le site approprié dans le tableau, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="520b9-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="520b9-117">Pour activer le vidage, sélectionnez **Activer le vidage des enregistrements des détails des appels**.</span><span class="sxs-lookup"><span data-stu-id="520b9-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="520b9-118">Dans **Conserver les enregistrements des détails des appels pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les enregistrements des détails des appels sont à conserver.</span><span class="sxs-lookup"><span data-stu-id="520b9-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="520b9-119">Dans **Conserver les données de signalement d’erreurs pendant la durée maximale (jours) :**, sélectionnez le nombre maximum de jours pendant lesquels les rapports d’erreurs sont à conserver.</span><span class="sxs-lookup"><span data-stu-id="520b9-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="520b9-120">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="520b9-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="520b9-121">Spécification de rétention des détails des appels à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="520b9-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="520b9-122">Vous pouvez créer des paramètres de rétention des détails des appels à l’aide de Windows PowerShell et l’applet de commande Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="520b9-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="520b9-123">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="520b9-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="520b9-124">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="520b9-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="520b9-125">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="520b9-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="520b9-126">Pour spécifier la conservation des enregistrements des détails des appels pour un emplacement particulier</span><span class="sxs-lookup"><span data-stu-id="520b9-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="520b9-127">Cette commande vide les enregistrements des détails des appels pour le site de Redmond, et configure ce site pour qu’il conserve les enregistrements des détails des appels et les données de signalement d’erreurs pendant 20 jours.</span><span class="sxs-lookup"><span data-stu-id="520b9-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="520b9-128">Pour spécifier la conservation des enregistrements des détails des appels pour plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="520b9-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="520b9-129">Cette commande configure la conservation des enregistrements des détails des appels pour tous les paramètres de configuration des enregistrements des détails des appels actuellement appliqués dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="520b9-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="520b9-130">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="520b9-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="520b9-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="520b9-131">See also</span></span>

[<span data-ttu-id="520b9-132">(DCR) dans Skype pour Business Server des détails des appels</span><span class="sxs-lookup"><span data-stu-id="520b9-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
