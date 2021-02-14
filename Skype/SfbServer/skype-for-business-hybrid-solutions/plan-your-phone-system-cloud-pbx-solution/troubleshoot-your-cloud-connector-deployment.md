---
title: Résolution des problèmes liés à votre déploiement de Cloud Connector
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
description: Résolution des problèmes de déploiement de la version Cloud Connector.
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359330"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="f400c-103">Résolution des problèmes liés à votre déploiement de Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="f400c-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="f400c-104">Cloud Connector Edition sera retirer le 31 juillet 2021 avec Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="f400c-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="f400c-105">Une fois votre organisation mise à niveau vers Teams, découvrez comment connecter votre réseau téléphonique local à Teams à l’aide du [routage direct.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="f400c-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="f400c-106">Résolution des problèmes de déploiement de la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f400c-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="f400c-107">Cette rubrique décrit les solutions aux problèmes courants avec les déploiements de la version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f400c-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="f400c-108">Si vous rencontrez des problèmes avec les appels vers et depuis le réseau téléphonique commuté (PSTN), vous pouvez examiner les solutions décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="f400c-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="f400c-109">Cloud Connector fournit des mécanismes intégrés pour résoudre automatiquement certains problèmes.</span><span class="sxs-lookup"><span data-stu-id="f400c-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="f400c-110">Un processus de détection automatique recherche les problèmes potentiels avec les appliances Cloud Connector et, si possible, prend des mesures correctives pour résoudre ces problèmes sans intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f400c-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="f400c-111">Le processus de détection fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="f400c-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="f400c-112">**Séquence de détection :** Le service de gestion Cloud Connector exécute un processus toutes les 60 secondes pour détecter si une appliance est en panne.</span><span class="sxs-lookup"><span data-stu-id="f400c-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="f400c-113">Dans Cloud Connector version 2.0 et versions ultérieures, le processus de détection utilise le commutateur Corpnet Skype Entreprise pour établir des connexions PowerShell aux ordinateurs Cloud Connector ; Pour les versions antérieures à la version 2.0, le processus de détection utilise le commutateur de gestion Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f400c-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f400c-114">Pour que la récupération automatique réussisse, il doit y avoir une connectivité réseau entre l’hôte et les machines virtuelles sur le commutateur réseau hôte.</span><span class="sxs-lookup"><span data-stu-id="f400c-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="f400c-115">Veillez à vérifier la connectivité réseau pour vous assurer que la détection et la récupération automatiques peuvent réussir.</span><span class="sxs-lookup"><span data-stu-id="f400c-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="f400c-116">**Surveillance :** Les services suivants sont surveillés dans Cloud Connector version 2.0 et ultérieures :</span><span class="sxs-lookup"><span data-stu-id="f400c-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="f400c-117">Les machines virtuelles ne sont pas connectées aux commutateurs virtuels d’entreprise ou Internet Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="f400c-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="f400c-118">Les machines virtuelles sont dans un état enregistré ou arrêté</span><span class="sxs-lookup"><span data-stu-id="f400c-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="f400c-119">Services serveur de gestion centralisée : REPLICA, MASTER</span><span class="sxs-lookup"><span data-stu-id="f400c-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="f400c-120">Services de serveur de médiation : REPLICA, RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="f400c-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="f400c-121">Services de serveur Edge : REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="f400c-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="f400c-122">Les règles de pare-feu entrant sont désactivées pour CS RTCSRV sur le serveur Edge, CS RTCMEDSRV sur le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f400c-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="f400c-123">Dans Cloud Connector version 1.4.2, seuls les services suivants sont surveillés :</span><span class="sxs-lookup"><span data-stu-id="f400c-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="f400c-124">Services de serveur de médiation : RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="f400c-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="f400c-125">Service serveur Edge : RTCSRV</span><span class="sxs-lookup"><span data-stu-id="f400c-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="f400c-126">**Processus de récupération :** Si des services surveillés sont arrêtés, une appliance est marquée et les services sont arrêtés et marqués manuellement jusqu’à ce que tous les problèmes soient résolus.</span><span class="sxs-lookup"><span data-stu-id="f400c-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="f400c-127">Cela empêche le routage des appels vers une appliance qui peut entraîner des défaillances d’appel.</span><span class="sxs-lookup"><span data-stu-id="f400c-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="f400c-128">Le service de gestion Cloud Connector va réessayer la récupération automatique comme suit:</span><span class="sxs-lookup"><span data-stu-id="f400c-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="f400c-129">L’intervalle de nouvelle tentative initial est toutes les dix secondes avec une durée d’intervalle maximale d’une heure.</span><span class="sxs-lookup"><span data-stu-id="f400c-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="f400c-130">Pour les trois premières tentatives de récupération, l’intervalle est de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="f400c-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="f400c-131">À partir de la quatrième tentative, l’intervalle augmente de deux fois l’intervalle précédent.</span><span class="sxs-lookup"><span data-stu-id="f400c-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="f400c-132">Par exemple, la quatrième nouvelle tentative aura lieu dans 20 secondes, la cinquième en 40 secondes, etc.</span><span class="sxs-lookup"><span data-stu-id="f400c-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="f400c-133">Lorsque l’intervalle maximal d’une heure est atteint, les tentatives se poursuivent une fois par heure.</span><span class="sxs-lookup"><span data-stu-id="f400c-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="f400c-134">Lorsque la récupération réussit, le nombre d’intervalles et de tentatives est fixé à leurs valeurs initiales.</span><span class="sxs-lookup"><span data-stu-id="f400c-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="f400c-135">Si le service de gestion est redémarré, le nombre d’intervalles et de tentatives est réinitialisé à leurs valeurs initiales.</span><span class="sxs-lookup"><span data-stu-id="f400c-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="f400c-136">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="f400c-136">Troubleshooting</span></span>

