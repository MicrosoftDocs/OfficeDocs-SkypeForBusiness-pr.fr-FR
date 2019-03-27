---
title: Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype pour les entreprises
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Découvrez comment exporter ou importer un fichier de configuration de routage voix dans Skype pour Business Server à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: 8f0d8f4e221cbe23ac37c4126a9d26aac46e6d53
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874842"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="491d7-103">Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="491d7-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="491d7-104">**Résumé :** Découvrez comment exporter ou importer un fichier de configuration de routage voix dans Skype pour Business Server à l’aide de la Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="491d7-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="491d7-105">Si vous souhaitez enregistrer la configuration du routage des communications vocales sans la publier, suivez cette procédure pour enregistrer et extraire une capture instantanée de votre configuration du routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="491d7-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="491d7-106">Lorsque vous importez un fichier de configuration de routage voix (.vcfg), mais les modifications ont été apportées à la voix configuration du routage sur le serveur dans le même temps, les pages du groupe de **Routage des communications vocales** dans Skype pour le panneau de configuration serveur Business indiquera qu’il sont des modifications non validées à la voix de routage.</span><span class="sxs-lookup"><span data-stu-id="491d7-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="491d7-107">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="491d7-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="491d7-108">Si vous avez apporté des modifications non validées aux paramètres de n’importe quelle page au sein du groupe, les modifications sont enregistrées dans le fichier de configuration vocale exporté (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="491d7-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="491d7-109">Cela vous permet de vous permettent d’effectuer le routage des modifications de configuration au cours de plusieurs sessions avant de publier les modifications de communications vocales.</span><span class="sxs-lookup"><span data-stu-id="491d7-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="491d7-110">Pour exporter une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="491d7-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="491d7-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="491d7-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="491d7-112">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="491d7-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="491d7-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="491d7-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="491d7-114">Dans le menu **Actions**, cliquez sur **Exporter la configuration**.</span><span class="sxs-lookup"><span data-stu-id="491d7-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="491d7-115">Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="491d7-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="491d7-116">Pour importer une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="491d7-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="491d7-117">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="491d7-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="491d7-118">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="491d7-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="491d7-119">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="491d7-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="491d7-120">Dans le menu **Actions**, cliquez sur **Importer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="491d7-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="491d7-121">Recherchez le fichier de configuration à importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="491d7-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="491d7-122">Cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="491d7-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="491d7-123">Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="491d7-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="491d7-124">Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="491d7-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

