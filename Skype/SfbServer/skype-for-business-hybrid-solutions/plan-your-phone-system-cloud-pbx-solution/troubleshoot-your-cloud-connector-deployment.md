---
title: Identification et résolution des problèmes de votre déploiement Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Résoudre les problèmes de votre déploiement en nuage connecteur Edition.
ms.openlocfilehash: 2290d032f1461c37c31d138510388f17a52f5843
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838620"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="7f920-103">Identification et résolution des problèmes de votre déploiement Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="7f920-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="7f920-104">Résoudre les problèmes de votre déploiement en nuage connecteur Edition.</span><span class="sxs-lookup"><span data-stu-id="7f920-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="7f920-p101">Cette rubrique vous décrit les solutions aux problèmes courants liés au déploiement de la version Cloud Connector. Si vous rencontrez des problèmes liés aux appels vers ou sur la Réseau Téléphonique Commuté (RTC), vous pouvez tenter de les résoudre en suivant les solutions décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="7f920-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="7f920-107">Connecteur de cloud fournit des mécanismes intégrés pour la résolution des problèmes automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7f920-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="7f920-108">Un processus de détection automatique recherche les problèmes potentiels avec les appareils nuage connecteur et, prend la mesure du possible, les actions correctives pour résoudre les problèmes sans l’intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7f920-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="7f920-109">Le processus de détection fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f920-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="7f920-110">**Séquence de détection :** Le service de gestion du nuage connecteur s’exécute un processus toutes les 60 secondes pour détecter si un appareil est inactif.</span><span class="sxs-lookup"><span data-stu-id="7f920-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="7f920-111">Dans le nuage connecteur version 2.0 et versions ultérieure, le processus de détection utilise le Skype pour Business Corpnet commutateur pour établir des connexions de PowerShell pour les ordinateurs dans le nuage connecteur ; pour les versions antérieures à 2.0, le processus de détection utilise le commutateur de gestion dans le nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="7f920-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f920-112">Pour la récupération automatique aboutisse, la connectivité réseau entre l’hôte et les machines virtuelles doit être sur le commutateur réseau hôte.</span><span class="sxs-lookup"><span data-stu-id="7f920-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="7f920-113">Veillez à vérifier la connectivité réseau pour vous assurer que la détection automatique et de récupération soient prises en compte.</span><span class="sxs-lookup"><span data-stu-id="7f920-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="7f920-114">**Surveillance :** Les services suivants sont analysés dans le nuage connecteur version 2.0 et versions ultérieure :</span><span class="sxs-lookup"><span data-stu-id="7f920-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="7f920-115">Machines virtuelles n’êtes pas connectés au nuage connecteur d’entreprise ou commutateurs virtuels Internet</span><span class="sxs-lookup"><span data-stu-id="7f920-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="7f920-116">Machines virtuelles sont dans un état arrêté ou enregistré</span><span class="sxs-lookup"><span data-stu-id="7f920-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="7f920-117">Services de serveur d’administration centrale : RÉPLICA, forme de base</span><span class="sxs-lookup"><span data-stu-id="7f920-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="7f920-118">Services de serveur de médiation : RÉPLICA, RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="7f920-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="7f920-119">Services de serveur Edge : RÉPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="7f920-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="7f920-120">Trafic entrant pare-feu règles sont désactivés pour RTCSRV CS sur le serveur de périphérie, CS RTCMEDSRV sur le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7f920-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="7f920-121">Dans le nuage connecteur version 1.4.2, uniquement les services suivants sont analysés :</span><span class="sxs-lookup"><span data-stu-id="7f920-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="7f920-122">Services de serveur de médiation : RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="7f920-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="7f920-123">Service du serveur Edge : RTCSRV</span><span class="sxs-lookup"><span data-stu-id="7f920-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="7f920-124">**Processus de récupération :** Si tous les services surveillés sont arrêtés, un matériel est marqué vers le bas et services sont arrêtés et marqués manuelles jusqu'à ce que tous les problèmes peuvent être résolus.</span><span class="sxs-lookup"><span data-stu-id="7f920-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="7f920-125">Cela empêche les appels du routage vers une application qui peut entraîner des échecs d’appel.</span><span class="sxs-lookup"><span data-stu-id="7f920-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="7f920-126">Le service de gestion du nuage connecteur système recommencer la récupération automatique comme suit</span><span class="sxs-lookup"><span data-stu-id="7f920-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="7f920-127">L’intervalle de nouvelle tentative initiale est toutes les dix secondes avec un intervalle maximal d’une heure.</span><span class="sxs-lookup"><span data-stu-id="7f920-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="7f920-128">Pour les tentatives de trois premiers récupération, l’intervalle de temps est de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="7f920-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="7f920-129">L’intervalle de temps à partir de la quatrième tentative, augmente par deux fois la précédente intervalle de temps.</span><span class="sxs-lookup"><span data-stu-id="7f920-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="7f920-130">Par exemple, la quatrième tentative sera se produisent dans les 20 secondes, la cinquième de 40 secondes et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="7f920-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="7f920-131">Lorsque l’intervalle maximal d’une heure est atteint, tentatives continue une fois par heure.</span><span class="sxs-lookup"><span data-stu-id="7f920-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="7f920-132">Lors de la récupération se déroule correctement, le nombre de l’intervalle et réessayez est défini à leurs valeurs initiales.</span><span class="sxs-lookup"><span data-stu-id="7f920-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="7f920-133">Si le service de gestion est redémarré, le nombre de l’intervalle et réessayez est réinitialisé à leurs valeurs initiales.</span><span class="sxs-lookup"><span data-stu-id="7f920-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="7f920-134">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="7f920-134">Troubleshooting</span></span>