<span data-ttu-id="f400c-137">Voici des solutions aux problèmes couramment rencontrés :</span><span class="sxs-lookup"><span data-stu-id="f400c-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="f400c-138">**Problème : le déploiement échoue ou cesse de répondre lors de l’exécution des scripts de déploiement. Après la connexion à chaque VM, l’adresse IP est manquante ou incorrecte pour la NIC gestion/interne/externe.**</span><span class="sxs-lookup"><span data-stu-id="f400c-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="f400c-139">**Résolution :** Ce problème ne peut pas être résolu automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f400c-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="f400c-140">Les CCI ne peuvent pas être ajoutées aux ordinateurs VM pendant leur exécution.</span><span class="sxs-lookup"><span data-stu-id="f400c-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="f400c-141">Veuillez arrêter et supprimer ces VM dans le gestionnaire hyper-v, puis exécutez les cmdlets suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="f400c-142">**Problème : une fois le serveur Active Directory et la forêt installés, le serveur CMS et/ou le serveur de médiation n’ont pas correctement rejoint le domaine.**</span><span class="sxs-lookup"><span data-stu-id="f400c-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="f400c-143">**Résolution :** Pour résoudre ce problème, prenez les mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="f400c-144">Connectez-vous au serveur Active Directory et vérifiez que le domaine a été créé correctement.</span><span class="sxs-lookup"><span data-stu-id="f400c-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="f400c-145">Connectez-vous au serveur CMS/de médiation et vérifiez qu’une adresse IP valide est attribuée à la carte réseau du réseau d’entreprise et que l’adresse IP statique et le DNS valides sont configurés en tant qu’adresse IP du serveur AD.</span><span class="sxs-lookup"><span data-stu-id="f400c-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="f400c-146">Connectez-vous au serveur CMS/de médiation et ouvrez une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="f400c-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="f400c-147">Assurez-vous que vous pouvez effectuer un test ping sur le nom deqdn et l’adresse IP du serveur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f400c-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="f400c-148">Si vous ne le pouvez pas, il peut y avoir un conflit d’adresses IP.</span><span class="sxs-lookup"><span data-stu-id="f400c-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="f400c-149">Essayez d’affecter une nouvelle adresse IP pour Active Directory et mettez à jour le DNS sur le serveur CMS/médiation en conséquence.</span><span class="sxs-lookup"><span data-stu-id="f400c-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="f400c-150">**Problème : vous recevez le message d’erreur suivant, « Remove-VMSwitch : Échec lors de la suppression du commutateur Ethernet virtuel. Le commutateur virtuel « Cloud Connector Management Switch » ne peut pas être supprimé, car il est utilisé par des machines virtuelles ou affecté à des pools enfants. »**</span><span class="sxs-lookup"><span data-stu-id="f400c-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="f400c-151">**Résolution :** Le « commutateur de gestion Cloud Connector » n’a pas été supprimé après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="f400c-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="f400c-152">Si vous avez atteint cette erreur, consultez le gestionnaire Hyper-v et vérifiez qu’aucune machine virtuelle ne s’y connecte encore.</span><span class="sxs-lookup"><span data-stu-id="f400c-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="f400c-153">Si des machines virtuelles sont toujours connectées, déconnectez-les et supprimez le commutateur de gestion.</span><span class="sxs-lookup"><span data-stu-id="f400c-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="f400c-154">Si le commutateur de gestion ne peut toujours pas être supprimé, redémarrez le serveur hôte et réessayez.</span><span class="sxs-lookup"><span data-stu-id="f400c-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="f400c-155">**Problème : vous recevez le message d’erreur suivant, « Le démarrage du service RTCMRAUTH a échoué. Vérifiez que le service n’est pas désactivé. »**</span><span class="sxs-lookup"><span data-stu-id="f400c-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f400c-156">Ce problème s’applique uniquement aux versions cloud connector antérieures à la version 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f400c-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="f400c-157">L’échec du démarrage peut également être dû au fait que ce serveur frontal a été précédemment échoué (à l’aide d’un ordinateur qui a échoué).</span><span class="sxs-lookup"><span data-stu-id="f400c-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="f400c-158">Si c’est le cas, veuillez appeler la panne (à l’aide de la panne d’ordinateur).</span><span class="sxs-lookup"><span data-stu-id="f400c-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="f400c-159">**Résolution :** Ce problème se produit sur un serveur Edge lorsque le certificat d’ac racine ou le certificat d’ac intermédiaire n’est pas approuvé par le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="f400c-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="f400c-160">Même si le certificat externe peut être importé mais que la chaîne de certificats est rompue.</span><span class="sxs-lookup"><span data-stu-id="f400c-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="f400c-161">Dans cette condition, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="f400c-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="f400c-162">Importez manuellement le certificat d’ac racine et tous les certificats d’ac intermédiaire de votre certificat externe dans le serveur Edge, puis redémarrez le serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="f400c-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="f400c-163">Une fois que les services RTCMRAUTH et RTCSRV ont démarré sur le serveur Edge, revenir à votre serveur hôte, lancez une console PowerShell en tant qu’administrateur et exécutez l’cmdlet suivante pour basculer vers le nouveau déploiement :</span><span class="sxs-lookup"><span data-stu-id="f400c-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="f400c-164">**Problème : le serveur hôte a été redémarré lorsque des mises à jour Windows ont été appliquées et que les appels du serveur échouent.**</span><span class="sxs-lookup"><span data-stu-id="f400c-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="f400c-165">**Résolution :** Si vous avez déployé un environnement de haute disponibilité, Microsoft fournit une cmdlet pour vous aider à déplacer un ordinateur hôte (instance de déploiement) vers ou hors de la topologie actuelle lorsque vous vérifiez et installez manuellement la mise à jour de Windows.</span><span class="sxs-lookup"><span data-stu-id="f400c-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="f400c-166">Pour ce faire, utilisez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="f400c-167">Sur le serveur hôte, démarrez une console PowerShell en tant qu’administrateur, puis exécutez :</span><span class="sxs-lookup"><span data-stu-id="f400c-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="f400c-168">Recherchez les mises à jour et installez les mises à jour disponibles.</span><span class="sxs-lookup"><span data-stu-id="f400c-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="f400c-169">Dans la console PowerShell, exécutez l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="f400c-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="f400c-170">**Problème : lorsqu’un appel est effectué à partir d’un client Skype Entreprise à l’aide d’un numéro PSTN, l’appel ne peut pas être recalcalé à une conférence en invitant un autre numéro PSTN.**</span><span class="sxs-lookup"><span data-stu-id="f400c-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="f400c-171">**Résolution :** Pour résoudre ce problème, voir Configurer les paramètres du serveur [de médiation hybride en ligne.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)</span><span class="sxs-lookup"><span data-stu-id="f400c-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="f400c-172">**Problème : un message d’avertissement s’affiche à propos de Windows Update lorsque vous installez le serveur Active Directory : « La mise à jour automatique de Windows n’est pas activée. Pour vous assurer que votre rôle ou fonctionnalité nouvellement installé est automatiquement mis à jour, activer Windows Update. »**</span><span class="sxs-lookup"><span data-stu-id="f400c-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="f400c-173">**Résolution :** Lancez une session PowerShell client distante à l’aide des informations d’identification d’administrateur client Skype Entreprise, puis exécutez l’cmdlet suivante pour vérifier la configuration _EnableAutoUpdate_ de votre site :</span><span class="sxs-lookup"><span data-stu-id="f400c-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="f400c-174">Si  _EnableAutoUpdate_ est définie sur **True,** vous pouvez ignorer ce message d’avertissement en toute sécurité, car le service CCEManagement gère le téléchargement et l’installation des mises à jour Windows pour les machines virtuelles et le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="f400c-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="f400c-175">Si  _EnableAutoUpdate_ est définie sur **False**, exécutez l’cmdlet suivante pour la définir sur **True**.</span><span class="sxs-lookup"><span data-stu-id="f400c-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="f400c-176">Vous pouvez également vérifier et installer manuellement les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="f400c-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="f400c-177">Voir la section suivante.</span><span class="sxs-lookup"><span data-stu-id="f400c-177">See the next section.</span></span>
    
