---
title: Résolution des problèmes de votre déploiement Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Dépannez votre déploiement de Cloud Connector Edition.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359330"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="13555-103">Résolution des problèmes de votre déploiement Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="13555-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="13555-104">La version Cloud Connector sera déconnectée le 31 juillet 2021 avec Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="13555-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="13555-105">Une fois que votre organisation a effectué la mise à niveau vers Teams, Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="13555-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="13555-106">Dépannez votre déploiement de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="13555-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="13555-107">Cette rubrique décrit les solutions aux problèmes courants liés aux déploiements de Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="13555-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="13555-108">Si vous rencontrez des problèmes avec les appels vers et à partir du réseau téléphonique commuté (RTC), vous pouvez examiner les solutions décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="13555-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="13555-109">Cloud Connector fournit des mécanismes intégrés permettant de résoudre automatiquement certains problèmes.</span><span class="sxs-lookup"><span data-stu-id="13555-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="13555-110">Un processus de détection automatique recherche les problèmes potentiels liés aux appareils Cloud Connector et, dans la mesure du possible, prend des mesures correctives pour résoudre ces problèmes sans intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="13555-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="13555-111">Le processus de détection fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="13555-112">**Séquence de détection :** Le service de gestion de Cloud Connector exécute un processus toutes les 60 secondes pour détecter si une appliance est en panne.</span><span class="sxs-lookup"><span data-stu-id="13555-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="13555-113">Dans la version 2,0 de Cloud Connector et les versions ultérieures, le processus de détection utilise le commutateur de gestion des appels Skype entreprise pour établir des connexions PowerShell aux machines Cloud Connector ; pour les versions antérieures à 2,0, le processus de détection utilise le commutateur de gestion Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="13555-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13555-114">Pour que la récupération automatique réussisse, il doit y avoir une connectivité réseau entre l’hôte et les machines virtuelles sur le commutateur réseau de l’hôte.</span><span class="sxs-lookup"><span data-stu-id="13555-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="13555-115">Veillez à vérifier la connectivité réseau pour vous assurer que la détection et la récupération automatiques peuvent réussir.</span><span class="sxs-lookup"><span data-stu-id="13555-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="13555-116">**Surveillance :** Les services suivants sont surveillés dans Cloud Connector version 2,0 et versions ultérieures :</span><span class="sxs-lookup"><span data-stu-id="13555-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="13555-117">Les machines virtuelles ne sont pas connectées aux commutateurs virtuels d’entreprise ou Internet de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="13555-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="13555-118">Les machines virtuelles sont dans un état enregistré ou arrêté</span><span class="sxs-lookup"><span data-stu-id="13555-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="13555-119">Services de serveur de gestion centralisée : RÉPLICA, maître</span><span class="sxs-lookup"><span data-stu-id="13555-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="13555-120">Services de serveur de médiation : RÉPLICA, RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="13555-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="13555-121">Services serveur Edge : RÉPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="13555-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="13555-122">Les règles de pare-feu entrant sont désactivées pour le RTCSRV de CS sur le serveur Edge, CS RTCMEDSRV sur le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="13555-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="13555-123">Dans la version 1.4.2 de Cloud Connector, seuls les services suivants sont surveillés :</span><span class="sxs-lookup"><span data-stu-id="13555-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="13555-124">Services de serveur de médiation : RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="13555-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="13555-125">Service serveur Edge : RTCSRV</span><span class="sxs-lookup"><span data-stu-id="13555-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="13555-126">**Processus de récupération :** Si des services surveillés sont en panne, une appliance est marquée comme étant inactive et les services sont arrêtés et corrigés manuellement jusqu’à ce que tous les problèmes puissent être résolus.</span><span class="sxs-lookup"><span data-stu-id="13555-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="13555-127">Cela empêchera les appels de routage vers une appliance susceptible de provoquer des échecs d’appel.</span><span class="sxs-lookup"><span data-stu-id="13555-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="13555-128">Le service de gestion Cloud Connector relance la récupération automatique comme suit</span><span class="sxs-lookup"><span data-stu-id="13555-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="13555-129">L’intervalle de nouvelle tentative initiale est de dix secondes, avec un intervalle maximal d’une heure.</span><span class="sxs-lookup"><span data-stu-id="13555-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="13555-130">Pour les trois premières tentatives de récupération, la durée de l’intervalle est de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="13555-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="13555-131">À partir de la quatrième nouvelle tentative, le temps de l’intervalle augmente de deux fois l’intervalle de temps précédent.</span><span class="sxs-lookup"><span data-stu-id="13555-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="13555-132">Par exemple, la quatrième tentative se produira dans 20 secondes, la cinquième en 40 secondes, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="13555-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="13555-133">Lorsque l’intervalle maximal d’une heure est atteint, les tentatives se poursuivent une fois par heure.</span><span class="sxs-lookup"><span data-stu-id="13555-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="13555-134">Lorsque la récupération réussit, l’intervalle et le nombre de nouvelles tentatives sont définis sur leurs valeurs initiales.</span><span class="sxs-lookup"><span data-stu-id="13555-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="13555-135">Si le service de gestion est redémarré, l’intervalle et le nombre de nouvelles tentatives sont réinitialisés à leurs valeurs initiales.</span><span class="sxs-lookup"><span data-stu-id="13555-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="13555-136">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="13555-136">Troubleshooting</span></span>

