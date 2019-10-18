---
title: Présentation de la gestion des salles de Microsoft teams
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Présentation de la gestion des salles de Microsoft Teams.
ms.openlocfilehash: a55741fced90a62316ab8d046a91ee0364b314fd
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573560"
---
# <a name="management-overview"></a><span data-ttu-id="2fb26-103">Vue d’ensemble de la gestion</span><span class="sxs-lookup"><span data-stu-id="2fb26-103">Management overview</span></span>

<span data-ttu-id="2fb26-104">Il est essentiel de développer et d’exécuter les opérations de maintenance et d’exécution en continu pour vous assurer que vos systèmes de salle Microsoft teams sont disponibles pour vos utilisateurs et offrir ainsi une bonne utilisation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2fb26-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="2fb26-105">Surveillance</span><span class="sxs-lookup"><span data-stu-id="2fb26-105">Monitoring</span></span> 

<span data-ttu-id="2fb26-106">Le contrôle des systèmes de salle Microsoft teams comporte deux activités clés :</span><span class="sxs-lookup"><span data-stu-id="2fb26-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="2fb26-107">Surveillance de périphériques, d’applications et de périphériques</span><span class="sxs-lookup"><span data-stu-id="2fb26-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="2fb26-108">Surveillance de la qualité et de la fiabilité (bord)</span><span class="sxs-lookup"><span data-stu-id="2fb26-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="2fb26-109">Analyse du périphérique, de l’application et de l’appareil périphériques de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2fb26-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="2fb26-110">Pour garantir que les utilisateurs peuvent utiliser les unités de salles de Microsoft Teams, les unités doivent être activées, connectées au réseau avec l’application Microsoft teams de Microsoft correctement configurée et être connectées aux périphériques de fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="2fb26-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="2fb26-111">Les informations relatives à l’état de l’application Microsoft teams salles et aux périphériques connectés sont écrites par l’application Microsoft teams dans le journal des événements Windows et expliquées dans les [entrées du journal](azure-monitor-manage.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="2fb26-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="2fb26-112">**Paramètre**</span><span class="sxs-lookup"><span data-stu-id="2fb26-112">**Setting**</span></span>|<span data-ttu-id="2fb26-113">**Permet**</span><span class="sxs-lookup"><span data-stu-id="2fb26-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2fb26-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (DWORD) 1</span><span class="sxs-lookup"><span data-stu-id="2fb26-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="2fb26-115">Permet au démarrage de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2fb26-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="2fb26-116">Gestion de l'\> alimentation-sur le ca, éteindre l’écran après 10 minutes</span><span class="sxs-lookup"><span data-stu-id="2fb26-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="2fb26-117">Gestion de l'\> alimentation-sur le secteur, jamais mettre le système en veille</span><span class="sxs-lookup"><span data-stu-id="2fb26-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="2fb26-118">Activation de l’affichage et de la réactivation des salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2fb26-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="2fb26-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="2fb26-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="2fb26-120">Ou équivalent signifie la désactivation de l’expiration du mot de passe sur le compte local.</span><span class="sxs-lookup"><span data-stu-id="2fb26-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="2fb26-121">Si vous n’effectuez pas cette opération, le compte Skype ne parviendra pas à se connecter en signalant l’expiration d’un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="2fb26-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="2fb26-122">Note que ceci aura un impact sur tous les comptes locaux sur l’ordinateur, et par conséquent, cet échec entraînera aussi l’éventuelle expiration du compte administratif.</span><span class="sxs-lookup"><span data-stu-id="2fb26-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="2fb26-123">Active le compte Skype avec lequel toujours se connecter</span><span class="sxs-lookup"><span data-stu-id="2fb26-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="2fb26-124">Pour transférer des fichiers à l’aide de stratégies de groupe, voir [configurer un élément de fichier](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2fb26-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="2fb26-125">Gestion distante à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fb26-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="2fb26-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="2fb26-126"></span></span>

<span data-ttu-id="2fb26-127">Nous vous recommandons d’utiliser Microsoft Operations Manager suite pour surveiller vos systèmes de salle Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2fb26-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="2fb26-128">Pour obtenir des instructions sur la configuration de la surveillance et l’alerte de base, voir [déployer la gestion des salles de Microsoft teams avec Azure Monitor](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="2fb26-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="2fb26-129">Grâce à ces instructions, vous pouvez créer un tableau de bord simple à utiliser pour identifier les problèmes liés à l’utilisation de vos unités de salle Microsoft teams au sein de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="2fb26-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="2fb26-130">Points de décision</span><span class="sxs-lookup"><span data-stu-id="2fb26-130">Decision points</span></span>|<ul><li><span data-ttu-id="2fb26-131">Vérifiez que vous utilisez la suite de gestion des opérations pour surveiller votre déploiement de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2fb26-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="2fb26-132">Déterminez la liste de distribution cible à utiliser pour les alertes par e-mail.</span><span class="sxs-lookup"><span data-stu-id="2fb26-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="2fb26-133">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="2fb26-133">Next steps</span></span>|<ul><li><span data-ttu-id="2fb26-134">Définissez votre approche de qualité et de surveillance de la fiabilité.</span><span class="sxs-lookup"><span data-stu-id="2fb26-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="2fb26-135">Surveillance de la qualité et de la fiabilité (bord)</span><span class="sxs-lookup"><span data-stu-id="2fb26-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="2fb26-136">Nous vous conseillons d’implémenter les procédures de vérification de la qualité opérationnelle et de la fiabilité dans le cadre de votre déploiement pour contrôler la tendance des appels et de la qualité des réunions et de la fiabilité, en identifiant les zones de préoccupation et en vous efforçant de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="2fb26-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="2fb26-137">Lorsque vous chargez vos informations de bâtiment dans bord, vous pouvez examiner les tendances en matière de qualité d’appel et de fiabilité d’un niveau par niveau, ce qui permet de comparer facilement les bâtiments et de focaliser votre attention sur des problèmes spécifiques.</span><span class="sxs-lookup"><span data-stu-id="2fb26-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="2fb26-138">Nous vous recommandons de revoir et de suivre le Guide de la [qualité de l’utilisation](https://aka.ms/qerguide) pour identifier les tendances en matière de qualité et de fiabilité, et créer un plan d’action pour les résoudre.</span><span class="sxs-lookup"><span data-stu-id="2fb26-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="2fb26-139">Mise à jour du système d’exploitation Microsoft teams et de l’application Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2fb26-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="2fb26-140">Nous vous recommandons de mettre à jour l’application système d’exploitation de Microsoft teams et de Microsoft teams pour bénéficier des mises à jour et des améliorations du produit.</span><span class="sxs-lookup"><span data-stu-id="2fb26-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="2fb26-141">Pour obtenir une aide détaillée, voir [gérer les salles de Microsoft teams](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="2fb26-141">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="2fb26-142">Mises à jour Windows</span><span class="sxs-lookup"><span data-stu-id="2fb26-142">Windows Updates</span></span>

<span data-ttu-id="2fb26-143">Microsoft teams Room s’exécute sur Windows 10 entreprise IoT ou Windows 10 entreprise (VL) et reçoit les mêmes mises à jour Windows et les mêmes versions de système d’exploitation que le bureau standard.</span><span class="sxs-lookup"><span data-stu-id="2fb26-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="2fb26-144">Pour plus d’informations, voir [gérer les mises à jour Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="2fb26-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="2fb26-145">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="2fb26-145">Troubleshooting</span></span>

<span data-ttu-id="2fb26-146">Nous vous recommandons de configurer l’alerte de la suite de gestion des opérations comme décrit dans la section ci-dessus pour que votre équipe et votre support technique soient avertis de tout problème de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2fb26-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="2fb26-147">Les options qui s’offrent à vous pour la gestion à distance PowerShell sont décrites dans [gestion à distance à l’aide de PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="2fb26-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="2fb26-148">Dans le cas où un périphérique est déconnecté, vous devrez peut-être vous reposer sur des « mains actives » locales ou sur la prise en charge de l’examen et de la reconnexion des appareils.</span><span class="sxs-lookup"><span data-stu-id="2fb26-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="2fb26-149">Pour plus d’informations sur la résolution des problèmes et le mode administrateur, voir [gérer les salles de Microsoft teams](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="2fb26-149">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="2fb26-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2fb26-150">See also</span></span>

[<span data-ttu-id="2fb26-151">Aide Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="2fb26-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="2fb26-152">Plan pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2fb26-152">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="2fb26-153">Déploiement de salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2fb26-153">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="2fb26-154">Configurer une console de salle Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="2fb26-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="2fb26-155">Gérer les paramètres de la console salles de Microsoft teams à distance à l’aide d’un fichier de configuration XML</span><span class="sxs-lookup"><span data-stu-id="2fb26-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