- <span data-ttu-id="f400c-178">**Problème : vous recevez un message d’erreur : impossible d’inscrire l’appliance car votre entrée/configuration actuelle ou ou est en conflit avec des \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> appliances existantes. Supprimez l’appliance conflictuelle ou mettez à jour vos informations d’entrée/configuration, puis inscrivez-vous à nouveau. ' when run Register-CcAppliance to register current appliance to online.**</span><span class="sxs-lookup"><span data-stu-id="f400c-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="f400c-179">**Résolution :** Valeurs pour le , et doit être unique et utilisé \<ApplianceName\> \<Mediation Server FQDN\> uniquement pour \<Mediation Server IP Address\> l’inscription d’une appliance.</span><span class="sxs-lookup"><span data-stu-id="f400c-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="f400c-180">Par défaut, \<ApplianceName\> provient du nom d’hôte.</span><span class="sxs-lookup"><span data-stu-id="f400c-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="f400c-181">\<Mediation Server FQDN\> et \<Mediation Server IP Address\> défini dans le fichier ini de configuration.</span><span class="sxs-lookup"><span data-stu-id="f400c-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="f400c-182">Par exemple, à l’aide de (ApplianceName= MyserverNew, FQDN du serveur de médiation=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span><span class="sxs-lookup"><span data-stu-id="f400c-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="f400c-183">Tout d’abord, vérifiez votre CloudConnector.ini dans la section répertoire ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="f400c-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="f400c-184">Vous obtenez \<SiteName\> et \<Mediation Server FQDN\> les \<Mediation Server IP Address\> valeurs dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="f400c-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="f400c-185">\<ApplianceName\> est le nom de votre serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="f400c-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="f400c-186">Ensuite, lancez l’application PowerShell à distance du client à l’aide de vos informations d’identification d’administrateur client Skype Entreprise, puis exécutez l’cmdlet suivante pour vérifier la ou les appliance(s) inscrite(s).</span><span class="sxs-lookup"><span data-stu-id="f400c-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="f400c-187">Après avoir identifié les conflits, vous pouvez mettre à jour votre fichier CloudConnector.ini avec les informations qui correspond à l’appliance inscrite, ou désinsister l’appliance existante pour résoudre les conflits.</span><span class="sxs-lookup"><span data-stu-id="f400c-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="f400c-188">**Problème : la cmdlet Get-CcRunningVersion renvoie une valeur vide si une appliance déployée est en cours d’exécution sur l’hôte.**</span><span class="sxs-lookup"><span data-stu-id="f400c-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="f400c-189">**Résolution :** Cela peut se produire lorsque vous faites une mise à niveau de la version 1.3.4 ou 1.3.8 vers la version 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="f400c-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="f400c-190">Après avoir installé la version 1.4.1 avec le .msi, vous devez l’exécuter avant d’exécuter une `Register-CcAppliance` autre cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f400c-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="f400c-191">`Register-CcAppliance` migrera le module.ini de %UserProfile%\CloudConnector vers %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="f400c-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="f400c-192">Si vous l’avez manqué, une nouvelle module.ini sera créée dans le dossier %ProgramData%\CloudConnector et remplacera les informations de version d’exécution/sauvegarde pour la version 1.3.4 ou 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="f400c-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="f400c-193">Comparez module.ini fichiers dans le dossier %UserProfile%\CloudConnector et %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="f400c-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="f400c-194">S’il existe des différences, supprimez le module.ini dans %ProgramData%\CloudConnector et  `Register-CcAppliance` réexécutez.</span><span class="sxs-lookup"><span data-stu-id="f400c-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="f400c-195">Vous pouvez également modifier le fichier manuellement pour qu’il soit correctement en cours d’exécution et en version de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="f400c-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="f400c-196">**Problème : après avoir exécuté l'Switch-CcVersion cmdlet pour basculer vers une ancienne version différente de la version actuelle du script, il n’existe aucune prise en charge de la haute disponibilité pour cette ancienne version.**</span><span class="sxs-lookup"><span data-stu-id="f400c-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="f400c-197">**Résolution :** Par exemple, vous avez mis à niveau la version 1.4.1 vers la version 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f400c-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="f400c-198">Votre version de script actuelle, qui peut être déterminée par l’exécution, et votre version en cours d’exécution, qui peut être déterminée par l’exécution sont les deux `Get-CcVersion`  `Get-CcRunningVersion` 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f400c-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="f400c-199">Pour l’instant, si vous exécutez pour revenir à la version en cours d’exécution vers la version 1.4.1, il n’y aura pas de prise en charge de la haute disponibilité pour cette `Switch-CcVersion` ancienne version.</span><span class="sxs-lookup"><span data-stu-id="f400c-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="f400c-200">Pour obtenir une prise en charge complète de la haute disponibilité, revenir à la version 1.4.2, afin que la version en cours d’exécution et la version de script soient identiques.</span><span class="sxs-lookup"><span data-stu-id="f400c-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="f400c-201">Si vous rencontrez des problèmes avec votre déploiement 1.4.2, désinstallez-le et réinstallez-le dès que possible.</span><span class="sxs-lookup"><span data-stu-id="f400c-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="f400c-202">**Problème : les certificats d’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**</span><span class="sxs-lookup"><span data-stu-id="f400c-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="f400c-203">**Résolution :** Les certificats de l’autorité de certification Skype Entreprise sont valides pendant cinq ans.</span><span class="sxs-lookup"><span data-stu-id="f400c-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="f400c-204">Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides pendant deux ans.</span><span class="sxs-lookup"><span data-stu-id="f400c-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f400c-205">Dans Cloud Connector version 2.0 et versions ultérieures, l’cmdlet Renew-CcServerCertificate est devenu Update-CcServerCertificate et la cmdlet Renew-CcCACertificate a été changée en Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="f400c-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="f400c-206">Si les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis, exécutez la cmdlet Renew-CcServerCertificate ou Update-CcServerCertificate pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="f400c-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="f400c-207">Si les certificats d’autorité de certification sont sur le point d’expirer, exécutez la cmdlet Renew-CcCACertificate ou Update-CcCACertificate pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="f400c-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="f400c-208">**Si les certificats de l’autorité** de certification sont compromis et qu’il n’existe qu’une seule appliance dans le site, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="f400c-209">Exécutez lEnter-CcUpdate cmdlet pour vider les services et mettre l’appliance en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="f400c-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="f400c-210">Exécutez les cmdlets suivantes pour réinitialiser et créer de nouveaux certificats d’autorité de certification et tous les certificats serveur internes :</span><span class="sxs-lookup"><span data-stu-id="f400c-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="f400c-211">Pour les publication de Cloud Connector avant la version 2.0 :</span><span class="sxs-lookup"><span data-stu-id="f400c-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="f400c-212">Ou pour cloud connector version 2.0 et ultérieure :</span><span class="sxs-lookup"><span data-stu-id="f400c-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="f400c-213">Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez la cmdlet Export-CcRootCertificate à partir de l’appliance, puis installez le certificat exporté sur vos passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="f400c-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="f400c-214">Vous pouvez également être tenu de ré-émettre le certificat sur votre passerelle.</span><span class="sxs-lookup"><span data-stu-id="f400c-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="f400c-215">Exécutez l'Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="f400c-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="f400c-216">**Si les certificats de** l’autorité de certification sont compromis et qu’il existe plusieurs appliances dans le site, effectuez les étapes séquentielles suivantes sur chaque appliance du site.</span><span class="sxs-lookup"><span data-stu-id="f400c-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="f400c-217">Microsoft vous recommande d’effectuer ces étapes pendant les périodes d’utilisation normales.</span><span class="sxs-lookup"><span data-stu-id="f400c-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="f400c-218">Sur la première appliance, exécutez la cmdlet Remove-CcCertificationAuthorityFile pour nettoyer les fichiers de sauvegarde de l’autorité de contrôle d’accès dans \<SiteRoot\> l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="f400c-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="f400c-219">Exécutez l'Enter-CcUpdate pour vider les services et mettre chaque appliance en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="f400c-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="f400c-220">Sur la première appliance, exécutez les cmdlets suivantes pour réinitialiser et créer de nouveaux certificats d’autorité de certification et tous les certificats serveur internes :</span><span class="sxs-lookup"><span data-stu-id="f400c-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="f400c-221">Pour les publication de Cloud Connector avant la version 2.0 :</span><span class="sxs-lookup"><span data-stu-id="f400c-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="f400c-222">Ou pour cloud connector version 2.0 et ultérieure :</span><span class="sxs-lookup"><span data-stu-id="f400c-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="f400c-223">Sur la première appliance, exécutez l’cmdlet suivante pour back up the CA files to the \<SiteRoot\> folder.</span><span class="sxs-lookup"><span data-stu-id="f400c-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="f400c-224">Sur toutes les autres appliances du même site, exécutez les commandes suivantes pour consommer les fichiers de sauvegarde de l’ac, afin que les appliances utilisent toutes le même certificat racine, puis demandent de nouveaux certificats.</span><span class="sxs-lookup"><span data-stu-id="f400c-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="f400c-225">Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez la cmdlet Export-CcRootCertificate à partir de n’importe quelle appliance du site, puis installez le certificat exporté sur vos passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="f400c-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="f400c-226">Vous pouvez également être obligé de ré-émettre le certificat sur votre passerelle.</span><span class="sxs-lookup"><span data-stu-id="f400c-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="f400c-227">Exécutez l'Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="f400c-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="f400c-228">**Problème : vous recevez le message d’erreur suivant dans le journal du service de gestion Cloud Connector, « C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log » : Erreur CceService : 0 : Exception inattendue lors du signalement de l’état en ligne : System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\> . Veuillez créer un objet d’informations d’identification, en vous assurez que vous avez utilisé le nom d’utilisateur et le mot de passe corrects. ---\>**</span><span class="sxs-lookup"><span data-stu-id="f400c-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="f400c-229">**Résolution :** Les informations d’identification de l’administrateur client général Microsoft 365 ou Office 365 ont été modifiées depuis l’inscription de l’appliance Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f400c-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="f400c-230">Pour mettre à jour les informations d’identification stockées localement sur l’appliance Cloud Connector, exécutez ce qui suit à partir de l’administrateur PowerShell sur l’appliance hôte :</span><span class="sxs-lookup"><span data-stu-id="f400c-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="f400c-231">**Problème : après avoir changé le mot de passe du compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : clé non valide pour une utilisation dans l’état spécifié . » dans %ProgramFiles%\Skype For Business Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de l’cmdlet Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="f400c-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="f400c-232">**Résolution :** Toutes les informations d’identification Cloud Connector sont stockées dans le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml ».</span><span class="sxs-lookup"><span data-stu-id="f400c-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="f400c-233">Lorsque le mot de passe du serveur hôte change, vous devez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="f400c-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="f400c-234">**Si vous exécutez Cloud Connector version 1.4.2,** régénérez tous les mots de passe Cloud Connector en suivant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="f400c-235">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="f400c-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="f400c-236">Supprimez le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml ».</span><span class="sxs-lookup"><span data-stu-id="f400c-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="f400c-237">Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance -Local » pour entrer de nouveau les mots de passe suivant la description.</span><span class="sxs-lookup"><span data-stu-id="f400c-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="f400c-238">Entrez les mêmes mots de passe que vous avez entrés auparavant pour le déploiement Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f400c-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="f400c-239">**Si vous exécutez Cloud Connector version 2.0** ou ultérieure, régénérez tous les mots de passe Cloud Connector en suivant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="f400c-240">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="f400c-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="f400c-241">Supprimez le fichier suivant : « %SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml " .</span><span class="sxs-lookup"><span data-stu-id="f400c-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="f400c-242">Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance -Local » pour entrer de nouveau les mots de passe suivant la description.</span><span class="sxs-lookup"><span data-stu-id="f400c-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="f400c-243">Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 1.4.2, utilisez le mot de passe VMAdmin pour le mot de passe CceService lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="f400c-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="f400c-244">Entrez le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector pour tous les autres comptes.</span><span class="sxs-lookup"><span data-stu-id="f400c-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="f400c-245">Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 1.4.2 et que les mots de passe DomainAdmin et VMAdmin sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="f400c-246">Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="f400c-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="f400c-247">Lorsque vous êtes invité à entrer les anciennes informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="f400c-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="f400c-248">Lorsque vous êtes invité à entrer les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="f400c-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="f400c-249">Si le fichier de mot de passe mis en cache a été généré avec Cloud Connector version 2.0 ou ultérieure, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="f400c-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="f400c-250">Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="f400c-251">Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="f400c-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="f400c-252">Lorsque vous êtes invité à entrer l’ancienne informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="f400c-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="f400c-253">Lorsque vous êtes invité à entrer les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="f400c-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="f400c-254">Exécutez Set-CcCredential -AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="f400c-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="f400c-255">Lorsque vous êtes invité à entrer l’ancienne informations d’identification du compte, entrez les informations d’identification que vous avez utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="f400c-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="f400c-256">Lorsque vous êtes invité à entrer les nouvelles informations d’identification du compte, entrez le mot de passe du mot de passe VmAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="f400c-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="f400c-257">**Problème : avec Cloud Connector version 2.1 et versions ultérieures, lorsque vous exécutez Register-CcAppliance ou d’autres cmdlets sur l’appliance, vous recevez un message d’erreur tel que : « Pour Each-Object : la propriété « Common » est in trouvée sur cet objet. Vérifiez que la propriété existe. À C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14 »**</span><span class="sxs-lookup"><span data-stu-id="f400c-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="f400c-258">**Résolution :** Cloud Connector 2.1 et les ultérieures nécessitent .NET Framework 4.6.1 ou une ultérieure.</span><span class="sxs-lookup"><span data-stu-id="f400c-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="f400c-259">Veuillez mettre à jour .NET Framework sur l’appliance vers la version 4.6.1 ou ultérieure et ré-exécuter les cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f400c-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="f400c-260">**Problème : avec Cloud Connector Edition 2.1, lorsque vous exécutez Install-CcAppliance, vous recevez un message d’erreur tel que : « Échec de l’installation d’une nouvelle instance avec erreur : impossible de définir « State », car seules les chaînes peuvent être utilisées comme valeurs pour définir les propriétés XmlNode »**</span><span class="sxs-lookup"><span data-stu-id="f400c-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="f400c-261">**Résolution :** In Cloudconnector.ini, under the [Common] section, please add the « State » config as below: CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="f400c-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="f400c-262">Il n’est pas obligatoire que la ligne « State » soit une valeur, mais la ligne « State » ne peut pas être supprimée du fichier Cloudconnector.ini'état.</span><span class="sxs-lookup"><span data-stu-id="f400c-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="f400c-263">**Problème : vous recevez le message d’erreur suivant « Démon-WindowsImage : Dismount-WindowsImage échoué. Code d’erreur = 0xc1550115 » lors de l’installation ou de la mise à niveau de l’édition Cloud Connector.**</span><span class="sxs-lookup"><span data-stu-id="f400c-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="f400c-264">**Résolution :** Lancez une console PowerShell en tant qu’administrateur, exécutez « DISM -Cleanup-Wim ».</span><span class="sxs-lookup"><span data-stu-id="f400c-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="f400c-265">Cette opération nettoie toutes les images en difficulté.</span><span class="sxs-lookup"><span data-stu-id="f400c-265">This will clean up all troubled images.</span></span> <span data-ttu-id="f400c-266">Exécutez Install-CcAppliance à nouveau ou attendez la mise à niveau automatique des bits.</span><span class="sxs-lookup"><span data-stu-id="f400c-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="f400c-267">**Problème : échec du déploiement de la première appliance Cloud Connector dans un environnement de haute haute sécurité**</span><span class="sxs-lookup"><span data-stu-id="f400c-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="f400c-268">**Résolution :** Les étapes à suivre dépendent de la raison de l’échec du déploiement :</span><span class="sxs-lookup"><span data-stu-id="f400c-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="f400c-269">Si la première appliance Cloud Connector échoue et que vous ne pouvez pas déterminer la raison de la défaillance, vous devez réinstaller l’appliance jusqu’à ce que le déploiement réussisse, puis installer les autres appliances.</span><span class="sxs-lookup"><span data-stu-id="f400c-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="f400c-270">Si la première appliance Cloud Connector échoue avec un problème mineur, tel qu’un problème de certificat externe, vous pourrez peut-être résoudre le problème sans réinstaller l’appliance.</span><span class="sxs-lookup"><span data-stu-id="f400c-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="f400c-271">Vous pouvez ensuite utiliser l’powerShell distant client pour marquer le déploiement comme réussi comme suit.</span><span class="sxs-lookup"><span data-stu-id="f400c-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="f400c-272">(Vous pouvez également suivre les étapes suivantes si le premier déploiement a réussi, mais, pour une raison quelconque, Cloud Connector ne parvient pas à signaler le déploiement comme un succès.)</span><span class="sxs-lookup"><span data-stu-id="f400c-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="f400c-273">Pour obtenir l’identité (GUID) de la première appliance Cloud Connector, exécutez Get-CsHybridPSTNAppliance cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f400c-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="f400c-274">Pour marquer l’appliance comme correctement déployée, exécutez le Set-CsCceApplianceDeploymentStatus comme suit :</span><span class="sxs-lookup"><span data-stu-id="f400c-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="f400c-275">**Problème : vous devez vérifier et installer manuellement les mises à jour Windows sur le serveur hôte ou les machines virtuelles.**</span><span class="sxs-lookup"><span data-stu-id="f400c-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="f400c-276">**Résolution :** Nous vous recommandons de tirer parti des mises à jour automatisées du système d’exploitation fournies par Skype Entreprise, version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f400c-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="f400c-277">Une fois qu’une appliance est inscrite pour la gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifient et installent automatiquement les mises à jour Windows en fonction des paramètres de la fenêtre de temps de mise à jour du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="f400c-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="f400c-278">Si vous devez vérifier et installer manuellement les mises à jour Windows, suivez les étapes de cette section qui s’appliquent à votre type de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f400c-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="f400c-279">Vous devez planifier la mise à jour du serveur hôte et des ordinateurs virtuels qui s’exécutent sur celui-ci en même temps afin de réduire le temps d’in panne nécessaire pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="f400c-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="f400c-280">Si vous préférez, vous pouvez utiliser un serveur Windows Server Update Services (WSUS) pour fournir des mises à jour aux serveurs Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="f400c-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="f400c-281">Assurez-vous simplement de configurer Windows Update pour qu’il **ne s’installe** pas automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f400c-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="f400c-282">Pour plus d’informations sur la mise à jour manuelle de votre déploiement Cloud Connector, consultez la section suivante.</span><span class="sxs-lookup"><span data-stu-id="f400c-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="f400c-283">**Problème : lorsque Cloud Connector est mis à jour vers une nouvelle build, les cmdlets Cloud Connector ne sont pas mises à jour.**</span><span class="sxs-lookup"><span data-stu-id="f400c-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="f400c-284">Cela se produit parfois si une fenêtre PowerShell reste ouverte lorsque la mise à jour automatique se produit.</span><span class="sxs-lookup"><span data-stu-id="f400c-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="f400c-285">**Résolution :** Pour charger les cmdlets mises à jour, vous pouvez suivre l’une des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="f400c-286">Fermez PowerShell sur l’appliance Cloud Connector, puis rouvrez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f400c-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="f400c-287">Sinon, vous pouvez exécuter Import-Module CloudConnector -Force.</span><span class="sxs-lookup"><span data-stu-id="f400c-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="f400c-288">**Problème : le terme « Stop-CsWindowsService » n’est pas reconnu comme nom d’une cmdlet, d’une fonction, d’un fichier de script ou d’un programme opérable. » erreur lors de la tentative d'Enter-CcUpdate cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="f400c-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="f400c-289">**Résolution :** Supprimez le $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.</span><span class="sxs-lookup"><span data-stu-id="f400c-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="f400c-290">PowerShell crée ce fichier en tant que cache d’cmdlets à partir de modules qu’il trouve afin qu’il n’a pas à analyser à nouveau tous les modules, car cela ralentissait les choses.</span><span class="sxs-lookup"><span data-stu-id="f400c-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="f400c-291">Il est fort probable qu’il y a eu une altération de fichier qui a fourni des résultats erronés à PowerShell lors de la lecture à partir de ce cache.</span><span class="sxs-lookup"><span data-stu-id="f400c-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="f400c-292">**Problème : « Import-Module CloudConnector » génère l’erreur « Import-Module : le module spécifié « CloudConnector » n’a pas été chargé car aucun fichier de module valide n’a été trouvé dans un répertoire de modules »**</span><span class="sxs-lookup"><span data-stu-id="f400c-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="f400c-293">**Résolution :**</span><span class="sxs-lookup"><span data-stu-id="f400c-293">**Resolution:**</span></span>
    - <span data-ttu-id="f400c-294">Vérifier que effectivement le module CloudConnector existe sous c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="f400c-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="f400c-295">Après avoir validé que le module CloudConnector existe sous cet emplacement, la variable d’environnement PSModulePath stockant le chemin d’accès aux emplacements des modules peut être modifiée :</span><span class="sxs-lookup"><span data-stu-id="f400c-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="f400c-296">a.</span><span class="sxs-lookup"><span data-stu-id="f400c-296">a.</span></span> <span data-ttu-id="f400c-297">Modification temporaire : démarrez Powershell en tant qu’administrateur et exécutez la commande suivante : $env:PSModulePath = $env:PSModulePath + « ; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="f400c-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="f400c-298">b.</span><span class="sxs-lookup"><span data-stu-id="f400c-298">b.</span></span> <span data-ttu-id="f400c-299">Pour les changements persistants, démarrez PowerShell en tant qu’administrateur et exécutez les commandes suivantes, une par une : $CurrentValue = [Environment]::GetEnvironmentVariable(« PSModulePath », « Machine ») SetEnvironmentVariable(« PSModulePath », $CurrentValue + « ; C:\Program Files\WindowsPowerShell\Modules », « Machine »)</span><span class="sxs-lookup"><span data-stu-id="f400c-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="f400c-300">Installer manuellement les mises à jour Windows</span><span class="sxs-lookup"><span data-stu-id="f400c-300">Install Windows updates manually</span></span>

