---
title: Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype Entreprise
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 'Résumé : Découvrez comment exporter ou importer un fichier de configuration du routage des voix dans Skype Entreprise Server à l’aide du Panneau de configuration de Skype Entreprise Server.'
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830354"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="f8000-103">Exporter ou importer un fichier de configuration d’itinéraire de voix dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="f8000-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="f8000-104">**Résumé :** Découvrez comment exporter ou importer un fichier de configuration du routage des voix dans Skype Entreprise Server à l’aide du Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f8000-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="f8000-105">Si vous souhaitez enregistrer votre configuration de routage des voix sans la publier, suivez ces étapes pour enregistrer et récupérer un instantané de votre configuration de routage des voix.</span><span class="sxs-lookup"><span data-stu-id="f8000-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="f8000-106">Lorsque vous importez un fichier de configuration du routage des voix (.vcfg), mais que des modifications  ont été apportées à la configuration du routage des voix sur le serveur entre-temps, les pages du groupe de routage des voix du Panneau de configuration de Skype Entreprise Server indiquent que des modifications non prises en compte ont été apportées au routage des voix.</span><span class="sxs-lookup"><span data-stu-id="f8000-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="f8000-107">Ces modifications non validées représentent les différences entre les deux configurations qui doivent être rapprochées.</span><span class="sxs-lookup"><span data-stu-id="f8000-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="f8000-108">Si vous avez apporté des modifications non omises aux paramètres d’une page du groupe, les modifications sont enregistrées dans le fichier de configuration vocale exporté (.vcfg).</span><span class="sxs-lookup"><span data-stu-id="f8000-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="f8000-109">Cela vous permet d’apporter des modifications à la configuration du routage des voix au cours de plusieurs sessions avant de publier les modifications.</span><span class="sxs-lookup"><span data-stu-id="f8000-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="f8000-110">Pour exporter une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="f8000-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="f8000-111">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f8000-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f8000-112">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f8000-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f8000-113">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="f8000-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f8000-114">Dans le menu **Actions**, cliquez sur **Exporter la configuration**.</span><span class="sxs-lookup"><span data-stu-id="f8000-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="f8000-115">Spécifiez un emplacement et un nom de fichier, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f8000-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="f8000-116">Pour importer une configuration du routage des communications vocales</span><span class="sxs-lookup"><span data-stu-id="f8000-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="f8000-117">Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f8000-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f8000-118">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f8000-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f8000-119">Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.</span><span class="sxs-lookup"><span data-stu-id="f8000-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="f8000-120">Dans le menu **Actions**, cliquez sur **Importer la configuration**.</span><span class="sxs-lookup"><span data-stu-id="f8000-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="f8000-121">Recherchez le fichier de configuration que vous voulez importer, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="f8000-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="f8000-122">Cliquez sur **Valider**, puis sur **Valider tout**.</span><span class="sxs-lookup"><span data-stu-id="f8000-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f8000-123">Chaque fois que vous importez un fichier de configuration des communications vocales, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration.</span><span class="sxs-lookup"><span data-stu-id="f8000-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="f8000-124">Pour plus d’informations, voir Publier les modifications en attente de la configuration du [routage](voice-route-config-changes.md) des voix dans Skype Entreprise dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f8000-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

