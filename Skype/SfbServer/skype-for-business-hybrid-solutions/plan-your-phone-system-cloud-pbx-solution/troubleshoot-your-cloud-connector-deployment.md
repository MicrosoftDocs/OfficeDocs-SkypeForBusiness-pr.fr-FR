---
title: Identification et résolution des problèmes de votre déploiement Cloud Connector
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
description: Résoudre les problèmes de déploiement de votre édition Cloud Connector.
ms.openlocfilehash: 3a6fd80cc0c4125303021746cdb626d8c5b49a5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814222"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="ff348-103">Identification et résolution des problèmes de votre déploiement Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ff348-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="ff348-104">Résoudre les problèmes de déploiement de votre édition Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ff348-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="ff348-p101">Cette rubrique vous décrit les solutions aux problèmes courants liés au déploiement de la version Cloud Connector. Si vous rencontrez des problèmes liés aux appels vers ou sur la Réseau Téléphonique Commuté (RTC), vous pouvez tenter de les résoudre en suivant les solutions décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ff348-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="ff348-107">Le Cloud Connector fournit des mécanismes intégrés qui permettent de résoudre automatiquement certains problèmes.</span><span class="sxs-lookup"><span data-stu-id="ff348-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="ff348-108">Un processus de détection automatique recherche les problèmes potentiels liés aux appareils Cloud Connector, et, dans la mesure du possible, effectue une action corrective pour résoudre ces problèmes sans nécessiter l’intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="ff348-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="ff348-109">Le processus de détection fonctionne comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="ff348-110">**Séquence de détection :** Le service de gestion des connecteurs Cloud exécute un processus toutes les 60 secondes pour détecter si une appliance est en panne.</span><span class="sxs-lookup"><span data-stu-id="ff348-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="ff348-111">Dans Cloud Connector version 2,0 et les versions ultérieures, le processus de détection utilise le commutateur corpnet Skype entreprise pour effectuer des connexions PowerShell aux ordinateurs Cloud Connector. pour les versions antérieures à 2,0, le processus de détection utilise le commutateur de gestion Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ff348-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff348-112">Pour que la récupération automatique puisse aboutir, la connectivité réseau doit être établie entre l’hôte et les machines virtuelles sur le commutateur du réseau hôte.</span><span class="sxs-lookup"><span data-stu-id="ff348-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="ff348-113">Veillez à vérifier la connectivité réseau pour vous assurer que la détection automatique et la récupération peuvent aboutir.</span><span class="sxs-lookup"><span data-stu-id="ff348-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="ff348-114">**Surveiller :** Les services suivants sont surveillés dans Cloud Connector version 2,0 et les versions ultérieures :</span><span class="sxs-lookup"><span data-stu-id="ff348-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="ff348-115">Les machines virtuelles ne sont pas connectées aux commutateurs virtuels d’entreprise ou de connexion Internet dans le Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ff348-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="ff348-116">Les machines virtuelles sont dans un état enregistré ou arrêté</span><span class="sxs-lookup"><span data-stu-id="ff348-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="ff348-117">Services serveur de gestion centralisée : réplica, maître</span><span class="sxs-lookup"><span data-stu-id="ff348-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="ff348-118">Services du serveur de médiation : RÉPLICA, RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="ff348-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="ff348-119">Services Edge Server : fac-similé, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="ff348-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="ff348-120">Les règles de pare-feu entrant sont désactivées pour le RTCSRV sur le serveur Edge, RTCMEDSRV CS</span><span class="sxs-lookup"><span data-stu-id="ff348-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="ff348-121">Dans Cloud Connector version 1.4.2, seuls les services suivants sont surveillés :</span><span class="sxs-lookup"><span data-stu-id="ff348-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="ff348-122">Services serveur de médiation : RTCSRV et MEDSVC</span><span class="sxs-lookup"><span data-stu-id="ff348-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="ff348-123">Service Edge Server : RTCSRV</span><span class="sxs-lookup"><span data-stu-id="ff348-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="ff348-124">**Processus de récupération :** Si des services surveillés sont en panne, une application est marquée comme étant arrêtée et les services sont arrêtés et signalés manuellement jusqu’à ce que tous les problèmes puissent être résolus.</span><span class="sxs-lookup"><span data-stu-id="ff348-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="ff348-125">Cela empêchera les appels de routage vers une appliance qui peut provoquer des échecs d’appel.</span><span class="sxs-lookup"><span data-stu-id="ff348-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="ff348-126">Le service de gestion de connecteur Cloud réutilise la récupération automatique comme suit.</span><span class="sxs-lookup"><span data-stu-id="ff348-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="ff348-127">L’intervalle de nouvelle tentative initial est de dix secondes, avec un intervalle de temps maximal d’une heure.</span><span class="sxs-lookup"><span data-stu-id="ff348-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="ff348-128">Pour les trois premières tentatives de récupération, l’intervalle est de 10 secondes.</span><span class="sxs-lookup"><span data-stu-id="ff348-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="ff348-129">À partir de la quatrième réessayer, l’intervalle de temps augmente de deux fois l’intervalle de temps précédent.</span><span class="sxs-lookup"><span data-stu-id="ff348-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="ff348-130">Par exemple, la quatrième réessayer aura lieu dans 20 secondes, le cinquième dans 40 secondes, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="ff348-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="ff348-131">Lorsque l’intervalle maximal d’une heure est atteint, les tentatives de connexion continuent une fois par heure.</span><span class="sxs-lookup"><span data-stu-id="ff348-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="ff348-132">Lorsque la restauration est réussie, l’intervalle et le nombre de tentatives sont définis sur leur valeur initiale.</span><span class="sxs-lookup"><span data-stu-id="ff348-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="ff348-133">Si le service de gestion est redémarré, l’intervalle et le nombre de tentatives sont réinitialisés à leur valeur initiale.</span><span class="sxs-lookup"><span data-stu-id="ff348-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="ff348-134">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="ff348-134">Troubleshooting</span></span>

