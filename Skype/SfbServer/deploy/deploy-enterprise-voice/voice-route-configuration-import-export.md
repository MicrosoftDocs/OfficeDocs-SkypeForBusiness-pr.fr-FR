---
title: Exportation ou importation d’un fichier de configuration du routage des communications vocales dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Apprenez à exporter ou importer un fichier de configuration de routage voix dans Skype pour Business Server 2015 à l’aide de la Skype pour le panneau de configuration de Business Server.'
ms.openlocfilehash: 8b676ac6417c172402c231401ea9284fccbb8d97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business-2015"></a><span data-ttu-id="304cd-103">Exportation ou importation d’un fichier de configuration du routage des communications vocales dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="304cd-103">Export or import a voice route configuration file in Skype for Business 2015</span></span>
 
<span data-ttu-id="304cd-104">**Résumé :** Apprenez à exporter ou importer un fichier de configuration de routage voix dans Skype pour 2015 de serveur d’entreprise à l’aide de la Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="304cd-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server 2015 by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="304cd-105">Si vous souhaitez enregistrer la configuration du routage des communications vocales sans la publier, suivez cette procédure pour enregistrer et extraire une capture instantanée de votre configuration du routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="304cd-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="304cd-106">Lorsque vous importez un fichier de configuration de routage voix (.vcfg), mais les modifications ont été apportées à la voix configuration de routage sur le serveur dans le même temps, les pages dans le groupe de **Routage voix** dans Skype pour le panneau de configuration de Business Server va indiquer si sont des modifications non validées pour le routage de la voix.</span><span class="sxs-lookup"><span data-stu-id="304cd-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="304cd-107">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="304cd-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="304cd-108">Si vous avez apporté toutes les modifications non validées pour les paramètres de n’importe quelle page au sein du groupe, les modifications sont enregistrées dans le fichier de configuration exporté vocal (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="304cd-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="304cd-109">Cela vous permet de faire des voix routage des modifications de configuration au cours de plusieurs sessions avant de publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="304cd-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="304cd-110">Pour exporter une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="304cd-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="304cd-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="304cd-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="304cd-112">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="304cd-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="304cd-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="304cd-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="304cd-114">Dans le menu **Actions**, cliquez sur **Exporter la configuration**.</span><span class="sxs-lookup"><span data-stu-id="304cd-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="304cd-115">Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="304cd-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="304cd-116">Pour importer une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="304cd-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="304cd-117">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="304cd-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="304cd-118">Ouvrez Skype pour le panneau de configuration de Business Server.</span><span class="sxs-lookup"><span data-stu-id="304cd-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="304cd-119">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="304cd-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="304cd-120">Dans le menu **Actions**, cliquez sur **Importer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="304cd-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="304cd-121">Recherchez le fichier de configuration à importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="304cd-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="304cd-122">Cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="304cd-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="304cd-123">Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="304cd-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="304cd-124">Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md) dans la documentation d’opérations.</span><span class="sxs-lookup"><span data-stu-id="304cd-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