<span data-ttu-id="13555-137">Voici des solutions aux problèmes rencontrés couramment :</span><span class="sxs-lookup"><span data-stu-id="13555-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="13555-138">**Problème : le déploiement échoue ou cesse de répondre lors de l’exécution des scripts de déploiement. Après l’ouverture de session sur chaque machine virtuelle, l’adresse IP est manquante ou incorrecte pour la carte d’interface réseau (NIC) de gestion/interne/externe.**</span><span class="sxs-lookup"><span data-stu-id="13555-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="13555-139">**Résolution :** Ce problème ne peut pas être résolu automatiquement.</span><span class="sxs-lookup"><span data-stu-id="13555-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="13555-140">Les cartes réseau ne peuvent pas être ajoutées aux machines virtuelles lorsqu’elles sont en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="13555-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="13555-141">Veuillez arrêter et supprimer ces machines virtuelles dans le Gestionnaire Hyper-v, puis exécutez les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="13555-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="13555-142">**Problème : après l’installation du serveur et de la forêt Active Directory, le serveur CMS et/ou le serveur de médiation n’ont pas correctement rejoint le domaine.**</span><span class="sxs-lookup"><span data-stu-id="13555-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="13555-143">**Résolution :** Pour résoudre ce problème, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="13555-144">Ouvrez une session sur le serveur Active Directory et vérifiez que le domaine a été correctement créé.</span><span class="sxs-lookup"><span data-stu-id="13555-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="13555-145">Ouvrez une session sur le serveur CMS/médiation et vérifiez que sur la carte d’entreprise (corpnet) une adresse IP valide est attribuée, et que l’adresse IP et le DNS statiques valides sont configurés en tant qu’adresse IP du serveur AD.</span><span class="sxs-lookup"><span data-stu-id="13555-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="13555-146">Ouvrez une session sur le serveur CMS/médiation, puis ouvrez une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="13555-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="13555-147">Assurez-vous que vous pouvez exécuter la commande ping sur le nom de domaine complet et l’adresse IP du serveur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="13555-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="13555-148">Si ce n’est pas le cas, il peut y avoir un conflit d’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="13555-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="13555-149">Essayez d’affecter une nouvelle adresse IP pour Active Directory et mettez à jour DNS sur le serveur CMS/médiation en conséquence.</span><span class="sxs-lookup"><span data-stu-id="13555-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="13555-150">**Problème : vous recevez le message d’erreur suivant : «Remove-VMSwitch : failed lors de la suppression du commutateur Ethernet virtuel. Le commutateur virtuel’Cloud Connector Management switch’ne peut pas être supprimé, car il est utilisé par des ordinateurs virtuels en cours d’exécution ou attribué à des pools enfants. "**</span><span class="sxs-lookup"><span data-stu-id="13555-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="13555-151">**Résolution :** Le « commutateur de gestion de Cloud Connector » n’a pas été supprimé après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="13555-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="13555-152">Si vous avez rencontré cette erreur, reportez-vous au Gestionnaire Hyper-v et vérifiez qu’il n’y a pas encore de machine virtuelle connectée.</span><span class="sxs-lookup"><span data-stu-id="13555-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="13555-153">Si des machines virtuelles sont toujours connectées, déconnectez-les et supprimez le commutateur de gestion.</span><span class="sxs-lookup"><span data-stu-id="13555-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="13555-154">Si le commutateur de gestion ne peut toujours pas être supprimé, redémarrez le serveur hôte et réessayez.</span><span class="sxs-lookup"><span data-stu-id="13555-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="13555-155">**Problème : vous recevez le message d’erreur suivant : «le service RTCMRAUTH n’a pas pu démarrer. Vérifiez que le service n’est pas désactivé. "**</span><span class="sxs-lookup"><span data-stu-id="13555-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13555-156">Ce problème concerne uniquement les versions de Cloud Connector antérieures à la version 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="13555-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="13555-157">L’échec de démarrage peut également être dû au fait que ce serveur frontal était précédemment basculé (avec basculement de l’ordinateur).</span><span class="sxs-lookup"><span data-stu-id="13555-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="13555-158">Si c’est le cas, appelez la restauration automatique (à l’aide de la restauration automatique de l’ordinateur).</span><span class="sxs-lookup"><span data-stu-id="13555-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="13555-159">**Résolution :** Ce problème se produit sur un serveur Edge lorsque le certificat de l’autorité de certification racine ou le certificat de l’autorité de certification intermédiaire n’est pas approuvé par le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="13555-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="13555-160">Même si le certificat externe peut être importé, mais que la chaîne de certificats est rompue.</span><span class="sxs-lookup"><span data-stu-id="13555-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="13555-161">Dans cette condition, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="13555-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="13555-162">Importez manuellement le certificat de l’AC racine et tous les certificats de l’autorité de certification intermédiaire de votre certificat externe dans le serveur Edge, puis redémarrez le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="13555-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="13555-163">Après avoir vu les services RTCMRAUTH et RTCSRV démarrés sur le serveur Edge, revenez à votre serveur hôte, lancez une console PowerShell en tant qu’administrateur et exécutez l’applet de commande suivante pour basculer vers le nouveau déploiement :</span><span class="sxs-lookup"><span data-stu-id="13555-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="13555-164">**Problème : le serveur hôte a redémarré lorsque des mises à jour Windows ont été appliquées et les appels service par le serveur échouent.**</span><span class="sxs-lookup"><span data-stu-id="13555-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="13555-165">**Résolution :** Si vous avez déployé un environnement de haute disponibilité, Microsoft fournit une cmdlet pour vous aider à déplacer un ordinateur hôte (instance de déploiement) à l’intérieur ou à l’extérieur de la topologie actuelle lors de la vérification et de l’installation manuelle de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="13555-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="13555-166">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="13555-167">Sur le serveur hôte, démarrez une console PowerShell en tant qu’administrateur, puis exécutez :</span><span class="sxs-lookup"><span data-stu-id="13555-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="13555-168">Recherchez les mises à jour et installez celles qui sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="13555-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="13555-169">Dans la console PowerShell, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="13555-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="13555-170">**Problème : lorsqu’un appel est effectué à partir d’un client Skype entreprise à l’aide d’un numéro RTC, l’appel ne peut pas être remonté vers une conférence en invitant un autre numéro RTC.**</span><span class="sxs-lookup"><span data-stu-id="13555-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="13555-171">**Résolution :** Pour résoudre ce problème, reportez-vous à la rubrique [configure Online Hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="13555-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="13555-172">**Problème : un message d’avertissement s’affiche à propos de Windows Update lors de l’installation d’Active Directory Server : «la mise à jour automatique de Windows n’est pas activée. Pour vous assurer que votre rôle ou votre fonctionnalité nouvellement installée est automatiquement mis à jour, activez Windows Update. "**</span><span class="sxs-lookup"><span data-stu-id="13555-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="13555-173">**Résolution :** Lancez une session PowerShell à distance du client à l’aide des informations d’identification de l’administrateur client de Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier la configuration de _EnableAutoUpdate_ de votre site :</span><span class="sxs-lookup"><span data-stu-id="13555-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="13555-174">Si  _EnableAutoUpdate_ a la valeur **true**, vous pouvez ignorer ce message d’avertissement en toute sécurité, car le service CCEManagement gère le téléchargement et l’installation des mises à jour Windows pour les machines virtuelles et le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="13555-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="13555-175">Si  _EnableAutoUpdate_ a la valeur **false**, exécutez la cmdlet suivante pour lui affecter la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="13555-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="13555-176">Vous pouvez également vérifier et installer manuellement les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="13555-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="13555-177">Voir la section suivante.</span><span class="sxs-lookup"><span data-stu-id="13555-177">See the next section.</span></span>
    
