---
title: Vue d’ensemble de la gestion des salles d’équipes Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Vue d’ensemble de la gestion des salles d’équipes Microsoft.
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32208245"
---
# <a name="management-overview"></a><span data-ttu-id="b537a-103">Vue d’ensemble de la gestion</span><span class="sxs-lookup"><span data-stu-id="b537a-103">Management overview</span></span> 

<span data-ttu-id="b537a-104">Il est essentiel de développer et exécuter la maintenance régulière et opérations pour vous assurer que vos systèmes salles d’équipes Microsoft sont disponibles pour vos utilisateurs et fournir un utilisateur un expérience.</span><span class="sxs-lookup"><span data-stu-id="b537a-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="b537a-105">Surveillance</span><span class="sxs-lookup"><span data-stu-id="b537a-105">Monitoring</span></span> 

<span data-ttu-id="b537a-106">Surveillance des systèmes de salles d’équipes Microsoft se compose de deux activités clés :</span><span class="sxs-lookup"><span data-stu-id="b537a-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="b537a-107">APPAREIL, application et surveillance du périphérique</span><span class="sxs-lookup"><span data-stu-id="b537a-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="b537a-108">Qualité et la fiabilité de la surveillance (CQD)</span><span class="sxs-lookup"><span data-stu-id="b537a-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="b537a-109">Dispositif de salles d’équipes Microsoft, application et surveillance du périphérique</span><span class="sxs-lookup"><span data-stu-id="b537a-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="b537a-110">Pour vous assurer que les utilisateurs sont en mesure d’utiliser les unités de salles d’équipes Microsoft, les unités doivent se trouver sur concernant au réseau avec l’application Microsoft équipes salles correctement configurée et être connectées à des périphériques fonctionne.</span><span class="sxs-lookup"><span data-stu-id="b537a-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="b537a-111">Pour plus d’informations sur l’état de l’application Microsoft équipes salles et les périphériques connectés sont écrits par l’application Microsoft équipes salles dans le journal des événements Windows et expliquées dans [comprendre les entrées du journal](azure-monitor.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="b537a-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="b537a-112">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="b537a-112">**Setting**</span></span>|<span data-ttu-id="b537a-113">**Permet de**</span><span class="sxs-lookup"><span data-stu-id="b537a-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b537a-114">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="b537a-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="b537a-115">Permet de salles d’équipes Microsoft amorçage</span><span class="sxs-lookup"><span data-stu-id="b537a-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="b537a-116">Gestion - de l’alimentation\> sur CA, désactiver écran au bout de 10 minutes</span><span class="sxs-lookup"><span data-stu-id="b537a-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="b537a-117">Gestion - de l’alimentation\> sur CA, placez jamais système en mode veille</span><span class="sxs-lookup"><span data-stu-id="b537a-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="b537a-118">Permet de salles d’équipes Microsoft activer affiche attaché et réactiver automatiquement</span><span class="sxs-lookup"><span data-stu-id="b537a-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="b537a-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="b537a-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="b537a-120">Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local.</span><span class="sxs-lookup"><span data-stu-id="b537a-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="b537a-121">Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="b537a-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="b537a-122">Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.</span><span class="sxs-lookup"><span data-stu-id="b537a-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="b537a-123">Active le compte Skype avec lequel toujours se connecter</span><span class="sxs-lookup"><span data-stu-id="b537a-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="b537a-124">Transfert de fichiers à l’aide de stratégies de groupe est traitée dans [un élément de fichier de configuration](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b537a-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="b537a-125">Gestion distante à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b537a-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="b537a-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="b537a-126"></span></span>