<span data-ttu-id="f400c-301">Si vous ne souhaitez pas utiliser les mises à jour automatiques dans votre environnement, suivez ces étapes pour vérifier et appliquer manuellement les mises à jour Windows.</span><span class="sxs-lookup"><span data-stu-id="f400c-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="f400c-302">La vérification et l’installation des mises à jour Windows peuvent nécessiter un redémarrage du serveur.</span><span class="sxs-lookup"><span data-stu-id="f400c-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="f400c-303">Lorsqu’un serveur hôte redémarre, les utilisateurs ne peuvent pas utiliser Cloud Connector pour mettre en place ou recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="f400c-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="f400c-304">Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler le moment où elles ont lieu, puis redémarrer les ordinateurs selon vos besoins pendant les heures de votre choix afin d’éviter toute perturbation des services.</span><span class="sxs-lookup"><span data-stu-id="f400c-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="f400c-305">Pour vérifier manuellement les mises à jour, connectez-vous à chaque serveur hôte et ouvrez le **Panneau de contrôle.**</span><span class="sxs-lookup"><span data-stu-id="f400c-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="f400c-306">Sélectionnez **Système et sécurité Windows \> Update,** puis gérez les mises à jour et les redémarrages du serveur selon le cas pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="f400c-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="f400c-307">S’il n’existe qu’une seule appliance dans le site, connectez-vous à chaque machine virtuelle et ouvrez le **Panneau de contrôle.**</span><span class="sxs-lookup"><span data-stu-id="f400c-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="f400c-308">Sélectionnez **Système et sécurité Windows \> Update,** puis configurez les mises à jour et les redémarrages du serveur selon le cas.</span><span class="sxs-lookup"><span data-stu-id="f400c-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="f400c-309">S’il existe plusieurs équipements dans le site, l’instance mise à jour et redémarré n’est pas accessible aux utilisateurs pendant les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="f400c-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="f400c-310">Les utilisateurs se connectent à d’autres instances du déploiement jusqu’à ce que toutes les machines virtuelles et tous les services Skype Entreprise démarrent sur les ordinateurs virtuels une fois les mises à jour terminées.</span><span class="sxs-lookup"><span data-stu-id="f400c-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="f400c-311">Pour éviter toute perturbation potentielle du service, vous pouvez supprimer l’instance de la ha pendant que vous appliquez les mises à jour, puis la restaurer une fois terminée.</span><span class="sxs-lookup"><span data-stu-id="f400c-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="f400c-312">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f400c-312">To do so:</span></span>
    
