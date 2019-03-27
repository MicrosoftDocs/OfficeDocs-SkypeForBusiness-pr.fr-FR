---
title: Activer la qualité de l’expérience dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Résumé : Découvrez comment activer la qualité de l’expérience (QoE) dans Skype pour Business Server.'
ms.openlocfilehash: ba3b34769e5fb74aa641d89168ef7203bec0d2d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892342"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="90c2f-103">Activer la qualité de l’expérience dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="90c2f-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="90c2f-104">**Résumé :** Découvrez comment activer la qualité de l’expérience (QoE) dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c2f-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="90c2f-p101">La qualité de l’expérience (QoE) enregistre des données numériques qui indiquent la qualité du média, ainsi que les informations sur les participants, les noms des appareils, les pilotes, les adresses IP et les types de point de terminaison impliqués dans les appels et les sessions. Pour plus d’informations, voir [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="90c2f-p101">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions. For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="90c2f-107">Procédez comme suit pour activer la QoE dans toute l’entreprise ou dans chacun de ses sites.</span><span class="sxs-lookup"><span data-stu-id="90c2f-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="90c2f-p102">Pour activer la qualité de l’expérience, vous devez commencer par configurer la surveillance et une base de données principale de surveillance. Pour plus d’informations, voir [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="90c2f-p102">To enable QoE, you must first configure monitoring and a monitoring back-end database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="90c2f-110">Pour activer la QoE à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="90c2f-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="90c2f-111">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur n’importe quel ordinateur qui se trouve dans le réseau dans lequel vous avez déployé Skype pour Business Server .</span><span class="sxs-lookup"><span data-stu-id="90c2f-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="90c2f-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="90c2f-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="90c2f-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis cliquez sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="90c2f-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="90c2f-114">Dans la page **Données de qualité de l’expérience**, cliquez sur la collection appropriée dans le tableau, sur **Action**, puis sur **Activer QoE**.</span><span class="sxs-lookup"><span data-stu-id="90c2f-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="90c2f-115">Activation de QoE à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90c2f-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="90c2f-116">Vous pouvez activer QoE à l’aide de Windows PowerShell et l’applet de commande **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="90c2f-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="90c2f-117">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90c2f-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="90c2f-118">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Skype pour Business Server, consultez l’article de blog [« rapide démarrer : gestion de Microsoft PowerShell Lync Server 2010 à l’aide à distance »](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="90c2f-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="90c2f-119">Le processus est le même dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="90c2f-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="90c2f-120">Pour activer la qualité de l’expérience pour un emplacement</span><span class="sxs-lookup"><span data-stu-id="90c2f-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="90c2f-121">Pour activer la qualité de l’expérience, définissez le paramètre EnableQoE sur True ($True).</span><span class="sxs-lookup"><span data-stu-id="90c2f-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="90c2f-122">Pour désactiver la qualité de l’expérience pour un emplacement</span><span class="sxs-lookup"><span data-stu-id="90c2f-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="90c2f-p104">Pour désactiver la qualité de l’expérience, définissez le paramètre EnableQoE sur False ($False). Ceci ne désinstalle pas la surveillance, mais suspend la collecte et le stockage des données de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="90c2f-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="90c2f-126">Pour utiliser une commande pour activer la qualité de l’expérience dans plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="90c2f-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="90c2f-127">Cette commande active la qualité de l’expérience pour tous les paramètres de configuration QoE actuellement utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="90c2f-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="90c2f-128">Pour plus d’informations, voir [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="90c2f-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="90c2f-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90c2f-129">See also</span></span>

[<span data-ttu-id="90c2f-130">Planification de la surveillance</span><span class="sxs-lookup"><span data-stu-id="90c2f-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="90c2f-131">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="90c2f-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

