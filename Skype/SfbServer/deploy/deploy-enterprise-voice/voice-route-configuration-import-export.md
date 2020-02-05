---
title: Exporter ou importer un fichier de configuration de l’itinéraire vocal dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Découvrez comment exporter ou importer un fichier de configuration de l’acheminement vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: b980aa26f4d67cd1697ec17286e6af7d9e657e15
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766877"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="4ac92-103">Exporter ou importer un fichier de configuration de l’itinéraire vocal dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="4ac92-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="4ac92-104">**Résumé :** Découvrez comment exporter ou importer un fichier de configuration de l’acheminement vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4ac92-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="4ac92-105">Si vous souhaitez enregistrer la configuration du routage des communications vocales sans la publier, suivez cette procédure pour enregistrer et extraire une capture instantanée de votre configuration du routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="4ac92-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="4ac92-106">Lorsque vous importez un fichier de configuration de l’acheminement vocal (. VCFG), mais que des modifications ont été apportées à la configuration de routage de la voix du serveur, en attendant, les pages du groupe de routage de la **voix** du panneau de configuration Skype entreprise Server indiquent qu’il n’y a pas de modifications non validées sur le routage vocal.</span><span class="sxs-lookup"><span data-stu-id="4ac92-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="4ac92-107">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="4ac92-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="4ac92-108">Si vous avez apporté des modifications non validées aux paramètres sur n’importe quelle page du groupe, les modifications sont enregistrées dans le fichier de configuration de la voix exporté (. VCFG).</span><span class="sxs-lookup"><span data-stu-id="4ac92-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="4ac92-109">Cela vous permet de procéder à des modifications de la configuration de l’acheminement des messages pendant plusieurs sessions avant de publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="4ac92-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="4ac92-110">Pour exporter une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="4ac92-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="4ac92-111">Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4ac92-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="4ac92-112">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4ac92-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4ac92-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="4ac92-114">Dans le menu **Actions**, cliquez sur **Exporter la configuration**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="4ac92-115">Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="4ac92-116">Pour importer une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="4ac92-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="4ac92-117">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="4ac92-118">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4ac92-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4ac92-119">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="4ac92-120">Dans le menu **Actions**, cliquez sur **Importer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="4ac92-121">Recherchez le fichier de configuration à importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="4ac92-122">Cliquez sur **Valider**, puis sur **Tout valider**.</span><span class="sxs-lookup"><span data-stu-id="4ac92-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4ac92-123">Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="4ac92-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="4ac92-124">Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="4ac92-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