<span data-ttu-id="7f920-135">Voici des solutions aux problèmes couramment rencontrés :</span><span class="sxs-lookup"><span data-stu-id="7f920-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="7f920-136">**Problème : le déploiement échoue ou cesse de répondre pendant l’exécution des scripts de déploiement. Après s’être connectée sur chaque machine virtuelle, l’adresse IP est manquante ou incorrecte pour la NIC Externe/Interne/Gestion.**</span><span class="sxs-lookup"><span data-stu-id="7f920-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="7f920-137">**Résolution :** Ce problème ne peut pas être résolu automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7f920-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="7f920-138">Les NIC ne peuvent pas être ajoutées aux machines virtuelles tant qu’elles sont en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="7f920-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="7f920-139">Veuillez éteindre et retirer ces machines virtuelles dans le gestionnaire hyper-v, puis exécuter l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7f920-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="7f920-140">**Problème : après l'installation du serveur et de la forêt Active Directory, le serveur CMS et/ou le serveur de médiation n'ont pas correctement rejoint le domaine.**</span><span class="sxs-lookup"><span data-stu-id="7f920-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="7f920-141">**Résolution :** Pour résoudre ce problème, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="7f920-142">Connectez-vous au serveur Active Directory et vérifiez que le domaine a été correctement créé.</span><span class="sxs-lookup"><span data-stu-id="7f920-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="7f920-143">Connectez-vous au serveur CMS/de médiation et vérifiez qu’une adresse IP valide est affectée à la NIC du réseau interne, et qu'une adresse IP statique et le DNS sont configurés comme adresse IP du serveur AD.</span><span class="sxs-lookup"><span data-stu-id="7f920-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="7f920-144">Ouvrez une session sur le serveur CMS/médiation et ouvrez une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="7f920-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="7f920-145">Assurez-vous que vous pouvez tester l’adresse IP et le nom de domaine complet du serveur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7f920-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="7f920-146">Si vous ne pouvez pas, il peut être un conflit d’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="7f920-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="7f920-147">Veuillez essayer d’attribuer une nouvelle adresse IP pour Active Directory et mettre à jour DNS sur le serveur CMS/médiation en conséquence.</span><span class="sxs-lookup"><span data-stu-id="7f920-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="7f920-148">**Problème : Vous recevez le message d’erreur suivant, « Remove-VMSwitch : Échec lors de la suppression du commutateur Ethernet virtuel. Le commutateur virtuel « Nuage connecteur gestion report » ne peut pas être supprimé car il est utilisé par les ordinateurs virtuels ou affecté aux pools enfants. »**</span><span class="sxs-lookup"><span data-stu-id="7f920-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="7f920-149">**Résolution :** Le « nuage connecteur gestion commutateur » n’a pas été supprimé après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="7f920-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="7f920-150">Si vous avez atteint cette erreur, veuillez accédez à Gestionnaire Hyper-v et vérifiez qu’il y a pas encore un ordinateur virtuel toujours connecté.</span><span class="sxs-lookup"><span data-stu-id="7f920-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="7f920-151">S’il existe des machines virtuelles encore connectés, déconnectez-les et supprimer le commutateur de gestion.</span><span class="sxs-lookup"><span data-stu-id="7f920-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="7f920-152">Si le commutateur gestion toujours ne peut pas être supprimé, redémarrez le serveur hôte et réessayez.</span><span class="sxs-lookup"><span data-stu-id="7f920-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="7f920-153">**Problème : Vous recevez le message d’erreur suivant, « Service RTCMRAUTH Échec de démarrage. Vérifiez que le service n’est pas désactivé. »**</span><span class="sxs-lookup"><span data-stu-id="7f920-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f920-154">Ce problème s’applique uniquement aux versions de nuage connecteur antérieures à 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="7f920-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="7f920-p110">L’échec du démarrage peut aussi être dû au fait que le serveur frontal a basculé (en utilisant la bascule ordinateur). Si c’est le cas, veuillez appeler la restauration (en utilisant la restauration ordinateur).</span><span class="sxs-lookup"><span data-stu-id="7f920-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="7f920-p111">**Résolution :** Ce problème se produit sur un serveur Edge quand le certificat de l’AC racine ou le certificat de l’AC intermédiaire n’est pas approuvé par le serveur Edge, même si le certificat extérieur peut être importé mais que la chaîne de certificats est brisée. Dans ces conditions, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="7f920-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="7f920-p112">Veuillez importer manuellement dans le serveur Edge le certificat de l’AC racine et tous les certificats d’AC intermédiaires de votre certificat externe, puis redémarrer le serveur Edge. Une fois que les services RTCMRAUTH et RTCSRV ont démarré sur le serveur Edge, retournez sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez l’applet de commande suivante pour basculer vers le nouveau déploiement :</span><span class="sxs-lookup"><span data-stu-id="7f920-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="7f920-162">**Problème : le serveur hôte a redémarré à l’application des mises à jour de Windows, et les appels qu’il gérait échouent.**</span><span class="sxs-lookup"><span data-stu-id="7f920-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="7f920-163">**Résolution :** Si vous avez déployé un environnement de haute disponibilité, Microsoft propose une applet de commande qui permettent de déplacer un ordinateur hôte (instance de déploiement) vers ou depuis la topologie actuelle lorsque vous vérifiez et installez manuellement les mises à jour de Windows.</span><span class="sxs-lookup"><span data-stu-id="7f920-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="7f920-164">Pour cela, veuillez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="7f920-165">Sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez :</span><span class="sxs-lookup"><span data-stu-id="7f920-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```
   Enter-CcUpdate
   ```

2. <span data-ttu-id="7f920-166">Vérifiez la présence de mise à jour, et installez toutes celles qui sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="7f920-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="7f920-167">Dans la console PowerShell, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7f920-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="7f920-168">**Problème : Quand un appel est placé en utilisant un numéro RTC depuis un client Skype Entreprise, l';appel ne peut pas être transformé en conférence en invitant un autre numéro RTC.**</span><span class="sxs-lookup"><span data-stu-id="7f920-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="7f920-169">**Résolution :** Pour résoudre ce problème, voir [hybride en ligne de configurer les paramètres de serveur de médiation](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="7f920-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="7f920-170">**Problème : un avertissement à propos de Windows Update s’affiche quand vous installez le serveur Active Directory - « La mise à jour automatique de Windows n’est pas activée. Pour vous assurer que le rôle ou la fonctionnalité que vous venez d’installer est automatiquement mis à jour, activez Windows Update. »**</span><span class="sxs-lookup"><span data-stu-id="7f920-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="7f920-171">**Résolution :** Lancer une session PowerShell distante de client à l’aide de Skype pour les informations d’identification d’administration de Business client, puis exécutez l’applet de commande suivante pour vérifier la configuration _EnableAutoUpdate_ de votre site :</span><span class="sxs-lookup"><span data-stu-id="7f920-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="7f920-172">Si _EnableAutoUpdate_ est définie sur **True**, vous pouvez ignorer ce message d’avertissement, car le service CCEManagement gère le téléchargement et l’installation de mises à jour de Windows pour les ordinateurs virtuels et le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7f920-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="7f920-173">Si _EnableAutoUpdate_ est défini sur **False**, exécutez après l’applet de commande pour lui attribuer **la valeur True**.</span><span class="sxs-lookup"><span data-stu-id="7f920-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="7f920-174">Une autre solution consiste à vérifier et installer les mises à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="7f920-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="7f920-175">Consultez la rubrique suivante.</span><span class="sxs-lookup"><span data-stu-id="7f920-175">See the next section.</span></span>
    
- <span data-ttu-id="7f920-176">**Problème : Vous recevez un message d’erreur : Impossible d’enregistrer l’appliance car votre entrée/configuration actuelle \<SiteName\> ou \<ApplianceName\> ou \<FQDN du serveur de médiation\> ou \<adresse IP de serveur de médiation \> est en conflit avec l’ou les matériels jour existants. Supprimer l’appliance conflit ou mettre à jour vos informations de configuration d’entrée, puis enregistrer à nouveau. « CcAppliance-enregistrer pour enregistrer la solution en cours en ligne lorsqu’il est exécuté.**</span><span class="sxs-lookup"><span data-stu-id="7f920-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="7f920-177">**Résolution :** Valeurs de la \<ApplianceName\>, \<FQDN du serveur de médiation\> et \<adresse IP de serveur de médiation\> doit être unique et uniquement utilisé pour l’inscription d’une application.</span><span class="sxs-lookup"><span data-stu-id="7f920-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="7f920-178">Par défaut, \<ApplianceName\> provient du nom d’hôte.</span><span class="sxs-lookup"><span data-stu-id="7f920-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="7f920-179">\<FQDN du serveur de médiation\> et \<adresse IP de serveur de médiation\> définies dans le fichier de configuration ini.</span><span class="sxs-lookup"><span data-stu-id="7f920-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="7f920-180">Par exemple, utiliser (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) pour inscrire sur SiteName=MySite, mais s'il existe un appareil inscrit (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), un conflit se produira.</span><span class="sxs-lookup"><span data-stu-id="7f920-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="7f920-181">Tout d’abord, vérifiez votre fichier CloudConnector.ini dans la rubrique répertoire ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="7f920-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="7f920-182">Vous obtiendrez \<SiteName\>, \<FQDN du serveur de médiation\> et \<adresse IP de serveur de médiation\> valeurs dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="7f920-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="7f920-183">\<ApplianceName\> est le nom du serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7f920-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="7f920-184">Deuxièmement, lancer client PowerShell à distance à l’aide de votre Skype pour les informations d’identification d’entreprise client d’administration, puis exécutez l’applet de commande suivante pour vérifier les ou les matériels jour inscrits.</span><span class="sxs-lookup"><span data-stu-id="7f920-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="7f920-185">Après avoir identifié les conflits, vous pouvez soit mettre à jour votre fichier CloudConnector.ini avec les informations correspondant à l’appliance inscrite, soit annuler l’inscription de « l’appliance » existant pour résoudre les conflits.</span><span class="sxs-lookup"><span data-stu-id="7f920-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="7f920-186">**Problème : L’applet de commande Get-CcRunningVersion renvoie une valeur vide s’il existe une solution déployée en cours d’exécution sur l’hôte.**</span><span class="sxs-lookup"><span data-stu-id="7f920-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="7f920-p118">**Résolution :** Cela peut arriver quand vous passez de la version 1.3.4 ou 1.3.8 à la version 1.4.1. Après l’installation de la 1.4.1 avec le .msi, vous devez exécuter `Register-CcAppliance` avant d’exécuter une quelconque autre applet de commande. `Register-CcAppliance` fera migrer le module du fichier .ini de %UserProfile%\CloudConnector vers %ProgramData%\CloudConnector. Si vous l’avez manqué, un nouveau module .ini sera créé dans le dossier %ProgramData%\CloudConnector et remplacera les informations de la version exécutée ou de sauvegarde pour la version 1.3.4 ou la 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="7f920-p118">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1. After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet. `Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector. If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="7f920-191">Comparez les modules des fichier .ini dans les dossiers %UserProfile%\CloudConnector et %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="7f920-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="7f920-192">S’il existe des différences, supprimez le fichier module.ini %ProgramData%\CloudConnector et relancez `Register-CcAppliance`.</span><span class="sxs-lookup"><span data-stu-id="7f920-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="7f920-193">Vous pouvez également modifier le fichier manuellement à la version de sauvegarde et le fonctionnement correct.</span><span class="sxs-lookup"><span data-stu-id="7f920-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="7f920-194">**Problème : Après avoir exécuté l’applet de commande commutateur-CcVersion pour basculer vers une ancienne version qui est différente de la version actuelle de script, il n’est aucune prise en charge de haute disponibilité pour cette version ancienne.**</span><span class="sxs-lookup"><span data-stu-id="7f920-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="7f920-195">**Résolution :** Par exemple, vous avez mis à niveau 1.4.1 à 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="7f920-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="7f920-196">La version actuelle de script, qui peut être déterminée en exécutant `Get-CcVersion`et la version en cours d’exécution, qui peut être déterminée en exécutant `Get-CcRunningVersion` sont les deux 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="7f920-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="7f920-197">À ce stade, si vous exécutez `Switch-CcVersion` pour faire rebasculer la version exécutée vers la version 1.4.1, la haute disponibilité pour cette ancienne version ne sera pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="7f920-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="7f920-p121">Pour que la haute disponibilité soit entièrement prise en charge, veuillez rebasculer vers la version 1.4.2 afin que la version exécutée et celle du script soient les mêmes. Si vous rencontrez des problèmes avec votre déploiement 1.4.2, veuillez désinstaller et réinstaller dès que possible.</span><span class="sxs-lookup"><span data-stu-id="7f920-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="7f920-200">**Problème : Les certificats de l’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**</span><span class="sxs-lookup"><span data-stu-id="7f920-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="7f920-p122">**Résolution :** Les certificats de l’autorité de certification de Skype Entreprise sont valides cinq ans. Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides deux ans.</span><span class="sxs-lookup"><span data-stu-id="7f920-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7f920-203">Dans le nuage connecteur version 2.0 et versions ultérieure, l’applet de commande renouveler-CcServerCertificate a été modifié pour la mise à jour-CcServerCertificate et l’applet de commande renouveler-CcCACertificate a été modifié pour la mise à jour-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="7f920-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="7f920-204">Si les certificats internes émis vers le magasin Central de gestion, le serveur de médiation et le serveur de périphérie sont bientôt expirer ou compromis, exécutez le renouvellement-CcServerCertificate ou l’applet de commande Update-CcServerCertificate pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="7f920-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="7f920-205">Si les certificats d’autorité de certification sont bientôt expirer, exécutez la cmdlet renouveler-CcCACertificate ou CcCACertificate de la mise à jour pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="7f920-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="7f920-206">**Si les certificats d’autorité de certification sont compromises et s’il n'existe qu’une seule application dans le site,** effectuez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="7f920-207">Exécutez l’applet de commande Enter-CcUpdate afin d’épuiser les services et de mettre l’appliance en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="7f920-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
    