1. <span data-ttu-id="f400c-313">Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f400c-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="f400c-314">Supprimez l’instance de la ha à l’aide de l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="f400c-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="f400c-315">Suivez les étapes d’une instance unique pour appliquer manuellement les mises à jour et redémarrer la machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="f400c-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="f400c-316">Définissez à nouveau l’instance sur HA avec l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="f400c-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="f400c-317">Pour les déploiements sur plusieurs sites, suivez les étapes d’un site unique pour chaque site du déploiement, en appliquant des mises à jour à un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="f400c-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="f400c-318">Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="f400c-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="f400c-319">Si vous devez installer un logiciel antivirus sur l’ordinateur hôte Cloud Connector, vous devez ajouter les exclusions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f400c-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="f400c-320">Répertoire Local Appliance sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f400c-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="f400c-321">Annuaire de sites distants sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f400c-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="f400c-322">L’annuaire de sites local sur l’ordinateur héberge le dossier racine du site partagé.</span><span class="sxs-lookup"><span data-stu-id="f400c-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="f400c-323">%ProgramFiles%\Skype For Business Cloud Connector Edition</span><span class="sxs-lookup"><span data-stu-id="f400c-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="f400c-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="f400c-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="f400c-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="f400c-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="f400c-326">Le processus est Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="f400c-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