- <span data-ttu-id="13555-178">**Problème : vous recevez un message d’erreur : impossible d’enregistrer l’appliance, car votre entrée/configuration actuelle ou ou, ou \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> ou \<Mediation Server IP Address\> en conflit avec une ou plusieurs Appliances existantes. Supprimez l’appliance Conflict ou mettez à jour vos informations d’entrée/configuration, puis réinscrivez-vous. 'lors de l’exécution de Register-applet ccappliance pour inscrire l’appliance actuelle sur Online.**</span><span class="sxs-lookup"><span data-stu-id="13555-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="13555-179">**Résolution :** Les valeurs pour \<ApplianceName\> le \<Mediation Server FQDN\> et \<Mediation Server IP Address\> doivent être uniques et utilisées uniquement pour l’enregistrement d’une appliance.</span><span class="sxs-lookup"><span data-stu-id="13555-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="13555-180">Par défaut, \<ApplianceName\> provient du nom d’hôte.</span><span class="sxs-lookup"><span data-stu-id="13555-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="13555-181">\<Mediation Server FQDN\> et \<Mediation Server IP Address\> défini dans le fichier ini de configuration.</span><span class="sxs-lookup"><span data-stu-id="13555-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="13555-182">Par exemple, l’utilisation de (Appliance = MyserverNew, nom de domaine complet du serveur de médiation = ms. contoso. com, adresse IP du serveur de médiation = 10.10.10.10) pour s’enregistrer sur SiteName = monsite, mais s’il existe un équipement enregistré (Appliance = monserveur, nom de domaine complet du serveur de médiation = ms. contoso. com, adresse IP du serveur de médiation)</span><span class="sxs-lookup"><span data-stu-id="13555-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="13555-183">Tout d’abord, vérifiez votre fichier CloudConnector.ini dans la section Directory ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="13555-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="13555-184">Vous obtiendrez \<SiteName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> les valeurs et dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="13555-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="13555-185">\<ApplianceName\> est le nom de votre serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="13555-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="13555-186">Deuxièmement, lancez le client distant PowerShell à l’aide de vos informations d’identification d’administrateur client Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier les appliances inscrites.</span><span class="sxs-lookup"><span data-stu-id="13555-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="13555-187">Après avoir identifié les conflits, vous pouvez soit mettre à jour votre fichier CloudConnector.ini avec les informations correspondant à l’appliance enregistrée, soit annuler l’inscription de l’appliance existante pour résoudre les conflits.</span><span class="sxs-lookup"><span data-stu-id="13555-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="13555-188">**Problème : l’applet de commande Get-applet ccrunningversion ne renvoie une valeur vide si une appliance déployée est en cours d’exécution sur l’hôte.**</span><span class="sxs-lookup"><span data-stu-id="13555-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="13555-189">**Résolution :** Cela peut se produire lorsque vous effectuez une mise à niveau depuis version 1.3.4 ou 1.3.8 vers 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="13555-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="13555-190">Après avoir installé la version 1.4.1 avec le. msi, vous devez exécuter `Register-CcAppliance` avant d’exécuter toute autre cmdlet.</span><span class="sxs-lookup"><span data-stu-id="13555-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="13555-191">`Register-CcAppliance` migre le fichier module.ini de%UserProfile%\CloudConnector vers%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="13555-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="13555-192">Si vous l’avez manqué, un nouveau module.ini sera créé dans le dossier%ProgramData%\CloudConnector et remplacera les informations de version en cours d’exécution/sauvegarde pour version 1.3.4 ou 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="13555-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="13555-193">Comparez les fichiers module.ini dans le dossier%UserProfile%\CloudConnector et%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="13555-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="13555-194">S’il existe des différences, supprimez le fichier module.ini dans%ProgramData%\CloudConnector et réexécutez  `Register-CcAppliance` .</span><span class="sxs-lookup"><span data-stu-id="13555-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="13555-195">Vous pouvez également modifier manuellement le fichier vers la version d’exécution et de sauvegarde correcte.</span><span class="sxs-lookup"><span data-stu-id="13555-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="13555-196">**Problème : après avoir exécuté la cmdlet Switch-CcVersion pour basculer vers une ancienne version différente de la version du script actuelle, il n’existe pas de prise en charge de la haute disponibilité pour cette ancienne version.**</span><span class="sxs-lookup"><span data-stu-id="13555-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="13555-197">**Résolution :** Par exemple, vous avez effectué une mise à niveau de 1.4.1 vers 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="13555-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="13555-198">Votre version de script actuelle, qui peut être déterminée en exécutant `Get-CcVersion` , et votre version en cours d’exécution, qui peut être déterminée en exécutant  `Get-CcRunningVersion` sont les deux 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="13555-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="13555-199">Pour l’instant, si vous exécutez `Switch-CcVersion` pour rebasculer la version en cours d’exécution vers la version 1.4.1, il n’y aura pas de prise en charge de la haute disponibilité pour cette ancienne version.</span><span class="sxs-lookup"><span data-stu-id="13555-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="13555-200">Pour obtenir une prise en charge complète de la haute disponibilité, revenez à la version 1.4.2, de sorte que la version en cours d’exécution et la version de script sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="13555-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="13555-201">Si vous rencontrez des problèmes avec votre déploiement 1.4.2, veuillez le désinstaller et le réinstaller dès que possible.</span><span class="sxs-lookup"><span data-stu-id="13555-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="13555-202">**Problème : les certificats de l’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**</span><span class="sxs-lookup"><span data-stu-id="13555-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="13555-203">**Résolution :** Les certificats de l’autorité de certification Skype entreprise sont valides pendant cinq ans.</span><span class="sxs-lookup"><span data-stu-id="13555-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="13555-204">Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans.</span><span class="sxs-lookup"><span data-stu-id="13555-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13555-205">Dans la version 2,0 de Cloud Connector et les versions ultérieures, la cmdlet Renew-CcServerCertificate a été remplacée par Update-CcServerCertificate et la cmdlet Renew-applet cccacertificate a été remplacée par Update-applet cccacertificate.</span><span class="sxs-lookup"><span data-stu-id="13555-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="13555-206">Si les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis, exécutez l’applet de commande Renew-CcServerCertificate ou Update-CcServerCertificate pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="13555-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="13555-207">Si les certificats de l’autorité de certification sont à proximité de l’expiration, exécutez l’applet de commande Renew-applet cccacertificate ou Update-applet cccacertificate pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="13555-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="13555-208">**Si les certificats de l’autorité de certification sont compromis et qu’il n’y a qu’une seule Appliance dans le site,** procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="13555-209">Exécutez la cmdlet Enter-applet ccupdate pour drainer les services et placer l’appliance en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="13555-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="13555-210">Exécutez les applets de commande suivantes pour réinitialiser et créer les nouveaux certificats de l’autorité de certification et tous les certificats de serveur interne :</span><span class="sxs-lookup"><span data-stu-id="13555-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="13555-211">Pour les versions de Cloud Connector antérieures à 2,0 :</span><span class="sxs-lookup"><span data-stu-id="13555-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="13555-212">Ou pour Cloud Connector version 2,0 et versions ultérieures :</span><span class="sxs-lookup"><span data-stu-id="13555-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="13555-213">Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de commande Export-applet ccrootcertificate à partir de l’appliance, puis installez le certificat exporté sur vos passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="13555-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="13555-214">Vous devrez peut-être également relancer le certificat sur votre passerelle.</span><span class="sxs-lookup"><span data-stu-id="13555-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="13555-215">Exécutez la cmdlet Exit-applet ccupdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="13555-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="13555-216">**Si les certificats de l’autorité de certification sont compromis et qu’il y a plusieurs Appliances dans le site,** effectuez les étapes séquentielles suivantes sur chaque appliance du site.</span><span class="sxs-lookup"><span data-stu-id="13555-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="13555-217">Microsoft vous recommande d’effectuer ces étapes en dehors des heures de pointe.</span><span class="sxs-lookup"><span data-stu-id="13555-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="13555-218">Sur la première appliance, exécutez la cmdlet Remove-applet cccertificationauthorityfile pour nettoyer les fichiers de sauvegarde de l’autorité de certification dans le \<SiteRoot\> répertoire.</span><span class="sxs-lookup"><span data-stu-id="13555-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="13555-219">Exécutez la cmdlet Enter-applet ccupdate pour purger les services et placez chaque appliance en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="13555-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="13555-220">Sur la première appliance, exécutez les applets de commande suivantes pour réinitialiser et créer de nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :</span><span class="sxs-lookup"><span data-stu-id="13555-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="13555-221">Pour les versions de Cloud Connector antérieures à 2,0 :</span><span class="sxs-lookup"><span data-stu-id="13555-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="13555-222">Ou pour Cloud Connector version 2,0 et versions ultérieures :</span><span class="sxs-lookup"><span data-stu-id="13555-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="13555-223">Sur la première appliance, exécutez l’applet de commande suivante pour sauvegarder les fichiers de l’autorité de certification dans le \<SiteRoot\> dossier.</span><span class="sxs-lookup"><span data-stu-id="13555-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="13555-224">Sur toutes les autres Appliances du même site, exécutez les commandes suivantes pour consommer les fichiers de sauvegarde de l’autorité de certification, afin que les applications utilisent le même certificat racine, puis demandez de nouveaux certificats.</span><span class="sxs-lookup"><span data-stu-id="13555-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="13555-225">Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de commande Export-applet ccrootcertificate à partir de n’importe quelle Appliance dans le site, puis installez le certificat exporté sur vos passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="13555-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="13555-226">Vous devrez peut-être également relancer le certificat sur votre passerelle.</span><span class="sxs-lookup"><span data-stu-id="13555-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="13555-227">Exécutez la cmdlet Exit-applet ccupdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="13555-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="13555-228">**Problème : vous recevez le message d’erreur suivant dans le journal du service de gestion de Cloud Connector, « C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log » : CceService Error : 0 : exception inattendue lors de la création de rapports sur en ligne : System. Management. Automation. CmdletInvocationException : échec de l’ouverture de session pour l’utilisateur \<Global Tenant Admin\> . Créez un objet d’informations d’identification, en vous assurant que vous avez utilisé le nom d’utilisateur et le mot de passe corrects. ---\>**</span><span class="sxs-lookup"><span data-stu-id="13555-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="13555-229">**Résolution :** Les informations d’identification d’administrateur client global Microsoft 365 ou Office 365 ont été modifiées depuis l’inscription de l’appliance Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="13555-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="13555-230">Pour mettre à jour les informations d’identification stockées localement sur le matériel de Cloud Connector, exécutez la commande suivante à partir d’administration PowerShell sur l’appliance hôte :</span><span class="sxs-lookup"><span data-stu-id="13555-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="13555-231">**Problème : une fois que vous avez modifié le mot de passe pour le compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : Key non valide pour une utilisation dans l’état spécifié. » dans%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de la cmdlet Get-applet cccredential.**</span><span class="sxs-lookup"><span data-stu-id="13555-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="13555-232">**Résolution :** Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML».</span><span class="sxs-lookup"><span data-stu-id="13555-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="13555-233">Lorsque le mot de passe sur le serveur hôte est modifié, vous devez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="13555-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="13555-234">**Si vous exécutez la version 1.4.2 de Cloud Connector,** regénérez tous les mots de passe Cloud Connector en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="13555-235">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="13555-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="13555-236">Supprimez le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML».</span><span class="sxs-lookup"><span data-stu-id="13555-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="13555-237">Lancez une console PowerShell en tant qu’administrateur, puis exécutez la commande « Register-applet ccappliance-local » pour entrer de nouveau les mots de passe à la suite de la description.</span><span class="sxs-lookup"><span data-stu-id="13555-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="13555-238">Entrez les mêmes mots de passe que ceux que vous avez entrés pour le déploiement de Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="13555-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="13555-239">**Si vous exécutez la version 2,0 de Cloud Connector ou une version ultérieure,** regénérez tous les mots de passe Cloud Connector en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="13555-240">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="13555-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="13555-241">Supprimez le fichier suivant : "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . XML».</span><span class="sxs-lookup"><span data-stu-id="13555-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="13555-242">Lancez une console PowerShell en tant qu’administrateur, puis exécutez la commande « Register-applet ccappliance-local » pour entrer de nouveau les mots de passe à la suite de la description.</span><span class="sxs-lookup"><span data-stu-id="13555-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="13555-243">Si le fichier de mot de passe mis en cache a été généré avec la version 1.4.2 de Cloud Connector, utilisez le mot de passe VMAdmin pour le mot de passe CceService lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="13555-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="13555-244">Entrez le mot de passe que vous avez entré avant le déploiement de Cloud Connector pour tous les autres comptes.</span><span class="sxs-lookup"><span data-stu-id="13555-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="13555-245">Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 1.4.2 et que les mots de passe DomainAdmin et VMAdmin sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="13555-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="13555-246">Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="13555-247">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="13555-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="13555-248">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé précédemment.</span><span class="sxs-lookup"><span data-stu-id="13555-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="13555-249">Si le fichier de mot de passe mis en cache a été généré avec la version 2,0 ou ultérieure de Cloud Connector, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="13555-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="13555-250">Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="13555-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="13555-251">Exécutez Set-applet cccredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="13555-252">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="13555-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="13555-253">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé précédemment.</span><span class="sxs-lookup"><span data-stu-id="13555-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="13555-254">Exécutez Set-applet cccredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="13555-255">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="13555-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="13555-256">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin que vous avez utilisé précédemment.</span><span class="sxs-lookup"><span data-stu-id="13555-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="13555-257">**Problème : avec Cloud Connector version 2,1 et versions ultérieures, lors de l’exécution de la commande Register-applet ccappliance ou d’autres cmdlets sur l’appliance, vous recevez un message d’erreur de type : « for each-Object : la propriété «Common » est introuvable sur cet objet. Vérifiez que la propriété existe. Sur C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char : 14 "**</span><span class="sxs-lookup"><span data-stu-id="13555-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="13555-258">**Résolution :** Cloud Connector 2,1 et versions ultérieures nécessite .NET Framework 4.6.1 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="13555-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="13555-259">Mettez à jour .NET Framework sur l’appliance vers la version 4.6.1 ou ultérieure et réexécutez l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="13555-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="13555-260">**Problème : avec la version Cloud Connector 2,1, lors de l’exécution de install-applet ccappliance, vous recevez un message d’erreur tel que : « échec de l’installation de la nouvelle instance avec l’erreur : impossible de définir «état » car seules les chaînes peuvent être utilisées comme valeurs pour définir les propriétés XmlNode»**</span><span class="sxs-lookup"><span data-stu-id="13555-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="13555-261">**Résolution :** Dans Cloudconnector.ini, dans la section [Common], ajoutez le fichier « State » config comme suit : CountryCode = USA state = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="13555-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="13555-262">Il n’est pas obligatoire que la ligne « État » ait la valeur, mais la ligne « État » ne peut pas être supprimée du fichier Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="13555-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="13555-263">**Problème : vous recevez le message d’erreur suivant : «Dismount-WindowsImage : Dismount-WindowsImage a échoué. Code d’erreur = 0xc1550115 "lors de l’installation ou de la mise à niveau de la version Cloud Connector.**</span><span class="sxs-lookup"><span data-stu-id="13555-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="13555-264">**Résolution :** Lancez une console PowerShell en tant qu’administrateur, exécutez « DISM-Cleanup-Wim ».</span><span class="sxs-lookup"><span data-stu-id="13555-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="13555-265">Cette opération nettoie toutes les images ayant rencontré un problème.</span><span class="sxs-lookup"><span data-stu-id="13555-265">This will clean up all troubled images.</span></span> <span data-ttu-id="13555-266">Exécutez à nouveau install-applet ccappliance ou attendez que la mise à niveau de bits soit automatique.</span><span class="sxs-lookup"><span data-stu-id="13555-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="13555-267">**Problème : le déploiement de la première Appliance Cloud Connector dans un environnement haute disponibilité échoue.**</span><span class="sxs-lookup"><span data-stu-id="13555-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="13555-268">**Résolution :** Les étapes que vous effectuez dépendent de la raison pour laquelle le déploiement a échoué :</span><span class="sxs-lookup"><span data-stu-id="13555-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="13555-269">Si la première Appliance Cloud Connector échoue et que vous ne parvenez pas à déterminer la raison de l’échec, vous devez réinstaller l’appliance jusqu’à ce que le déploiement réussisse, puis installer les autres appliances.</span><span class="sxs-lookup"><span data-stu-id="13555-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="13555-270">Si la première Appliance Cloud Connector échoue avec un problème mineur, tel qu’un problème de certificat externe, vous pourrez peut-être résoudre le problème sans réinstaller l’appliance.</span><span class="sxs-lookup"><span data-stu-id="13555-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="13555-271">Vous pouvez ensuite utiliser PowerShell à distance du client pour marquer le déploiement comme étant réussi, comme suit.</span><span class="sxs-lookup"><span data-stu-id="13555-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="13555-272">(Vous pouvez également utiliser les étapes suivantes si le premier déploiement a réussi, mais, pour une raison quelconque, Cloud Connector ne parvient pas à signaler le déploiement en tant que réussite.)</span><span class="sxs-lookup"><span data-stu-id="13555-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="13555-273">Pour obtenir l’identité (GUID) de la première Appliance Cloud Connector, exécutez la cmdlet Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="13555-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="13555-274">Pour marquer l’appliance comme ayant été déployée avec succès, exécutez la CsCceApplianceDeploymentStatus comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="13555-275">**Problème : vous devez vérifier et installer les mises à jour de Windows manuellement sur le serveur hôte ou les machines virtuelles.**</span><span class="sxs-lookup"><span data-stu-id="13555-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="13555-276">**Résolution :** Nous vous recommandons de tirer parti des mises à jour automatisées du système d’exploitation fournies par Skype entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="13555-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="13555-277">Une fois qu’une appliance est inscrite pour la gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifieront et installeront automatiquement les mises à jour de Windows conformément aux paramètres de la fenêtre de mise à jour du système d’exploitation</span><span class="sxs-lookup"><span data-stu-id="13555-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="13555-278">Si vous devez vérifier et installer les mises à jour de Windows manuellement, suivez les étapes de cette section qui s’appliquent à votre type de déploiement.</span><span class="sxs-lookup"><span data-stu-id="13555-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="13555-279">Vous devez planifier la mise à jour simultanée du serveur hôte et des machines virtuelles qu’il exécute, afin de minimiser le temps nécessaire pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="13555-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="13555-280">Si vous préférez, vous pouvez utiliser un serveur Windows Server Update Services (WSUS) pour fournir des mises à jour aux serveurs Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="13555-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="13555-281">N’oubliez pas de configurer la mise à jour Windows pour qu’elle **ne soit pas** installée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="13555-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="13555-282">Pour plus d’informations sur la mise à jour manuelle de votre déploiement de Cloud Connector, reportez-vous à la section suivante.</span><span class="sxs-lookup"><span data-stu-id="13555-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="13555-283">**Problème : lorsque Cloud Connector est mis à jour vers une nouvelle version, les cmdlets de Cloud Connector ne sont pas mises à jour.**</span><span class="sxs-lookup"><span data-stu-id="13555-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="13555-284">Cela se produit parfois si une fenêtre PowerShell est laissée ouverte lorsque des mises à jour automatiques se produisent.</span><span class="sxs-lookup"><span data-stu-id="13555-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="13555-285">**Résolution :** Pour charger les applets de commande mises à jour, vous pouvez effectuer l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="13555-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="13555-286">Fermez PowerShell sur le matériel Cloud Connector, puis rouvrez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="13555-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="13555-287">Sinon, vous pouvez exécuter import-module CloudConnector-force.</span><span class="sxs-lookup"><span data-stu-id="13555-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="13555-288">**Problème : « le terme «Stop-CsWindowsService » n’est pas reconnu comme le nom d’une cmdlet, d’une fonction, d’un fichier de script ou d’un programme exécutable». erreur lors de la tentative d’exécution de la cmdlet Enter-applet ccupdate.**</span><span class="sxs-lookup"><span data-stu-id="13555-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="13555-289">**Résolution :** Supprimez le $HOME fichier \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="13555-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="13555-290">PowerShell crée ce fichier sous la forme d’un cache d’applets de commande à partir de modules qu’il trouve afin qu’il n’ait pas à analyser à chaque fois tous les modules, car cela entraînerait un ralentissement des opérations.</span><span class="sxs-lookup"><span data-stu-id="13555-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="13555-291">Il y a probablement eu une altération des fichiers qui fournissait des résultats trompeurs lors de la lecture de ce cache.</span><span class="sxs-lookup"><span data-stu-id="13555-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="13555-292">**Problème : "import-module CloudConnector" génère une erreur "Import-Module : le module spécifié" CloudConnector "n’a pas été chargé, car aucun fichier de module valide n’a été trouvé dans un répertoire de module"**</span><span class="sxs-lookup"><span data-stu-id="13555-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="13555-293">**Résolution :**</span><span class="sxs-lookup"><span data-stu-id="13555-293">**Resolution:**</span></span>
    - <span data-ttu-id="13555-294">Vérifiez que le module CloudConnector existe effectivement sous c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="13555-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="13555-295">Après avoir validé que le module CloudConnector existe sous cet emplacement, la variable d’environnement PSModulePath stockant le chemin d’accès aux emplacements des modules peut être modifiée :</span><span class="sxs-lookup"><span data-stu-id="13555-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="13555-296">a.</span><span class="sxs-lookup"><span data-stu-id="13555-296">a.</span></span> <span data-ttu-id="13555-297">Modification temporaire : démarrez PowerShell en tant qu’administrateur et exécutez la commande suivante : $env :P SModulePath = $env :P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="13555-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="13555-298">b.</span><span class="sxs-lookup"><span data-stu-id="13555-298">b.</span></span> <span data-ttu-id="13555-299">Pour les modifications permanentes, démarrez PowerShell en tant qu’administrateur et exécutez les commandes suivantes, une par une : $CurrentValue = [Environment] :: GetEnvironmentVariable ("PSModulePath", "machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," machine ")</span><span class="sxs-lookup"><span data-stu-id="13555-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="13555-300">Installer les mises à jour de Windows manuellement</span><span class="sxs-lookup"><span data-stu-id="13555-300">Install Windows updates manually</span></span>