<span data-ttu-id="ff348-135">Vous trouverez ci-après les solutions aux problèmes rencontrés fréquemment :</span><span class="sxs-lookup"><span data-stu-id="ff348-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="ff348-136">**Problème : le déploiement échoue ou cesse de répondre pendant l’exécution des scripts de déploiement. Après s’être connectée sur chaque machine virtuelle, l’adresse IP est manquante ou incorrecte pour la NIC Externe/Interne/Gestion.**</span><span class="sxs-lookup"><span data-stu-id="ff348-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="ff348-137">**Résolution :** Ce problème ne peut pas être résolu automatiquement.</span><span class="sxs-lookup"><span data-stu-id="ff348-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="ff348-138">Les NIC ne peuvent pas être ajoutées aux machines virtuelles tant qu’elles sont en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="ff348-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="ff348-139">Veuillez éteindre et retirer ces machines virtuelles dans le gestionnaire hyper-v, puis exécuter l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ff348-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="ff348-140">**Problème : après l’installation du serveur et de la forêt Active Directory, le serveur CMS et/ou le serveur de médiation ne rejoignent pas correctement le domaine.**</span><span class="sxs-lookup"><span data-stu-id="ff348-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="ff348-141">**Résolution :** Pour résoudre ce problème, suivez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff348-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="ff348-142">Ouvrez une session sur le serveur Active Directory et vérifiez que le domaine a été correctement créé.</span><span class="sxs-lookup"><span data-stu-id="ff348-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="ff348-143">Connectez-vous au serveur CMS/de médiation et vérifiez qu’une adresse IP valide est affectée à la NIC du réseau interne, et qu'une adresse IP statique et le DNS sont configurés comme adresse IP du serveur AD.</span><span class="sxs-lookup"><span data-stu-id="ff348-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="ff348-144">Ouvrez une session sur le serveur CMS/médiation et ouvrez une invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="ff348-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="ff348-145">Vérifiez que vous pouvez exécuter une commande ping sur le FQDN et l’adresse IP du serveur Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff348-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="ff348-146">Si ce n’est pas le cas, il peut y avoir un conflit d’adresses IP.</span><span class="sxs-lookup"><span data-stu-id="ff348-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="ff348-147">Veuillez essayer d’affecter une nouvelle adresse IP pour Active Directory et de mettre à jour le DNS sur le serveur CMS/médiation en conséquence.</span><span class="sxs-lookup"><span data-stu-id="ff348-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="ff348-148">**Problème : vous recevez le message d’erreur suivant : «Remove-VMSwitch : failed lors de la suppression du commutateur Virtual Ethernet. Le commutateur virtuel’commutateur de gestion des connecteurs Cloud’ne peut pas être supprimé car il est utilisé par des machines virtuelles ou affectées à des pools enfants. "**</span><span class="sxs-lookup"><span data-stu-id="ff348-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="ff348-149">**Résolution :** Le « commutateur de gestion des connecteurs Cloud » n’a pas été supprimé après le déploiement.</span><span class="sxs-lookup"><span data-stu-id="ff348-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="ff348-150">Si vous avez atteint ce message d’erreur, accédez au Gestionnaire Hyper-v et vérifiez qu’aucun ordinateur virtuel n’est encore connecté à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="ff348-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="ff348-151">Si des machines virtuelles sont toujours connectées, déconnectez-les et supprimez le commutateur de gestion.</span><span class="sxs-lookup"><span data-stu-id="ff348-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="ff348-152">Si le commutateur de gestion ne peut pas être supprimé, redémarrez le serveur hôte, puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="ff348-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="ff348-153">**Problème : vous recevez le message d’erreur suivant : « impossible de démarrer le service RTCMRAUTH ». Vérifiez que le service n’est pas désactivé.»**</span><span class="sxs-lookup"><span data-stu-id="ff348-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff348-154">Ce problème ne s’applique qu’aux versions Cloud Connector antérieures à la version 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ff348-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="ff348-p110">L’échec du démarrage peut aussi être dû au fait que le serveur frontal a basculé (en utilisant la bascule ordinateur). Si c’est le cas, veuillez appeler la restauration (en utilisant la restauration ordinateur).</span><span class="sxs-lookup"><span data-stu-id="ff348-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="ff348-p111">**Résolution :** Ce problème se produit sur un serveur Edge quand le certificat de l’AC racine ou le certificat de l’AC intermédiaire n’est pas approuvé par le serveur Edge, même si le certificat extérieur peut être importé mais que la chaîne de certificats est brisée. Dans ces conditions, le service RTCMRAUTH et/ou RTCSRV ne peut pas démarrer.</span><span class="sxs-lookup"><span data-stu-id="ff348-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="ff348-p112">Veuillez importer manuellement dans le serveur Edge le certificat de l’AC racine et tous les certificats d’AC intermédiaires de votre certificat externe, puis redémarrer le serveur Edge. Une fois que les services RTCMRAUTH et RTCSRV ont démarré sur le serveur Edge, retournez sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez l’applet de commande suivante pour basculer vers le nouveau déploiement :</span><span class="sxs-lookup"><span data-stu-id="ff348-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="ff348-162">**Problème : le serveur hôte a redémarré à l’application des mises à jour de Windows, et les appels qu’il gérait échouent.**</span><span class="sxs-lookup"><span data-stu-id="ff348-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="ff348-163">**Résolution :** Si vous avez déployé un environnement haute disponibilité, Microsoft fournit une cmdlet pour vous permettre de déplacer un ordinateur hôte (instance de déploiement) dans ou en dehors de la topologie actuelle lorsque vous vérifiez et installez manuellement Windows Update.</span><span class="sxs-lookup"><span data-stu-id="ff348-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="ff348-164">Pour cela, veuillez suivre les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff348-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="ff348-165">Sur le serveur hôte, lancez une console PowerShell en tant qu’administrateur, et exécutez :</span><span class="sxs-lookup"><span data-stu-id="ff348-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="ff348-166">Vérifiez la présence de mise à jour, et installez toutes celles qui sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="ff348-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="ff348-167">Dans la console PowerShell, exécutez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ff348-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="ff348-168">**Problème : Quand un appel est placé en utilisant un numéro RTC depuis un client Skype Entreprise, l';appel ne peut pas être transformé en conférence en invitant un autre numéro RTC.**</span><span class="sxs-lookup"><span data-stu-id="ff348-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="ff348-169">**Résolution :** Pour résoudre ce problème, voir [configurer les paramètres du serveur de médiation hybride en ligne](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span><span class="sxs-lookup"><span data-stu-id="ff348-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="ff348-170">**Problème : un avertissement à propos de Windows Update s’affiche quand vous installez le serveur Active Directory - « La mise à jour automatique de Windows n’est pas activée. Pour vous assurer que le rôle ou la fonctionnalité que vous venez d’installer est automatiquement mis à jour, activez Windows Update. »**</span><span class="sxs-lookup"><span data-stu-id="ff348-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="ff348-171">**Résolution :** Lancez une session PowerShell distante du client à l’aide des informations d’identification d’administrateur de clients Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier la configuration de _EnableAutoUpdate_ de votre site :</span><span class="sxs-lookup"><span data-stu-id="ff348-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="ff348-172">Si l’argument _EnableAutoUpdate_ a la valeur **true**, vous pouvez ignorer ce message d’avertissement, car le service CCEManagement gère le téléchargement et l’installation des mises à jour Windows pour les machines virtuelles et le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="ff348-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="ff348-173">Si l’argument _EnableAutoUpdate_ est défini sur **false**, exécutez l’applet de commande suivante pour lui attribuer la valeur **true**.</span><span class="sxs-lookup"><span data-stu-id="ff348-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="ff348-174">Une autre solution consiste à vérifier et installer les mises à jour manuellement.</span><span class="sxs-lookup"><span data-stu-id="ff348-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="ff348-175">Consultez la rubrique suivante.</span><span class="sxs-lookup"><span data-stu-id="ff348-175">See the next section.</span></span>
    
