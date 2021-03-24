---
title: Activer la qualité de l’expérience dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Résumé : Découvrez comment activer la qualité de l’expérience (QoE) dans Skype Entreprise Server.'
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095208"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="05863-103">Activer la qualité de l’expérience dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="05863-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="05863-104">**Résumé : Découvrez** comment activer la qualité de l’expérience (QoE) dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="05863-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="05863-105">La qualité de l’expérience (QoE) enregistre des données numériques qui indiquent la qualité du média, ainsi que les informations sur les participants, les noms des appareils, les pilotes, les adresses IP et les types de point de terminaison impliqués dans les appels et les sessions.</span><span class="sxs-lookup"><span data-stu-id="05863-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="05863-106">Pour plus d’informations, voir [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="05863-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="05863-107">Procédez comme suit pour activer la QoE dans toute l’entreprise ou dans chacun de ses sites.</span><span class="sxs-lookup"><span data-stu-id="05863-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="05863-108">Pour activer la qualité de l’expérience, vous devez commencer par configurer la surveillance et une base de données principale de surveillance.</span><span class="sxs-lookup"><span data-stu-id="05863-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="05863-109">Pour plus d’informations, voir [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span><span class="sxs-lookup"><span data-stu-id="05863-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="05863-110">Pour activer la qualité de l’expérience à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="05863-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="05863-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou qui dispose de droits d’utilisateur équivalents) ou affecté au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à tout ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="05863-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="05863-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="05863-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="05863-113">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Données de qualité de l’expérience**.</span><span class="sxs-lookup"><span data-stu-id="05863-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="05863-114">Dans la page **Données de qualité de l’expérience**, cliquez sur la collection appropriée dans le tableau, sur **Action**, puis sur **Activer QoE**.</span><span class="sxs-lookup"><span data-stu-id="05863-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="05863-115">Activation de la QoE à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="05863-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="05863-116">Vous pouvez activer la QoE à l’Windows PowerShell et à l’aide de l';cmdlet **Set-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="05863-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="05863-117">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="05863-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="05863-118">Pour plus d’informations sur l’utilisation des Windows PowerShell distantes pour se connecter à Skype Entreprise Server, consultez l’article de blog « Démarrage rapide : Gestion [de Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="05863-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="05863-119">Le processus est le même dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="05863-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="05863-120">Pour activer la qualité de l’expérience pour un emplacement</span><span class="sxs-lookup"><span data-stu-id="05863-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="05863-121">Pour activer la qualité de l’expérience, définissez le paramètre EnableQoE sur True ($True).</span><span class="sxs-lookup"><span data-stu-id="05863-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="05863-122">Pour désactiver la qualité de l’expérience pour un emplacement</span><span class="sxs-lookup"><span data-stu-id="05863-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="05863-p104">Pour désactiver la qualité de l’expérience, définissez le paramètre EnableQoE sur False ($False). Ceci ne désinstalle pas la surveillance, mais suspend la collecte et le stockage des données de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="05863-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="05863-126">Pour utiliser une commande pour activer la qualité de l’expérience dans plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="05863-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="05863-127">Cette commande active la qualité de l’expérience pour tous les paramètres de configuration QoE actuellement utilisés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="05863-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="05863-128">Pour plus d’informations, [voir Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="05863-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="05863-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="05863-129">See also</span></span>

[<span data-ttu-id="05863-130">Planification de la surveillance</span><span class="sxs-lookup"><span data-stu-id="05863-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="05863-131">Déploiement du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="05863-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)