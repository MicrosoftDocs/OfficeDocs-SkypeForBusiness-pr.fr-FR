---
title: Présentation de la gestion de systèmes de salle Skype v2
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
description: Vue d’ensemble de la gestion de systèmes de salle Skype v2.
ms.openlocfilehash: edd73c6ecf973d0d066b5f46d949a792bc0910c5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880284"
---
# <a name="management-overview"></a><span data-ttu-id="290bb-103">Vue d’ensemble de la gestion</span><span class="sxs-lookup"><span data-stu-id="290bb-103">Management overview</span></span> 

<span data-ttu-id="290bb-104">Il est essentiel de développer et exécuter la maintenance régulière et opérations pour vous assurer que votre v2 Skype salle systèmes sont disponibles pour vos utilisateurs et fournir un utilisateur un expérience.</span><span class="sxs-lookup"><span data-stu-id="290bb-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Skype Room Systems v2 systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="290bb-105">Surveillance</span><span class="sxs-lookup"><span data-stu-id="290bb-105">Monitoring</span></span> 

<span data-ttu-id="290bb-106">Surveillance v2 Skype salle systèmes se compose de deux activités clés :</span><span class="sxs-lookup"><span data-stu-id="290bb-106">Monitoring Skype Room Systems v2 systems consists of two key activities:</span></span>