2. <span data-ttu-id="7f920-208">Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :</span><span class="sxs-lookup"><span data-stu-id="7f920-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="7f920-209">Pour les versions de nuage connecteur avant 2.0 :</span><span class="sxs-lookup"><span data-stu-id="7f920-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="7f920-210">Ou pour le nuage connecteur version 2.0 et versions ultérieure :</span><span class="sxs-lookup"><span data-stu-id="7f920-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. <span data-ttu-id="7f920-211">Exécutez l’applet de commande Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="7f920-211">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>
    
4. <span data-ttu-id="7f920-212">Exécutez l’applet de commande Export-CcRootCertificate sur le fichier local dans l’appliance, puis copiez et installez le certificat exporté vers vos passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="7f920-212">Run the Export-CcRootCertificate cmdlet on the local file in the appliance, and then copy and install the exported certificate to your PSTN gateways.</span></span>
    
    <span data-ttu-id="7f920-213">**Si les certificats d’autorité de certification sont compromises et qu’il existe plusieurs applications dans le site,** procédez comme suit séquentiel sur chaque appliance dans le site.</span><span class="sxs-lookup"><span data-stu-id="7f920-213">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="7f920-214">Microsoft recommande que vous suivez ces étapes pendant les heures non pics d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="7f920-214">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
   - <span data-ttu-id="7f920-215">Sur la première application, exécutez l’applet de commande Remove-CcCertificationAuthorityFile pour le nettoyage de l’autorité de certification sauvegarder des fichiers dans le \<SiteRoot\> directory.</span><span class="sxs-lookup"><span data-stu-id="7f920-215">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>
    
   - <span data-ttu-id="7f920-216">Exécutez l’applet de commande entrée-CcUpdate pour décharger les services et placer chaque application en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="7f920-216">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>
    
   - <span data-ttu-id="7f920-217">Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :</span><span class="sxs-lookup"><span data-stu-id="7f920-217">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="7f920-218">Pour les versions de nuage connecteur avant 2.0 :</span><span class="sxs-lookup"><span data-stu-id="7f920-218">For Cloud Connector releases before 2.0:</span></span>
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="7f920-219">Ou pour le nuage connecteur version 2.0 et versions ultérieure :</span><span class="sxs-lookup"><span data-stu-id="7f920-219">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

   - <span data-ttu-id="7f920-220">Sur la première application, exécutez la cmdlet suivante pour sauvegarder les fichiers de l’autorité de certification pour le \<SiteRoot\> dossier.</span><span class="sxs-lookup"><span data-stu-id="7f920-220">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span> <span data-ttu-id="7f920-221">Ultérieurement, sur tous les autres matériels dans le même site, l’applet de commande Reset-CcCACertificate consomme automatiquement les fichiers de sauvegarde d’autorité de certification et équipements utiliseront le même certificat racine.</span><span class="sxs-lookup"><span data-stu-id="7f920-221">Later, on all other appliances in the same site, the Reset-CcCACertificate cmdlet will consume the CA backup files automatically and appliances will use the same root certificate.</span></span>
    
     ```
     Backup-CcCertificationAuthority
     ```

   - <span data-ttu-id="7f920-222">Exécutez l’applet de commande Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="7f920-222">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 
    
   - <span data-ttu-id="7f920-223">Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de commande Export-CcRootCertificate à partir de n’importe quel matériel dans le site, puis installez le certificat exporté dans vos passerelles PSTN.</span><span class="sxs-lookup"><span data-stu-id="7f920-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> 
    