- <span data-ttu-id="ff348-176">**Problème : vous recevez un message d’erreur : il n’est pas possible d’enregistrer l' \<application\> , \<car\> votre \<nom de domaine\> complet \</de l’adresse\> de site Supprimez l’application Conflict ou mettez à jour vos informations d’entrée/configuration, puis inscrivez-vous à nouveau. 'lors de l’inscription de Register-CcAppliance pour inscrire l’application en ligne.**</span><span class="sxs-lookup"><span data-stu-id="ff348-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="ff348-177">**Résolution :** Les valeurs de \<l'\>adresse \<\> IP du serveur\> de \<médiation et du nom de domaine complet du serveur de médiation ApplianceName doivent être uniques et réservées pour une seule inscription d’appliance.</span><span class="sxs-lookup"><span data-stu-id="ff348-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="ff348-178">Par défaut, \<ApplianceName\> provient du nom d’hôte.</span><span class="sxs-lookup"><span data-stu-id="ff348-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="ff348-179">\<Nom de domaine\> complet \<du serveur de médiation\> et adresse IP du serveur de médiation définie dans le fichier ini de configuration.</span><span class="sxs-lookup"><span data-stu-id="ff348-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="ff348-180">Par exemple, utiliser (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) pour inscrire sur SiteName=MySite, mais s'il existe un appareil inscrit (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), un conflit se produira.</span><span class="sxs-lookup"><span data-stu-id="ff348-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="ff348-181">Tout d’abord, vérifiez votre fichier CloudConnector.ini dans la rubrique répertoire ApplianceRoot.</span><span class="sxs-lookup"><span data-stu-id="ff348-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="ff348-182">Vous obtiendrez \<SiteName\>, \<Mediation Server FQDN\> et \<les valeurs d’adresse\> IP du serveur de médiation dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="ff348-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="ff348-183">\<ApplianceName\> est le nom de votre serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="ff348-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="ff348-184">Deuxièmement, lancez l’application PowerShell distante avec les informations d’identification d’administrateur de votre client Skype entreprise, puis exécutez l’applet de commande suivante pour vérifier les matériels enregistrés.</span><span class="sxs-lookup"><span data-stu-id="ff348-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="ff348-185">Après avoir identifié les conflits, vous pouvez soit mettre à jour votre fichier CloudConnector.ini avec les informations correspondant à l’appliance inscrite, soit annuler l’inscription de « l’appliance » existant pour résoudre les conflits.</span><span class="sxs-lookup"><span data-stu-id="ff348-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="ff348-186">**Problème : l’applet de passe Get-CcRunningVersion renvoie une valeur vide si une application déployée est en cours d’exécution sur l’hôte.**</span><span class="sxs-lookup"><span data-stu-id="ff348-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="ff348-187">**Résolution :** Cela peut se produire lorsque vous effectuez une mise à niveau de 1.3.4 ou de 1.3.8 vers 1.4.1.</span><span class="sxs-lookup"><span data-stu-id="ff348-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="ff348-188">Après l’installation de la version 1.4.1 avec le fichier. msi, `Register-CcAppliance` vous devez l’exécuter avant d’exécuter une autre cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ff348-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="ff348-189">`Register-CcAppliance`va migrer le fichier module. ini de%UserProfile%\CloudConnector vers%ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="ff348-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="ff348-190">Si vous l’avez manqué, un nouveau module .ini sera créé dans le dossier %ProgramData%\CloudConnector et remplacera les informations de la version exécutée ou de sauvegarde pour la version 1.3.4 ou la 1.3.8.</span><span class="sxs-lookup"><span data-stu-id="ff348-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="ff348-191">Comparez les modules des fichier .ini dans les dossiers %UserProfile%\CloudConnector et %ProgramData%\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="ff348-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="ff348-192">S’il existe des différences, supprimez le fichier module. ini dans%ProgramData%\CloudConnector `Register-CcAppliance`, puis réexécutez.</span><span class="sxs-lookup"><span data-stu-id="ff348-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="ff348-193">Vous pouvez également modifier manuellement le fichier en fonction de la version correcte d’exécution et de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ff348-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="ff348-194">**Problème : après avoir exécuté l’applet de contrôle Switch-CcVersion pour basculer vers une ancienne version différente de la version de script actuelle, il n’y a pas de prise en charge de haute disponibilité pour cette ancienne version.**</span><span class="sxs-lookup"><span data-stu-id="ff348-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="ff348-195">**Résolution :** Par exemple, vous avez effectué une mise à niveau de 1.4.1 vers 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ff348-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="ff348-196">Votre version de script actuelle, qui peut être déterminée en `Get-CcVersion`cours d’exécution, ainsi que votre version en cours d’exécution `Get-CcRunningVersion` , qui peut être déterminée en exécution sont les deux 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="ff348-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="ff348-197">Pour le moment, si vous exécutez `Switch-CcVersion` pour basculer la version d’exécution vers 1.4.1, il n’y a pas de prise en charge de haute disponibilité pour cette ancienne version.</span><span class="sxs-lookup"><span data-stu-id="ff348-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="ff348-p121">Pour que la haute disponibilité soit entièrement prise en charge, veuillez rebasculer vers la version 1.4.2 afin que la version exécutée et celle du script soient les mêmes. Si vous rencontrez des problèmes avec votre déploiement 1.4.2, veuillez désinstaller et réinstaller dès que possible.</span><span class="sxs-lookup"><span data-stu-id="ff348-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="ff348-200">**Problème : Les certificats de l’autorité de certification ou les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont sur le point d’expirer ou compromis.**</span><span class="sxs-lookup"><span data-stu-id="ff348-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="ff348-p122">**Résolution :** Les certificats de l’autorité de certification de Skype Entreprise sont valides cinq ans. Les certificats internes délivrés au magasin central de gestion, au serveur de médiation et au serveur Edge sont valides deux ans.</span><span class="sxs-lookup"><span data-stu-id="ff348-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff348-203">Dans Cloud Connector version 2,0 et les versions ultérieures, l’applet de contrôle Renew-CcServerCertificate a été remplacée par Update-CcServerCertificate et l’applet de connexion Renew-CcCACertificate a changé pour Update-CcCACertificate.</span><span class="sxs-lookup"><span data-stu-id="ff348-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="ff348-204">Si les certificats internes émis au magasin de gestion central, au serveur de médiation et au serveur Edge sont proches de l’expiration ou de la compromission, exécutez l’applet de certification Renew-CcServerCertificate ou Update-CcServerCertificate pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="ff348-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="ff348-205">Si les certificats d’autorité de certification sont proches de leur expiration, exécutez l’applet de nouvelle tentative de renouvellement-CcCACertificate ou de mise à jour-CcCACertificate pour renouveler vos certificats.</span><span class="sxs-lookup"><span data-stu-id="ff348-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="ff348-206">**Si les certificats d’autorité de certification sont compromis et qu’il n’y a qu’une seule application sur le site,** procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="ff348-207">Exécutez l’applet de commande Enter-CcUpdate afin d’épuiser les services et de mettre l’appliance en mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="ff348-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="ff348-208">Exécutez les applets de commande suivantes afin de réinitialiser et de créer les nouveaux certificats de l’autorité de certification et tous les certificats du serveur interne :</span><span class="sxs-lookup"><span data-stu-id="ff348-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="ff348-209">Pour les publications sur le Cloud Connector avant 2,0 :</span><span class="sxs-lookup"><span data-stu-id="ff348-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="ff348-210">Ou pour la version 2,0 du Cloud Connector ou version ultérieure :</span><span class="sxs-lookup"><span data-stu-id="ff348-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="ff348-211">Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de cmdlet Export-CcRootCertificate à partir de l’application, puis installez le certificat exporté sur vos passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="ff348-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="ff348-212">Il est possible que vous deviez également remettre à nouveau le certificat sur votre passerelle.</span><span class="sxs-lookup"><span data-stu-id="ff348-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="ff348-213">Exécutez l’applet de passe Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="ff348-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="ff348-214">**Si les certificats d’autorité de certification sont compromis et qu’il existe plusieurs applications sur le site,** effectuez les étapes séquentielles suivantes sur chaque application du site.</span><span class="sxs-lookup"><span data-stu-id="ff348-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="ff348-215">Microsoft vous recommande d’effectuer ces étapes en temps réel d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="ff348-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="ff348-216">Sur la première application, exécutez l’applet de l’applet de suppression-CcCertificationAuthorityFile pour nettoyer les fichiers de \<sauvegarde\> de l’autorité de certification dans l’annuaire SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="ff348-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="ff348-217">Exécutez l’applet de conduite Enter-CcUpdate pour purger les services et placez chaque application en mode de maintenance.</span><span class="sxs-lookup"><span data-stu-id="ff348-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="ff348-218">Sur la première application, exécutez les applets de commande suivantes pour réinitialiser et créer de nouveaux certificats d’autorité de certification et tous les certificats de serveur interne :</span><span class="sxs-lookup"><span data-stu-id="ff348-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="ff348-219">Pour les publications sur le Cloud Connector avant 2,0 :</span><span class="sxs-lookup"><span data-stu-id="ff348-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="ff348-220">Ou pour la version 2,0 du Cloud Connector ou version ultérieure :</span><span class="sxs-lookup"><span data-stu-id="ff348-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="ff348-221">Sur la première application, exécutez l’applet de commande suivante pour sauvegarder les fichiers de l' \<autorité\> de certification dans le dossier SiteRoot.</span><span class="sxs-lookup"><span data-stu-id="ff348-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="ff348-222">Sur tous les autres appareils du même site, exécutez les commandes suivantes pour utiliser les fichiers de sauvegarde de l’autorité de certification, afin que les applications utilisent le même certificat racine, puis demandent de nouveaux certificats.</span><span class="sxs-lookup"><span data-stu-id="ff348-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="ff348-223">Si TLS est utilisé entre la passerelle et le serveur de médiation, exécutez l’applet de certification Export-CcRootCertificate à partir de n’importe quel appareil dans le site, puis installez le certificat exporté sur vos passerelles RTC.</span><span class="sxs-lookup"><span data-stu-id="ff348-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="ff348-224">Il est possible que vous deviez également remettre à nouveau le certificat sur votre passerelle.</span><span class="sxs-lookup"><span data-stu-id="ff348-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="ff348-225">Exécutez l’applet de passe Exit-CcUpdate pour démarrer les services et quitter le mode maintenance.</span><span class="sxs-lookup"><span data-stu-id="ff348-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="ff348-226">**Problème : vous recevez le message d’erreur suivant dans le journal du service de gestion des connecteurs Cloud, "C:\Program Files\Skype entreprise Cloud Connector Edition\ManagementService\CceManagementService.log" : CceService erreur : 0 : exception inattendue lors du signalement de l’État sur Online : System. Management. \<Automation. CmdletInvocationException\>: échec de l’ouverture de session de l’administrateur client global de l’utilisateur. Créez un nouvel objet d’information d’identification, en vous assurant d’avoir utilisé le nom d’utilisateur et le mot de passe appropriés. ---\>**</span><span class="sxs-lookup"><span data-stu-id="ff348-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="ff348-227">**Résolution :** Les informations d’identification d’administrateur de client Office 365 globales ont été modifiées depuis l’inscription de l’application Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ff348-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="ff348-228">Pour mettre à jour les informations d’identification stockées localement sur le périphérique Cloud Connector, exécutez la commande suivante à partir d’administrateur PowerShell sur l’appareil hôte :</span><span class="sxs-lookup"><span data-stu-id="ff348-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="ff348-229">**Problème : après avoir modifié le mot de passe du compte de serveur hôte que vous avez utilisé pour le déploiement, vous recevez le message d’erreur suivant : « ConvertTo-SecureString : clé non valide pour une utilisation dans l’état spécifié ». dans%ProgramFiles%\Skype entreprise Cloud Connector Edition\ManagementService\CceManagementService.log ou lors de l’exécution de l’applet de passe Get-CcCredential.**</span><span class="sxs-lookup"><span data-stu-id="ff348-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="ff348-230">**Résolution :** Les informations d’identification de tous les connecteurs Cloud sont stockées dans le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="ff348-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="ff348-231">Lorsque le mot de passe du serveur hôte change, vous devrez mettre à jour les informations d’identification stockées localement.</span><span class="sxs-lookup"><span data-stu-id="ff348-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="ff348-232">**Si vous exécutez le Cloud Connector version 1.4.2,** régénérez tous les mots de passe du connecteur Cloud en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="ff348-233">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="ff348-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="ff348-234">Supprimez le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="ff348-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="ff348-235">Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance-local » pour entrer de nouveau le mot de passe suivi de la description.</span><span class="sxs-lookup"><span data-stu-id="ff348-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="ff348-236">Entrez le mot de passe que vous avez entré auparavant pour le déploiement Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="ff348-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="ff348-237">**Si vous exécutez le Cloud Connector version 2,0 ou une version ultérieure,** régénérez tous les mots de passe du connecteur Cloud en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="ff348-238">Redémarrez le serveur hôte.</span><span class="sxs-lookup"><span data-stu-id="ff348-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="ff348-239">Supprimez le fichier suivant : «%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".</span><span class="sxs-lookup"><span data-stu-id="ff348-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="ff348-240">Lancez une console PowerShell en tant qu’administrateur, puis exécutez « Register-CcAppliance-local » pour entrer de nouveau le mot de passe suivi de la description.</span><span class="sxs-lookup"><span data-stu-id="ff348-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="ff348-241">Si le fichier de mot de passe mis en cache a été généré à l’aide de la version 1.4.2 du Cloud Connector, utilisez le mot de passe VMAdmin du mot de passe CceService lorsque vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="ff348-241">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="ff348-242">Entrez le mot de passe que vous avez entré précédemment pour le déploiement Cloud Connector pour tous les autres comptes.</span><span class="sxs-lookup"><span data-stu-id="ff348-242">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="ff348-243">Si le fichier de mot de passe mis en cache a été généré avec le Cloud Connector version 1.4.2 et que les mots de passe DomainAdmin et VMAdmin sont différents, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff348-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="ff348-244">Exécutez Set-CcCredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="ff348-245">Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService.</span><span class="sxs-lookup"><span data-stu-id="ff348-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="ff348-246">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="ff348-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="ff348-247">Si le fichier de mot de passe mis en cache a été généré avec le Cloud Connector version 2,0 ou ultérieure, par défaut, VmAdmin et DomainAdmin utilisent le même mot de passe que CceService.</span><span class="sxs-lookup"><span data-stu-id="ff348-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="ff348-248">Si vous avez modifié les mots de passe DomainAdmin et VMAdmin, vous devez effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff348-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="ff348-249">Exécutez Set-CcCredential-AccountType DomainAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="ff348-250">Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="ff348-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="ff348-251">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe DomainAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="ff348-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="ff348-252">Exécutez Set-CcCredential-AccountType VmAdmin comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="ff348-253">Lorsque vous êtes invité à entrer les informations d’identification de l’ancien compte, entrez les informations d’identification utilisées pour le mot de passe CceService</span><span class="sxs-lookup"><span data-stu-id="ff348-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="ff348-254">Lorsque vous êtes invité à entrer les informations d’identification du nouveau compte, entrez le mot de passe du mot de passe VmAdmin que vous avez utilisé auparavant.</span><span class="sxs-lookup"><span data-stu-id="ff348-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="ff348-255">**Problème : avec le Cloud Connector version 2,1 et les versions ultérieures, lors de l’exécution de Register-CcAppliance ou d’autres applets de connexion sur l’application, vous recevez un message d’erreur tel que : « pour chaque objet : la propriété «Common » est introuvable sur cet objet. Vérifiez que la propriété existe. Dans C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char : 14 pouces**</span><span class="sxs-lookup"><span data-stu-id="ff348-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="ff348-256">**Résolution :** Le Cloud Connector 2,1 et les versions ultérieures requièrent .NET Framework 4.6.1 ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="ff348-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="ff348-257">Mettez à jour .NET Framework sur l’application avec la version 4.6.1 ou une version ultérieure, puis exécutez de nouveau l’applet de contrôle.</span><span class="sxs-lookup"><span data-stu-id="ff348-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="ff348-258">**Problème : avec le Cloud Connector édition 2,1, lors de l’exécution de l’installation-CcAppliance, vous recevez un message d’erreur tel que : « échec de l’installation d’une nouvelle instance avec une erreur : impossible de définir «État », car seules les chaînes peuvent être utilisées en tant que valeurs pour définir les propriétés XmlNode».**</span><span class="sxs-lookup"><span data-stu-id="ff348-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="ff348-259">**Résolution :** Dans Cloudconnector. ini, sous la section [Common], ajoutez la configuration « State » comme suit : CountryCode = US State = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="ff348-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="ff348-260">La valeur de la ligne « State » n’est pas obligatoire, mais la ligne « State » ne peut pas être supprimée du fichier Cloudconnector. ini.</span><span class="sxs-lookup"><span data-stu-id="ff348-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="ff348-261">**Problème : vous recevez le message d’erreur suivant : «démonter-WindowsImage : Dismount-WindowsImage a échoué. Code d’erreur = 0xc1550115 "lors de l’installation ou de la mise à niveau de la version Cloud Connector.**</span><span class="sxs-lookup"><span data-stu-id="ff348-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="ff348-262">**Résolution :** Lancez une console PowerShell en tant qu’administrateur, exécutez "DISM-Cleanup-Wim" ".</span><span class="sxs-lookup"><span data-stu-id="ff348-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="ff348-263">Toutes les images dépendantes sont nettoyées.</span><span class="sxs-lookup"><span data-stu-id="ff348-263">This will clean up all troubled images.</span></span> <span data-ttu-id="ff348-264">Exécutez de nouveau l’installation-CcAppliance ou attendez que la mise à niveau du bit soit automatique.</span><span class="sxs-lookup"><span data-stu-id="ff348-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="ff348-265">**Problème : échec du déploiement du premier appareil de connexion Cloud dans un environnement HA**</span><span class="sxs-lookup"><span data-stu-id="ff348-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="ff348-266">**Résolution :** Les étapes que vous prenez dépendent de la raison pour laquelle le déploiement a échoué :</span><span class="sxs-lookup"><span data-stu-id="ff348-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="ff348-267">Si la première Appliance du connecteur Cloud ne fonctionne pas et que vous ne pouvez pas déterminer la raison de l’échec, vous devez réinstaller celle-ci jusqu’à ce que le déploiement réussisse, puis installer les autres appareils.</span><span class="sxs-lookup"><span data-stu-id="ff348-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="ff348-268">Si la première Appliance du connecteur Cloud ne fonctionne pas avec un problème mineur, tel qu’un problème de certificat externe, vous serez peut-être en mesure de résoudre le problème sans réinstaller l’appliance.</span><span class="sxs-lookup"><span data-stu-id="ff348-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="ff348-269">Vous pouvez ensuite utiliser Remote PowerShell distante pour marquer le déploiement comme ayant abouti comme suit.</span><span class="sxs-lookup"><span data-stu-id="ff348-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="ff348-270">(Vous pouvez également suivre les étapes ci-dessous si le premier déploiement a abouti, mais pour une raison quelconque, le connecteur Cloud ne peut pas signaler le déploiement en tant que succès.)</span><span class="sxs-lookup"><span data-stu-id="ff348-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="ff348-271">Pour obtenir l’identité (GUID) du premier appareil de connexion Cloud, exécutez l’applet de connexion Get-CsHybridPSTNAppliance.</span><span class="sxs-lookup"><span data-stu-id="ff348-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="ff348-272">Pour marquer l’application comme ayant été déployée correctement, exécutez l’ensemble-CsCceApplianceDeploymentStatus en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff348-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="ff348-273">**Problème : Vous devez vérifier et installer les mises à jour de Windows manuellement sur le serveur hôte ou les machines virtuelles.**</span><span class="sxs-lookup"><span data-stu-id="ff348-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="ff348-p133">**Résolution ** Nous vous conseillons de profiter des avantages des mises à jour automatiques du système d’exploitation fournies par la version Cloud Connector de Skype Entreprise. Une fois qu’un appareil est inscrit pour une gestion en ligne et que la mise à jour automatique du système d’exploitation est activée, le serveur hôte et les machines virtuelles vérifieront et installeront automatiquement les mises à jour de Windows en fonction des paramètres d’heure de mise à jour du système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="ff348-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="ff348-p134">Si vous devez vérifier et installer les mises à jour de Windows manuellement, suivez les étapes de cette rubrique qui s’appliquent à votre type de déploiement. Vous devriez mettre à jour le serveur hôte en même temps que les machines virtuelles qui sont exécutées dessus pour réduire le temps d’arrêt nécessaire aux mises à jour.</span><span class="sxs-lookup"><span data-stu-id="ff348-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="ff348-p135">Si vous préférez, vous pouvez utiliser un serveur WSUS (services de mises à jour de serveur Windows) pour qu’il fournisse les mises à jour aux serveurs Cloud Connector. Assurez-vous simplement de configurer Windows Update de sorte qu’il n’effectue **pas** d’installation automatique.</span><span class="sxs-lookup"><span data-stu-id="ff348-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="ff348-280">Pour en savoir plus sur la mise à jour de votre déploiement Cloud Collector manuellement, consultez la rubrique suivante.</span><span class="sxs-lookup"><span data-stu-id="ff348-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="ff348-281">**Problème : lors de la mise à jour du connecteur Cloud vers une nouvelle version, les applets de construction Cloud Connector ne sont pas mis à jour.**</span><span class="sxs-lookup"><span data-stu-id="ff348-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="ff348-282">Cela se produit parfois si une fenêtre PowerShell reste ouverte lorsque la mise à jour automatique se produit.</span><span class="sxs-lookup"><span data-stu-id="ff348-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="ff348-283">**Résolution :** Pour charger les applets de commande mises à jour, vous pouvez effectuer l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff348-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="ff348-284">Fermez PowerShell sur le périphérique Cloud Connector, puis rouvrez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff348-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="ff348-285">Vous pouvez exécuter import-module CloudConnector-force.</span><span class="sxs-lookup"><span data-stu-id="ff348-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="ff348-286">**Problème : « le terme «Stop-CsWindowsService » n’est pas reconnu comme le nom d’une cmdlet, d’une fonction, d’un fichier de script ou d’un programme exécutable.» Lorsque vous tentez d’exécuter une cmdlet Enter-CcUpdate.**</span><span class="sxs-lookup"><span data-stu-id="ff348-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="ff348-287">**Résolution :** Supprimez le fichier \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache $HOME.</span><span class="sxs-lookup"><span data-stu-id="ff348-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="ff348-288">PowerShell crée ce fichier sous la forme d’un cache d’applets de connexion provenant de modules qu’il recherche afin qu’il n’ait pas à réanalyser tous les modules chaque fois que cela risque de ralentir.</span><span class="sxs-lookup"><span data-stu-id="ff348-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="ff348-289">Dans la plupart des cas, il y a eu une corruption de fichier qui proposait des résultats erronés à PowerShell lors de la lecture de ce cache.</span><span class="sxs-lookup"><span data-stu-id="ff348-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="ff348-290">**Problème : « import-module CloudConnector » génère une erreur « import-module : le module spécifié «CloudConnector » n’a pas été chargé car aucun fichier de module valide n’a été trouvé dans un répertoire de modules»**</span><span class="sxs-lookup"><span data-stu-id="ff348-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="ff348-291">**Résolution **</span><span class="sxs-lookup"><span data-stu-id="ff348-291">**Resolution:**</span></span>
    - <span data-ttu-id="ff348-292">Vérifiez que le module CloudConnector existe bien sous c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="ff348-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="ff348-293">Après validation du module CloudConnector dans cet emplacement, la variable d’environnement PSModulePath stockant le chemin d’accès aux emplacements des modules peut être modifiée :</span><span class="sxs-lookup"><span data-stu-id="ff348-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="ff348-294">a.</span><span class="sxs-lookup"><span data-stu-id="ff348-294">a.</span></span> <span data-ttu-id="ff348-295">Modification temporaire : démarrez PowerShell en tant qu’administrateur et exécutez la commande suivante : $env :P SModulePath = $env :P SModulePath + "; C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="ff348-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="ff348-296">b.</span><span class="sxs-lookup"><span data-stu-id="ff348-296">b.</span></span> <span data-ttu-id="ff348-297">Pour le changement permanent, démarrez PowerShell en tant qu’administrateur et exécutez les commandes suivantes, une par une : $CurrentValue = [Environment] :: GetEnvironmentVariable ("PSModulePath", "machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," machine ")</span><span class="sxs-lookup"><span data-stu-id="ff348-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="ff348-298">Installer manuellement les mises à jour Windows</span><span class="sxs-lookup"><span data-stu-id="ff348-298">Install Windows updates manually</span></span>

<span data-ttu-id="ff348-299">Si vous ne voulez pas utiliser les mises à jour automatiques dans votre environnement, suivez ces étapes pour vérifier et appliquer manuellement les mises à jour de Windows.</span><span class="sxs-lookup"><span data-stu-id="ff348-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="ff348-300">Vérifier et installer manuellement les mises à jour de Windows nécessite de redémarrer le serveur.</span><span class="sxs-lookup"><span data-stu-id="ff348-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="ff348-301">Lors du redémarrage d’un serveur hôte, les utilisateurs ne peuvent pas utiliser le Cloud Connector pour passer ou recevoir des appels.</span><span class="sxs-lookup"><span data-stu-id="ff348-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="ff348-302">Vous pouvez vérifier et installer manuellement les mises à jour pour contrôler quand elles ont lieu, puis redémarrer les machines au besoin au moment de votre choix pour éviter une perturbation des services.</span><span class="sxs-lookup"><span data-stu-id="ff348-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="ff348-303">Pour vérifier et installer manuellement les mises à jours, connectez-vous à chaque serveur hôte et ouvrez le **Panneau de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="ff348-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="ff348-304">Sélectionnez **système et sécurité \>Windows Update**, puis gérez les mises à jour et les redémarrages du serveur en fonction de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="ff348-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="ff348-305">S’il n’existe qu’un seul appareil sur le site, connectez-vous à chaque machine virtuelle et ouvrez le **Panneau de contrôle**.</span><span class="sxs-lookup"><span data-stu-id="ff348-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="ff348-306">Sélectionnez **système et sécurité \>Windows Update**, puis configurez les mises à jour et les redémarrages du serveur, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="ff348-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="ff348-p143">S’il existe plusieurs appareils sur le site, l’instance en cours de mise à jour et de redémarrage n’est plus accessible par les utilisateurs. Les utilisateurs se connecteront à d’autres instances du déploiement jusqu’à ce que toutes les machines virtuelles et que tous les services Skype Entreprise démarrent sur les machines virtuelles après la fin des mises à jour. Pour éviter de potentielles perturbations du service, vous pouvez supprimer les instances de la haute disponibilité pendant que vous appliquez les mises à jour, puis les restaurer une fois celles-ce achevées. Pour ce faire :</span><span class="sxs-lookup"><span data-stu-id="ff348-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="ff348-311">Sur chaque serveur hôte, ouvrez une console PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="ff348-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="ff348-312">Supprimez l’instance de la haute disponibilité grâce à l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ff348-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="ff348-313">Suivez les étapes pour une instance unique afin d’appliquer manuellement les mises à jour et redémarrer la machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="ff348-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="ff348-314">Définissez à nouveau l’instance en haute disponibilité grâce à l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ff348-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="ff348-315">Pour des déploiements sur plusieurs sites, suivez les étapes pour un site unique pour chaque site du déploiement, en appliquant les mises à jour un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="ff348-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="ff348-316">Conseils lors de l’installation d’un logiciel antivirus sur l’ordinateur hôte du Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ff348-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="ff348-317">Si vous avez besoin d’installer un logiciel antivirus sur l’ordinateur hôte du Cloud Connector, vous devez ajouter les exclusions suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff348-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="ff348-318">Répertoire d’appliance locale sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ff348-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="ff348-319">Répertoire de site distant sur chaque ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ff348-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="ff348-320">Sur l’ordinateur héberge le dossier racine du site partagé.</span><span class="sxs-lookup"><span data-stu-id="ff348-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="ff348-321">%ProgramFiles%\Skype entreprise version Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="ff348-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="ff348-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="ff348-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="ff348-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="ff348-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="ff348-324">Processus Microsoft. RTC. CCE. ManagementService. exe.</span><span class="sxs-lookup"><span data-stu-id="ff348-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