<span data-ttu-id="13555-301">Si vous ne souhaitez pas utiliser les mises à jour automatiques dans votre environnement, procédez comme suit pour vérifier et appliquer manuellement les mises à jour de Windows.</span><span class="sxs-lookup"><span data-stu-id="13555-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="13555-302">La vérification et l’installation des mises à jour Windows peuvent nécessiter un redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="13555-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="13555-303">Lorsqu’un serveur hôte redémarre, les utilisateurs ne peuvent pas utiliser Cloud Connector pour passer ou recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="13555-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="13555-304">Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler le moment où les mises à jour ont lieu, puis redémarrer les ordinateurs selon vos besoins pendant les périodes où vous choisissez d’éviter toute interruption des services.</span><span class="sxs-lookup"><span data-stu-id="13555-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="13555-305">Pour vérifier manuellement les mises à jour, connectez-vous à chaque serveur hôte et ouvrez le **panneau de configuration**.</span><span class="sxs-lookup"><span data-stu-id="13555-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="13555-306">Sélectionnez **système et sécurité \> Windows Update**, puis gérez les mises à jour et les redémarrages du serveur en fonction de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="13555-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="13555-307">S’il n’y a qu’une seule Appliance dans le site, connectez-vous à chaque machine virtuelle et ouvrez le **panneau de configuration**.</span><span class="sxs-lookup"><span data-stu-id="13555-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="13555-308">Sélectionnez **système et sécurité \> Windows Update**, puis configurez les mises à jour et les redémarrages du serveur, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="13555-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="13555-309">S’il y a plusieurs Appliances dans le site, l’instance en cours de mise à jour et de redémarrage n’est pas accessible par les utilisateurs pendant les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="13555-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="13555-310">Les utilisateurs se connecteront à d’autres instances dans le déploiement jusqu’à ce que toutes les machines virtuelles et tous les services Skype entreprise démarrent sur les machines virtuelles une fois les mises à jour terminées.</span><span class="sxs-lookup"><span data-stu-id="13555-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="13555-311">Pour éviter toute interruption potentielle du service, vous pouvez supprimer l’instance de la haute disponibilité lors de l’application des mises à jour, puis la restaurer lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="13555-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="13555-312">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="13555-312">To do so:</span></span>
    
1. <span data-ttu-id="13555-313">Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="13555-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="13555-314">Supprimez l’instance de la haute disponibilité à l’aide de l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="13555-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="13555-315">Suivez les étapes d’une instance unique pour appliquer manuellement les mises à jour et redémarrer l’ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="13555-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="13555-316">Redéfinissez l’instance sur HA avec l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="13555-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="13555-317">Pour les déploiements multisites, suivez les étapes d’un site unique pour chaque site du déploiement, en appliquant les mises à jour à un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="13555-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="13555-318">Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="13555-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="13555-319">Si vous devez installer un logiciel antivirus sur l’ordinateur hôte de Cloud Connector, vous devez ajouter les exclusions suivantes :</span><span class="sxs-lookup"><span data-stu-id="13555-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="13555-320">Répertoire d’appliance local sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="13555-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="13555-321">Annuaire de sites distants sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="13555-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="13555-322">L’annuaire de sites local sur l’ordinateur héberge le dossier racine du site partagé.</span><span class="sxs-lookup"><span data-stu-id="13555-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="13555-323">%ProgramFiles%\Skype pour Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="13555-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="13555-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="13555-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="13555-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="13555-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="13555-326">Le processus Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="13555-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