- <span data-ttu-id="7f920-224">**Problème : Vous recevez le message d’erreur suivant dans le journal du Service de gestion de connecteur dans le nuage, « C:\Program Files\Skype pour Business nuage connecteur Edition\ManagementService\CceManagementService.log » : erreur CceService : 0 : exception inattendue lorsque rapports d’état en ligne : System.Management.Automation.CmdletInvocationException : Échec de l’ouverture de session de l’utilisateur \<administrateur client Global\>. Créez un nouvel objet d’informations d’identification, en veillant à ce que vous avez utilisé le nom d’utilisateur et le mot de passe. ---\>**</span><span class="sxs-lookup"><span data-stu-id="7f920-224">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="7f920-225">**Résolution :** Informations d’identification d’administration Office 365 client globale ont été modifiées depuis l’appliance nuage connecteur a été enregistré.</span><span class="sxs-lookup"><span data-stu-id="7f920-225">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="7f920-226">Pour mettre à jour les informations d’identification stockées localement sur le matériel de nuage connecteur, exécutez ce qui suit à partir de PowerShell administrateur sur l’application hôte :</span><span class="sxs-lookup"><span data-stu-id="7f920-226">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="7f920-227">**Problème : Une fois que vous modifiez le mot de passe pour le compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : clé non valide pour une utilisation dans spécifié état. » dans %ProgramFiles%\Skype Business Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de l’applet de commande Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="7f920-227">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="7f920-228">**Résolution :** Toutes les informations d’identification sur le nuage connecteur sont stockées dans le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».</span><span class="sxs-lookup"><span data-stu-id="7f920-228">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="7f920-229">Lorsque le mot de passe sur le serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="7f920-229">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="7f920-230">**Si vous exécutez la version 1.4.2 de Cloud Connector,** renouvelez tous les mots de passe Cloud Connector en suivant les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-230">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="7f920-231">redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7f920-231">Restart the host server.</span></span>
    
  2. <span data-ttu-id="7f920-232">Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».</span><span class="sxs-lookup"><span data-stu-id="7f920-232">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="7f920-233">Lancer une console PowerShell en tant qu’administrateur et exécutez « Register-CcAppliance-Local » à entrer les mots de passe suivant la description.</span><span class="sxs-lookup"><span data-stu-id="7f920-233">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="7f920-234">Entrez les mots de passe même que vous avez entré avant le déploiement dans le nuage connecteur.</span><span class="sxs-lookup"><span data-stu-id="7f920-234">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="7f920-235">**Si vous exécutez nuage connecteur 2.0 ou version ultérieure,** régénérez tous les mots de passe dans le nuage connecteur en suivant ces étapes :</span><span class="sxs-lookup"><span data-stu-id="7f920-235">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="7f920-236">redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="7f920-236">Restart the host server.</span></span>
    
  5. <span data-ttu-id="7f920-237">Supprimez le fichier suivant : « % SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ».</span><span class="sxs-lookup"><span data-stu-id="7f920-237">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="7f920-238">Lancer une console PowerShell en tant qu’administrateur et exécutez « Register-CcAppliance-Local » à entrer les mots de passe suivant la description.</span><span class="sxs-lookup"><span data-stu-id="7f920-238">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="7f920-p127">Si le fichier du mot de passe en mémoire a été généré avec la version 1.4.2 de Cloud Connector, utilisez le mot de passe VMAdmin pour le mot de passe CceService lorsque vous y serez invité. Saisissez le même mot de passe que vous avez saisi pour le déploiement de Cloud Connector pour tous les autres comptes.</span><span class="sxs-lookup"><span data-stu-id="7f920-p127">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="7f920-241">Si le fichier du mot de passe en mémoire a été généré avec la version 1.4.2 de Cloud Connector et que les mots de passe DomainAdmin et VMAdmin sont différents, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-241">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="7f920-242">Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f920-242">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="7f920-243">Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="7f920-243">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="7f920-244">Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="7f920-244">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="7f920-245">Si le fichier de mot de passe mis en cache a été généré avec le nuage connecteur version 2.0 ou version ultérieure, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe en tant que CceService.</span><span class="sxs-lookup"><span data-stu-id="7f920-245">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="7f920-246">Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-246">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="7f920-247">Exécutez Set-CcCredential -AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f920-247">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="7f920-248">Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="7f920-248">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="7f920-249">Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe DomainAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="7f920-249">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="7f920-250">Exécutez Set-CcCredential -AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f920-250">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="7f920-251">Lorsque vous serez invité à entrer les anciennes informations d'identification du compte, saisissez les informations d'identification que vous avez utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="7f920-251">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="7f920-252">Lorsque vous serez invité à entrer les nouvelles informations d'identification du compte, saisissez le mot de passe VmAdmin que vous avez utilisé auparavant. </span><span class="sxs-lookup"><span data-stu-id="7f920-252">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="7f920-253">**Problème : Avec le nuage connecteur version 2.1 et version ultérieure, lors de l’exécution Register-CcAppliance ou autres applets de commande sur le matériel, vous recevez un message d’erreur tel : » pour chaque objet : la propriété « Commune » est introuvable sur cet objet. Vérifiez que la propriété existe. À C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 caractère : 14 »**</span><span class="sxs-lookup"><span data-stu-id="7f920-253">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="7f920-254">**Résolution :** Nuage connecteur 2.1 et version ultérieure requiert .NET Framework 4.6.1 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="7f920-254">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="7f920-255">Veuillez mettre à jour .NET Framework sur l’application vers la version 4.6.1 ou version ultérieure et réexécutez le cmdlet(s).</span><span class="sxs-lookup"><span data-stu-id="7f920-255">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="7f920-256">**Problème : Nuage connecteur Edition 2.1, lorsque vous exécutez Install-CcAppliance, vous recevez un message d’erreur tel que : « Impossible d’installer la nouvelle instance avec l’erreur : Impossible de définir « État » car seules les chaînes peuvent être utilisés en tant que valeurs pour définir les propriétés XmlNode »**</span><span class="sxs-lookup"><span data-stu-id="7f920-256">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="7f920-257">**Résolution :** Dans Cloudconnector.ini, sous la section [courantes], ajoutez la configuration de « État » comme indiqué ci-dessous : CountryCode = US State = WA ville = Redmond</span><span class="sxs-lookup"><span data-stu-id="7f920-257">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="7f920-258">Il n’est pas obligatoire pour la ligne « État » à la valeur, mais la ligne « État » ne peut pas être supprimée à partir du fichier Cloudconnector.ini.</span><span class="sxs-lookup"><span data-stu-id="7f920-258">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="7f920-259">**Problème : Vous recevez le message d’erreur « Dismount-WindowsImage : Dismount-WindowsImage a échoué. Code d’erreur = 0xc1550115 » lors de l’installation ou mise à niveau dans le nuage connecteur Edition.**</span><span class="sxs-lookup"><span data-stu-id="7f920-259">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="7f920-260">**Résolution :** Lancer une console PowerShell en tant qu’administrateur, exécutez « DISM-Cleanup-Wim' ».</span><span class="sxs-lookup"><span data-stu-id="7f920-260">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="7f920-261">Cela nettoie toutes les images défectueux.</span><span class="sxs-lookup"><span data-stu-id="7f920-261">This will clean up all troubled images.</span></span> <span data-ttu-id="7f920-262">Réexécutez Install-CcAppliance ou attendez que les fichiers binaires mettre à niveau automatiquement.</span><span class="sxs-lookup"><span data-stu-id="7f920-262">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="7f920-263">**Problème : Déploiement de l’application dans un environnement de haute disponibilité dans le nuage connecteur échoue**</span><span class="sxs-lookup"><span data-stu-id="7f920-263">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="7f920-264">**Résolution :** Les étapes à que suivre dépendent de la raison pour laquelle le déploiement a échoué :</span><span class="sxs-lookup"><span data-stu-id="7f920-264">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="7f920-265">Si la première application de nuage connecteur échoue et vous ne pouvez pas déterminer la cause de l’échec, vous devez installer l’application à nouveau jusqu'à ce que le déploiement a réussi et puis installer les autres applications.</span><span class="sxs-lookup"><span data-stu-id="7f920-265">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="7f920-266">En cas d’échec de l’application connecteur sur le nuage avec un problème mineur, par exemple un problème de certificat externe, vous pourrez peut-être résoudre le problème sans installer de nouveau l’application.</span><span class="sxs-lookup"><span data-stu-id="7f920-266">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="7f920-267">Vous pouvez ensuite utiliser des clients PowerShell à distance pour marquer le déploiement comme étant réussi comme suit.</span><span class="sxs-lookup"><span data-stu-id="7f920-267">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="7f920-268">(Vous pouvez également utiliser les étapes suivantes si le premier déploiement a réussi, mais, pour une raison quelconque, nuage connecteur ne parvient pas à signaler le déploiement comme étant réussi.)</span><span class="sxs-lookup"><span data-stu-id="7f920-268">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="7f920-269">Pour obtenir l’identité (GUID) de l’application dans le nuage connecteur, exécutez l’applet de commande Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="7f920-269">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="7f920-270">Pour marquer le matériel comme correctement déployé, exécutez la Set-CsCceApplianceDeploymentStatus comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f920-270">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="7f920-271">**Problème : Vous devez vérifier et installer les mises à jour de Windows manuellement sur le serveur hôte ou les machines virtuelles.**</span><span class="sxs-lookup"><span data-stu-id="7f920-271">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="7f920-p132">**Résolution ** Nous vous conseillons de profiter des avantages des mises à jour automatiques du système d’exploitation fournies par la version Cloud Connector de Skype Entreprise. Une fois qu’un appareil est inscrit pour une gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifieront et installeront automatiquement les mises à jour de Windows en fonction des paramètres d’heure de mise à jour du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="7f920-p132">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="7f920-p133">Si vous devez vérifier et installer les mises à jour de Windows manuellement, suivez les étapes de cette rubrique qui s’appliquent à votre type de déploiement. Vous devriez mettre à jour le serveur hôte en même temps que les machines virtuelles qui sont exécutées dessus pour réduire le temps d’arrêt nécessaire aux mises à jour.</span><span class="sxs-lookup"><span data-stu-id="7f920-p133">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="7f920-p134">Si vous préférez, vous pouvez utiliser un serveur WSUS (services de mises à jour de serveur Windows) pour qu’il fournisse les mises à jour aux serveurs Cloud Connector. Assurez-vous simplement de configurer Windows Update de sorte qu’il n’effectue **pas** d’installation automatique.</span><span class="sxs-lookup"><span data-stu-id="7f920-p134">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="7f920-278">Pour en savoir plus sur la mise à jour de votre déploiement Cloud Collector manuellement, consultez la rubrique suivante.</span><span class="sxs-lookup"><span data-stu-id="7f920-278">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="7f920-279">**Problème : Lorsque le nuage connecteur mises à jour vers une nouvelle version, cmdlets de connecteur de nuage ne sont pas mis à jour.**</span><span class="sxs-lookup"><span data-stu-id="7f920-279">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="7f920-280">Cela se produit parfois si une fenêtre PowerShell reste ouverte lors de la mise à jour automatique se produit.</span><span class="sxs-lookup"><span data-stu-id="7f920-280">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="7f920-281">**Résolution :** Pour charger les applets de commande mis à jour, vous pouvez effectuer une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-281">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="7f920-282">Fermez PowerShell sur le matériel de nuage connecteur, puis rouvrez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7f920-282">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="7f920-283">Vous pouvez également exécuter Import-Module CloudConnector-Force.</span><span class="sxs-lookup"><span data-stu-id="7f920-283">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="7f920-284">**Problème : « le terme 'Stop-CsWindowsService' n’est pas reconnu comme nom de l’applet de commande, fonction, fichier de script ou programme exécutable. » erreur lorsque vous essayez d’exécuter l’applet de commande entrée-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="7f920-284">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="7f920-285">**Résolution :** Supprimez le fichier de HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $.</span><span class="sxs-lookup"><span data-stu-id="7f920-285">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="7f920-286">PowerShell crée ce fichier comme un cache des applets de commande de modules qu’il trouve afin qu’il ne doit pas recommencer l’analyse chaque fois que tous les modules que choses vraiment lente.</span><span class="sxs-lookup"><span data-stu-id="7f920-286">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="7f920-287">Probablement, il a été une corruption de fichiers qui fournie résultats trompeuses PowerShell lors de la lecture depuis la mémoire cache.</span><span class="sxs-lookup"><span data-stu-id="7f920-287">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="7f920-288">**Problème : « Import-Module CloudConnector » génère l’erreur « Import-Module : le module spécifié est « CloudConnector » n’a pas été chargé, car aucun fichier de module valide a été trouvé dans n’importe quel répertoire module »**</span><span class="sxs-lookup"><span data-stu-id="7f920-288">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="7f920-289">**Résolution **</span><span class="sxs-lookup"><span data-stu-id="7f920-289">**Resolution:**</span></span>
    - <span data-ttu-id="7f920-290">Valider que fait le module CloudConnector existe sous c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="7f920-290">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="7f920-291">Une fois la validation de ce module CloudConnector existe sous cet emplacement, la variable d’environnement PSModulePath stocker le chemin d’accès vers les emplacements des modules peut être modifiée :</span><span class="sxs-lookup"><span data-stu-id="7f920-291">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="7f920-292">a.</span><span class="sxs-lookup"><span data-stu-id="7f920-292">a.</span></span> <span data-ttu-id="7f920-293">Modification temporaire : Démarrer Powershell en tant qu’administrateur et exécutez la commande suivante : $env : PSModulePath = $env : PSModulePath + « ; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="7f920-293">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="7f920-294">b.</span><span class="sxs-lookup"><span data-stu-id="7f920-294">b.</span></span> <span data-ttu-id="7f920-295">Changement persistent, démarrer le PowerShell en tant qu’administrateur et exécutez les commandes suivantes, un par un : $CurrentValue = [Environment] :: GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules », « Machine »)</span><span class="sxs-lookup"><span data-stu-id="7f920-295">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="7f920-296">Installer manuellement les mises à jour Windows</span><span class="sxs-lookup"><span data-stu-id="7f920-296">Install Windows updates manually</span></span>