<span data-ttu-id="b537a-127">Nous recommandons d’utiliser Microsoft Operations Manager Suite à surveiller vos systèmes salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b537a-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="b537a-128">Pour obtenir des instructions sur la configuration de surveillance et les alertes de base, voir [gestion de déployer Microsoft équipes salles avec Azure moniteur](../../deploy/deploy-clients/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="b537a-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md).</span></span> 

<span data-ttu-id="b537a-129">À l’aide de ce guide, vous pouvez créer un tableau de bord simple à utiliser pour identifier des problèmes avec des unités de vos salles d’équipes Microsoft dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="b537a-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="b537a-130">Points de décision</span><span class="sxs-lookup"><span data-stu-id="b537a-130">Decision points</span></span>|<ul><li><span data-ttu-id="b537a-131">Vérifiez que vous allez utiliser la Suite de gestion des opérations de déploiement de Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="b537a-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="b537a-132">Décider de la liste de distribution cible que vous allez utiliser pour les alertes par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="b537a-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="b537a-133">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="b537a-133">Next steps</span></span>|<ul><li><span data-ttu-id="b537a-134">Définir votre qualité et la fiabilité approche de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b537a-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="b537a-135">Qualité et la fiabilité de la surveillance (CQD)</span><span class="sxs-lookup"><span data-stu-id="b537a-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="b537a-136">Nous vous recommandons d’implémenter qualité opérationnelle en cours et la fiabilité de la surveillance des procédures dans le cadre de votre déploiement pour surveiller les tendances d’appel et de qualité de la réunion et de fiabilité, qui identifie les zones d’intérêt et utilisation d’une résolution.</span><span class="sxs-lookup"><span data-stu-id="b537a-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="b537a-137">Lorsque vous téléchargez vos informations de construction dans CQD vous pouvez examiner les tendances qualité et la fiabilité d’appel sur un niveau par construction, ce qui facilite la comparaison de bâtiments et concentrer votre attention sur des problèmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b537a-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="b537a-138">Pour plus d’informations, téléchargez le [Moniteur-CQD pour Skype pour Business remise en ligne et le Guide des opérations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="b537a-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="b537a-139">Nous vous recommandons de consulter et suivre le [Guide Quality of Experience passez en revue](https://aka.ms/qerguide) pour identifier les tendances de qualité et la fiabilité et créer un plan d’action pour les résoudre.</span><span class="sxs-lookup"><span data-stu-id="b537a-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="b537a-140">Mise à jour de l’application Microsoft équipes salles de système d’exploitation et de salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="b537a-140">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="b537a-141">Il est recommandé que vous mettez à jour l’application du système d’exploitation salles d’équipes Microsoft et les salles d’équipes Microsoft afin de bénéficier de mises à jour et améliorations.</span><span class="sxs-lookup"><span data-stu-id="b537a-141">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="b537a-142">Pour obtenir des instructions détaillées, voir [Gérer les salles d’équipes Microsoft](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="b537a-142">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="b537a-143">Mises à jour Windows</span><span class="sxs-lookup"><span data-stu-id="b537a-143">Windows Updates</span></span>

<span data-ttu-id="b537a-144">Salles d’équipes Microsoft s’exécute sur Windows 10 entreprise IoT ou entreprise de 10 Windows (VL) et reçoit les même versions mises à jour Windows et du système d’exploitation de bureau standard.</span><span class="sxs-lookup"><span data-stu-id="b537a-144">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="b537a-145">Pour plus d’informations, voir [Gérer les mises à jour de Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="b537a-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="b537a-146">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="b537a-146">Troubleshooting</span></span>

<span data-ttu-id="b537a-147">Nous vous recommandons de configurer Suite de gestion des opérations d’alerte comme décrit dans la section ci-dessus afin que votre équipe chargée des opérations et le support technique seront informés de tous les problèmes salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b537a-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="b537a-148">Les options dont vous disposez pour la gestion à distance PowerShell sont décrits dans la [gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="b537a-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="b537a-149">Dans le cas où un périphérique est déconnecté, vous devrez peut-être s’appuient sur locales mains « actives » ou la prise en charge de l’informatique d’analyser et reconnectez les périphériques.</span><span class="sxs-lookup"><span data-stu-id="b537a-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="b537a-150">Pour plus d’informations sur le mode de résolution des problèmes et d’administration, voir [Gérer les salles d’équipes Microsoft](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="b537a-150">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="b537a-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b537a-151">See also</span></span>

[<span data-ttu-id="b537a-152">Aide Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="b537a-152">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="b537a-153">Planifier des équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="b537a-153">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="b537a-154">Déployer les équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="b537a-154">Deploy Microsoft Teams Rooms</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="b537a-155">Configurer une console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="b537a-155">Configure a Microsoft Teams Rooms console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="b537a-156">Gérer les paramètres de console de salles d’équipes Microsoft à distance avec un fichier de configuration XML</span><span class="sxs-lookup"><span data-stu-id="b537a-156">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