-  <span data-ttu-id="290bb-107">APPAREIL, application et surveillance du périphérique</span><span class="sxs-lookup"><span data-stu-id="290bb-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="290bb-108">Qualité et la fiabilité de la surveillance (CQD)</span><span class="sxs-lookup"><span data-stu-id="290bb-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="290bb-109">Systèmes de salle Skype v2 DISPOSITIF, application et surveillance du périphérique</span><span class="sxs-lookup"><span data-stu-id="290bb-109">Skype Room Systems v2 device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="290bb-110">Pour vous assurer que les utilisateurs sont en mesure d’utiliser les unités de v2 Skype salle systèmes, les unités doivent se trouver sur concernant au réseau avec l’application v2 de systèmes de salle Skype correctement configurée et être connectées à des périphériques fonctionne.</span><span class="sxs-lookup"><span data-stu-id="290bb-110">To ensure that users are able to use the Skype Room Systems v2 units, the units must be on, connected to the network with the Skype Room Systems v2 application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="290bb-111">Plus d’informations sur l’état de l’application v2 de Skype salle systèmes et périphériques connectés sont écrits par l’application v2 de systèmes de salle Skype pour le journal des événements Windows et expliquées dans [comprendre les entrées du journal](azure-monitor.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="290bb-111">Information about the state of the Skype Room Systems v2 application and connected peripheral devices is written by the Skype Room Systems v2 application to the Windows event log and documented in [Understand the log entries](azure-monitor.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="290bb-112">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="290bb-112">**Setting**</span></span>|<span data-ttu-id="290bb-113">**Permet de**</span><span class="sxs-lookup"><span data-stu-id="290bb-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="290bb-114">HKLM\Software\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="290bb-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="290bb-115">V2 de systèmes de salle Skype permet de démarrer</span><span class="sxs-lookup"><span data-stu-id="290bb-115">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="290bb-116">Gestion - de l’alimentation\> sur CA, désactiver écran au bout de 10 minutes</span><span class="sxs-lookup"><span data-stu-id="290bb-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="290bb-117">Gestion - de l’alimentation\> sur CA, placez jamais système en mode veille</span><span class="sxs-lookup"><span data-stu-id="290bb-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="290bb-118">Permet de systèmes de salle Skype v2 activer affiche attaché et réactiver automatiquement</span><span class="sxs-lookup"><span data-stu-id="290bb-118">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="290bb-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="290bb-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="290bb-120">Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local.</span><span class="sxs-lookup"><span data-stu-id="290bb-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="290bb-121">Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="290bb-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="290bb-122">Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.</span><span class="sxs-lookup"><span data-stu-id="290bb-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="290bb-123">Active le compte Skype avec lequel toujours se connecter</span><span class="sxs-lookup"><span data-stu-id="290bb-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="290bb-124">Transfert de fichiers à l’aide de stratégies de groupe est traitée dans [un élément de fichier de configuration](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="290bb-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="290bb-125">Gestion distante à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="290bb-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="290bb-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="290bb-126"></span></span>


<span data-ttu-id="290bb-127">Nous recommandons d’utiliser Microsoft Operations Manager Suite à surveiller vos systèmes de v2 Skype salle.</span><span class="sxs-lookup"><span data-stu-id="290bb-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Skype Room Systems v2 systems.</span></span> <span data-ttu-id="290bb-128">Pour obtenir des instructions sur la configuration de surveillance et les alertes de base, voir [déployer Skype salle v2 SMS avec Azure moniteur](../../deploy/deploy-clients/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="290bb-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Skype Room Systems v2 management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md).</span></span> 

<span data-ttu-id="290bb-129">À l’aide de ce guide, vous pouvez créer un tableau de bord simple à utiliser pour identifier des problèmes avec des unités v2 de vos systèmes de salle Skype dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="290bb-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Skype Room Systems v2 units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="290bb-130">Points de décision</span><span class="sxs-lookup"><span data-stu-id="290bb-130">Decision points</span></span>|<ul><li><span data-ttu-id="290bb-131">Vérifiez que vous allez utiliser la Suite de gestion des opérations de déploiement de v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="290bb-131">Confirm that you'll use Operations Management Suite to monitor your Skype Room Systems v2 deployment.</span></span></li><li><span data-ttu-id="290bb-132">Décider de la liste de distribution cible que vous allez utiliser pour les alertes par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="290bb-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="290bb-133">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="290bb-133">Next steps</span></span>|<ul><li><span data-ttu-id="290bb-134">Définir votre qualité et la fiabilité approche de surveillance.</span><span class="sxs-lookup"><span data-stu-id="290bb-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="290bb-135">Qualité et la fiabilité de la surveillance (CQD)</span><span class="sxs-lookup"><span data-stu-id="290bb-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="290bb-136">Nous vous recommandons d’implémenter qualité opérationnelle en cours et la fiabilité de la surveillance des procédures dans le cadre de votre déploiement pour surveiller les tendances d’appel et de qualité de la réunion et de fiabilité, qui identifie les zones d’intérêt et utilisation d’une résolution.</span><span class="sxs-lookup"><span data-stu-id="290bb-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="290bb-137">Lorsque vous téléchargez vos informations de construction dans CQD vous pouvez examiner les tendances qualité et la fiabilité d’appel sur un niveau par construction, ce qui facilite la comparaison de bâtiments et concentrer votre attention sur des problèmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="290bb-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="290bb-138">Pour plus d’informations, téléchargez le [Moniteur-CQD pour Skype pour Business remise en ligne et le Guide des opérations](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="290bb-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="290bb-139">Nous vous recommandons de consulter et suivre le [Guide Quality of Experience passez en revue](https://aka.ms/qerguide) pour identifier les tendances de qualité et la fiabilité et créer un plan d’action pour les résoudre.</span><span class="sxs-lookup"><span data-stu-id="290bb-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a><span data-ttu-id="290bb-140">Mise à jour de l’application du système d’exploitation et systèmes de salle Skype de v2 Skype salle systèmes</span><span class="sxs-lookup"><span data-stu-id="290bb-140">Updating the Skype Room Systems v2 OS and Skype Room Systems application</span></span> 

<span data-ttu-id="290bb-141">Il est recommandé que vous mettez à jour Skype salle systèmes v2 OS Skype salle systèmes v2 à l’application et tirent parti des améliorations et des mises à jour de produit.</span><span class="sxs-lookup"><span data-stu-id="290bb-141">We recommend that you update the Skype Room Systems v2 OS and Skype Room Systems v2 application to benefit from product updates and improvements.</span></span> <span data-ttu-id="290bb-142">Pour obtenir des instructions détaillées, voir [Gérer les systèmes de salle Skype v2](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="290bb-142">For detailed guidance, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="290bb-143">Mises à jour Windows</span><span class="sxs-lookup"><span data-stu-id="290bb-143">Windows Updates</span></span>

<span data-ttu-id="290bb-144">Système de salle Skype v2 (SRS v2) s’exécute sur Windows 10 entreprise IoT ou entreprise de 10 Windows (VL) et reçoit les même versions mises à jour Windows et du système d’exploitation de bureau standard.</span><span class="sxs-lookup"><span data-stu-id="290bb-144">Skype Room System v2 (SRS v2) runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="290bb-145">Pour plus d’informations, voir [Gérer les mises à jour de Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="290bb-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="290bb-146">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="290bb-146">Troubleshooting</span></span>

<span data-ttu-id="290bb-147">Nous vous recommandons de configurer Suite de gestion des opérations d’alerte comme décrit dans la section ci-dessus afin que votre équipe chargée des opérations et le support technique seront informés de tous les systèmes de salle Skype v2 problèmes.</span><span class="sxs-lookup"><span data-stu-id="290bb-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Skype Room Systems v2 issues.</span></span> <span data-ttu-id="290bb-148">Les options dont vous disposez pour la gestion à distance PowerShell sont décrits dans la [gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="290bb-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="290bb-149">Dans le cas où un périphérique est déconnecté, vous devrez peut-être s’appuient sur locales mains « actives » ou la prise en charge de l’informatique d’analyser et reconnectez les périphériques.</span><span class="sxs-lookup"><span data-stu-id="290bb-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="290bb-150">Pour plus d’informations sur le mode de résolution des problèmes et d’administration, voir [Gérer les systèmes de salle Skype v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="290bb-150">For more information about troubleshooting and admin mode, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="290bb-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="290bb-151">See also</span></span>

[<span data-ttu-id="290bb-152">Systèmes de salle Skype version 2</span><span class="sxs-lookup"><span data-stu-id="290bb-152">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="290bb-153">Planification de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="290bb-153">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="290bb-154">Déploiement des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="290bb-154">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="290bb-155">Configuration d’une console pour les systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="290bb-155">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="290bb-156">Gestion à distance des paramètres d'une console Skype Room Systems v2 à l'aide d'un fichier de configuration XML</span><span class="sxs-lookup"><span data-stu-id="290bb-156">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