<span data-ttu-id="7f920-297">Si vous ne voulez pas utiliser les mises à jour automatiques dans votre environnement, suivez ces étapes pour vérifier et appliquer manuellement les mises à jour de Windows.</span><span class="sxs-lookup"><span data-stu-id="7f920-297">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="7f920-298">Vérifier et installer manuellement les mises à jour de Windows nécessite de redémarrer le serveur.</span><span class="sxs-lookup"><span data-stu-id="7f920-298">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="7f920-299">Lorsque le redémarrage d’un serveur hôte, les utilisateurs ne sera pas en mesure d’utiliser le connecteur sur le nuage pour passer ou recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="7f920-299">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="7f920-300">Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler quand elles ont lieu, puis redémarrer les machines au besoin au moment de votre choix pour éviter une perturbation des services.</span><span class="sxs-lookup"><span data-stu-id="7f920-300">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="7f920-301">Pour vérifier et installer manuellement les mises à jours, connectez-vous à chaque serveur hôte et ouvrez le **Panneau de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="7f920-301">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="7f920-302">Sélectionnez **système et sécurité \>mise à jour Windows**, puis gérer les mises à jour et redémarre le serveur en fonction de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="7f920-302">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="7f920-303">S’il n’existe qu’un seul appareil sur le site, connectez-vous à chaque machine virtuelle et ouvrez le **Panneau de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="7f920-303">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="7f920-304">Sélectionnez **système et sécurité \>mise à jour Windows**, puis configurez les mises à jour et redémarre le serveur comme il convient.</span><span class="sxs-lookup"><span data-stu-id="7f920-304">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="7f920-p142">S’il existe plusieurs appareils sur le site, l’instance en cours de mise à jour et de redémarrage n’est plus accessible par les utilisateurs. Les utilisateurs se connecteront à d’autres instances du déploiement jusqu’à ce que toutes les machines virtuelles et que tous les services Skype Entreprise démarrent sur les machines virtuelles après la fin des mises à jour. Pour éviter de potentielles perturbations du service, vous pouvez supprimer les instances de la haute disponibilité pendant que vous appliquez les mises à jour, puis les restaurer une fois celles-ce achevées. Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="7f920-p142">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="7f920-309">Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="7f920-309">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="7f920-310">Supprimez l’instance de la haute disponibilité grâce à l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7f920-310">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="7f920-311">Suivez les étapes pour une instance unique afin d’appliquer manuellement les mises à jour et redémarrer la machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="7f920-311">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="7f920-312">Définissez à nouveau l’instance en haute disponibilité grâce à l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7f920-312">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

<span data-ttu-id="7f920-313">Pour des déploiements sur plusieurs sites, suivez les étapes pour un site unique pour chaque site du déploiement, en appliquant les mises à jour un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="7f920-313">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="7f920-314">Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte de nuage connecteur</span><span class="sxs-lookup"><span data-stu-id="7f920-314">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="7f920-315">Si vous avez besoin installer un logiciel antivirus sur l’ordinateur hôte de connecteur dans le nuage, vous devez ajouter les exclusions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7f920-315">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="7f920-316">Répertoire de matériel local sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7f920-316">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="7f920-317">Annuaire de sites à distance sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7f920-317">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="7f920-318">Répertoire du Site local sur l’ordinateur héberge le dossier racine du site partagé.</span><span class="sxs-lookup"><span data-stu-id="7f920-318">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="7f920-319">%ProgramFiles%\Skype pour l’édition de connecteur Business Cloud</span><span class="sxs-lookup"><span data-stu-id="7f920-319">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="7f920-320">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="7f920-320">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="7f920-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="7f920-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="7f920-322">Le processus Microsoft.Rtc.CCE.ManagementService.exe.</span><span class="sxs-lookup"><span data-stu-id="7f920-322">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
