---
title: Facilité de gestion et outils Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="4d0af-103">Facilité de gestion et outils Skype Room System</span><span class="sxs-lookup"><span data-stu-id="4d0af-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="4d0af-104">Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="4d0af-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="4d0af-105">Portail d’administration</span><span class="sxs-lookup"><span data-stu-id="4d0af-105">Administrative Portal</span></span>

<span data-ttu-id="4d0af-106">Pour Skype pour les déploiements sur site de serveur de l’entreprise, vous pouvez utiliser le portail d’administration système de salle Skype activement gérer et surveiller des déploiements de systèmes d’espace Skype au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4d0af-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="4d0af-107">Pour plus d’informations, consultez les articles suivants :</span><span class="sxs-lookup"><span data-stu-id="4d0af-107">See the following articles for more details:</span></span>
  
- [<span data-ttu-id="4d0af-108">Déploiement du portail d’administration Web système salle de Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d0af-108">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [<span data-ttu-id="4d0af-109">Configuration de votre environnement de Lync Server 2013 pour le portail d’administration Web Lync salle de système</span><span class="sxs-lookup"><span data-stu-id="4d0af-109">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [<span data-ttu-id="4d0af-110">L’installation du portail Web d’administration de système Lync salle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d0af-110">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [<span data-ttu-id="4d0af-111">À l’aide du portail Web d’administration de système Lync salle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d0af-111">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="4d0af-112">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="4d0af-112">System Center Operations Manager</span></span>

<span data-ttu-id="4d0af-113">Système de chambre de Skype peuvent être surveillé via System Center Operations Manager (SCOM) par le [Pack d’administration système Skype salle](https://www.microsoft.com/en-us/download/details.aspx?id=42320) de téléchargement et de l’installer sur votre serveur SCOM.</span><span class="sxs-lookup"><span data-stu-id="4d0af-113">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/en-us/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="4d0af-114">SCOM vous permet de définir des alertes, de surveiller la santé du système de salle de Skype, de générer des rapports de temps de fonctionnement et bien plus encore.</span><span class="sxs-lookup"><span data-stu-id="4d0af-114">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="4d0af-115">Système de chambre de Skype est fourni avec un agent de surveillance préinstallé qui peut être configuré pour pointer vers le serveur SCOM.</span><span class="sxs-lookup"><span data-stu-id="4d0af-115">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="4d0af-116">Reportez-vous au guide d’installation fourni par le fabricant de votre système de salle Skype pour savoir comment configurer l’agent de surveillance sur le système local de Skype.</span><span class="sxs-lookup"><span data-stu-id="4d0af-116">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="4d0af-117">Liste de vérification Exchange</span><span class="sxs-lookup"><span data-stu-id="4d0af-117">Exchange Checklist</span></span>

- <span data-ttu-id="4d0af-118">Vérifiez qu’Autodiscover est configuré et qu’un DNS A/CNAME RECORD interne est disponible pour autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="4d0af-118">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="4d0af-119">Ping Autodiscover (par ex., ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4d0af-119">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="4d0af-120">Testez votre service Autodiscover avec l’outil d’analyse de connectivité de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d0af-120">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="4d0af-121">Choisissez le premier test, « Je n’arrive pas à se connecter avec Office Outlook ».</span><span class="sxs-lookup"><span data-stu-id="4d0af-121">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="4d0af-122">Si la salle de réunion a déjà une boîte aux lettres de ressources, étendre ce compte pour le système de salle Skype (exemple de script en bas de la page).</span><span class="sxs-lookup"><span data-stu-id="4d0af-122">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="4d0af-123">Skype pour entreprise aide-mémoire</span><span class="sxs-lookup"><span data-stu-id="4d0af-123">Skype for Business Checklist</span></span>

- <span data-ttu-id="4d0af-124">Exécutez les outils suivants :</span><span class="sxs-lookup"><span data-stu-id="4d0af-124">Run the following tools:</span></span>
    
  - <span data-ttu-id="4d0af-125">Skype pour entreprise Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="4d0af-125">Skype for Business Best Practices Analyzer</span></span> 
    
  - <span data-ttu-id="4d0af-126">Skype pour outil d’analyse de fonctionnement entreprise (Excel)</span><span class="sxs-lookup"><span data-stu-id="4d0af-126">Skype for Business Health Analysis Tool (Excel)</span></span> 
    
  - <span data-ttu-id="4d0af-127">Skype pour Analyseur de connectivité d’entreprise 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="4d0af-127">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="4d0af-128">Consultez [dépannage nouvelles utiles et des outils d’analyse d’Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="4d0af-128">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="4d0af-129">Confirmer vous avez un Skype pour le pool d’entreprise et un serveur Office Web Apps et que vous pouvez partager un PowerPoint à l’aide de la Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4d0af-129">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="4d0af-130">Si la salle de réunion a déjà une boîte aux lettres de ressources, l’activer pour Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="4d0af-130">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="4d0af-131">Si nécessaire, demandez un numéro SDA (numéro de téléphone) pour Meeting Room System, et mettez à jour le champ de l’outil Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4d0af-131">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="4d0af-132">Réseau</span><span class="sxs-lookup"><span data-stu-id="4d0af-132">Network</span></span>

- <span data-ttu-id="4d0af-133">Assurez-vous que vous disposez d’une connexion de réseau câblé pour le système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="4d0af-133">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="4d0af-134">Lire le Guide de planification de Skype pour les entreprises de réseau.</span><span class="sxs-lookup"><span data-stu-id="4d0af-134">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="4d0af-135">Demander un Skype pour l’évaluation du réseau de l’entreprise à partir d’un Skype pour le partenaire commercial.</span><span class="sxs-lookup"><span data-stu-id="4d0af-135">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="4d0af-136">Lire les données de performance capturées dans le Skype pour outil d’analyse de fonctionnement entreprise (Excel).</span><span class="sxs-lookup"><span data-stu-id="4d0af-136">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="4d0af-137">Exécutez l’outil d’analyse réseau.</span><span class="sxs-lookup"><span data-stu-id="4d0af-137">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="4d0af-138">Exécutez l’outil de diagnostic avant appel.</span><span class="sxs-lookup"><span data-stu-id="4d0af-138">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="4d0af-139">Sécurité du système local de Skype</span><span class="sxs-lookup"><span data-stu-id="4d0af-139">Skype Room System Security</span></span>

<span data-ttu-id="4d0af-140">Système de chambre de Skype est un système intégré qui peut être entièrement intégré dans un déploiement de Windows, à l’aide de la Skype pour le modèle de sécurité d’entreprise, la gestion des droits et outils de gestion de SCOM.</span><span class="sxs-lookup"><span data-stu-id="4d0af-140">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="4d0af-141">Parmi les fonctionnalités figurent :</span><span class="sxs-lookup"><span data-stu-id="4d0af-141">Features include:</span></span>
  
- <span data-ttu-id="4d0af-142">Un filtre d’écriture pour empêcher les écritures sur disque en mode utilisateur</span><span class="sxs-lookup"><span data-stu-id="4d0af-142">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="4d0af-p105">Un verrouilleur d’applications pour empêcher toute application de s’exécuter. Tous les ports USB sont désactivés en mode utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4d0af-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="4d0af-145">Aucune des applications standard ou des visionneuses ne résident sur le matériel du système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="4d0af-145">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="4d0af-146">Tout le contenu est généré via des protocoles HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="4d0af-146">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="4d0af-p107">Le PC applicatif exécute le système d’exploitation Windows Embedded Standard 7. Tout le matériel, y compris les périphériques, est fourni par les partenaires OEM.</span><span class="sxs-lookup"><span data-stu-id="4d0af-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="4d0af-149">Facultatif : rejoindre un domaine pour les Active Directory Domain Services (AD DS). La gestion locale de la sécurité et le contrôle du compte est alors possible.</span><span class="sxs-lookup"><span data-stu-id="4d0af-149">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="4d0af-150">Vous pouvez également gérer le compte d’administrateur local à l’aide de la Skype pour le centre d’administration Business.</span><span class="sxs-lookup"><span data-stu-id="4d0af-150">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="4d0af-151">Système de chambre de Skype est mis à jour via des processus standard de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="4d0af-151">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="4d0af-152">Système de chambre de Skype se connecte avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="4d0af-152">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="4d0af-153">Skype pour entreprise utilise le cryptage de bout en bout et d’autorisation pour tous les modes de communication</span><span class="sxs-lookup"><span data-stu-id="4d0af-153">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="4d0af-154">Système de salle Skype prend en charge Skype pour les normes de sécurité et de conformité commerciale.</span><span class="sxs-lookup"><span data-stu-id="4d0af-154">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="4d0af-155">Voir la rubrique Planification de la sécurité dans Lync Server 2013 pour plus d’informations.</span><span class="sxs-lookup"><span data-stu-id="4d0af-155">See Planning for security in Lync Server 2013 for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="4d0af-156">Licence</span><span class="sxs-lookup"><span data-stu-id="4d0af-156">License</span></span>

<span data-ttu-id="4d0af-157">Vérifiez que vous utilisez un KMS pour l’activation du logiciel.</span><span class="sxs-lookup"><span data-stu-id="4d0af-157">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="4d0af-158">Dans ce cas, vous devrez peut-être vérifier ou ajouter le Skype pour clé KMS de client entreprise.</span><span class="sxs-lookup"><span data-stu-id="4d0af-158">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="4d0af-159">Si vous n’êtes pas à l’aide de KMS, puis demande la clé de licence pour le Skype pour client d’entreprise MAK en volume.</span><span class="sxs-lookup"><span data-stu-id="4d0af-159">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="4d0af-160">Clés de licence</span><span class="sxs-lookup"><span data-stu-id="4d0af-160">License keys</span></span>

<span data-ttu-id="4d0af-161">Système de chambre de Skype exécute le Skype pour client ordinateur de bureau d’entreprise en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="4d0af-161">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="4d0af-162">Si le système de salle de Skype est membre d’un domaine, il découvre votre serveur gestionnaire de clés.</span><span class="sxs-lookup"><span data-stu-id="4d0af-162">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="4d0af-163">(et si elle possède le Volume Licensing Lync clés activera automatiquement).</span><span class="sxs-lookup"><span data-stu-id="4d0af-163">(and if it has the Volume Licensing KMS Lync Key it will activate automatically).</span></span> <span data-ttu-id="4d0af-164">Les licences en volume fournit également une MAK, ce qui vous permet d’entrer lorsqu’il affiche les xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="4d0af-164">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="4d0af-165">(Vous avez besoin de l’accès Internet à activer à l’aide de la clé d’activation multiple, mais pas de KMS).</span><span class="sxs-lookup"><span data-stu-id="4d0af-165">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="4d0af-166">Pour plus d’informations, consultez l’activation en Volume Office 2013.</span><span class="sxs-lookup"><span data-stu-id="4d0af-166">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="4d0af-167">Pour entrer la clé MAK, accédez aux paramètres de l’OEM \> outil de gestion de licences de SRS.</span><span class="sxs-lookup"><span data-stu-id="4d0af-167">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="4d0af-168">Cliquez sur Vérifier l’état.</span><span class="sxs-lookup"><span data-stu-id="4d0af-168">Click Check Status.</span></span> <span data-ttu-id="4d0af-169">Lorsque le statut indique que « le produit n’est pas activé », entrez la clé.</span><span class="sxs-lookup"><span data-stu-id="4d0af-169">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="4d0af-170">Si lors de l’activation, vous obtenez une erreur indiquant que, « « le Service de licences logicielles a signalé que la clé de produit non valide, » puis vérifiez que :</span><span class="sxs-lookup"><span data-stu-id="4d0af-170">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="4d0af-171">Vous avez saisi la clé correctement.</span><span class="sxs-lookup"><span data-stu-id="4d0af-171">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="4d0af-172">Vous avez entré le Skype pour clé MAK de l’entreprise et pas une autre clé.</span><span class="sxs-lookup"><span data-stu-id="4d0af-172">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="4d0af-173">Le système a accès à Internet.</span><span class="sxs-lookup"><span data-stu-id="4d0af-173">The system has Internet access.</span></span>
    
- <span data-ttu-id="4d0af-174">Vous pouvez effectuer l’activation par téléphone, mais vous devez d’abord avoir tenté d’activer l’aide de l’outil de gestion des licences SRS.</span><span class="sxs-lookup"><span data-stu-id="4d0af-174">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="4d0af-175">Pour effectuer l’activation par téléphone, lancez une réunion test (pas un appel de test car cela est trop court).</span><span class="sxs-lookup"><span data-stu-id="4d0af-175">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="4d0af-176">Dans l’Assistant Activation de Microsoft Office, sélectionnez l’Activation par téléphone, appelez Microsoft, tapez le numéro long et entrer une réponse.</span><span class="sxs-lookup"><span data-stu-id="4d0af-176">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="4d0af-177">Autorité de certification</span><span class="sxs-lookup"><span data-stu-id="4d0af-177">Certificate Authority</span></span>

<span data-ttu-id="4d0af-178">Vérifiez que l’autorité de certification utilisée pour émettre le certificat Office Web Apps Server 2013 dispose d’un chemin HTTP inclus dans la propriété Liste de révocation de certificats.</span><span class="sxs-lookup"><span data-stu-id="4d0af-178">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="4d0af-179">Importer le fichier de certificat (.crt) sur le système de salle de Skype si pour Business Server à l’aide de Skype.</span><span class="sxs-lookup"><span data-stu-id="4d0af-179">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="4d0af-180">Vous pouvez l’obtenir facilement à partir du partage CertEnroll du serveur CA, ou dans le dossier racine de confiance de n’importe quel PC lié au domaine.</span><span class="sxs-lookup"><span data-stu-id="4d0af-180">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="4d0af-181">Certificats</span><span class="sxs-lookup"><span data-stu-id="4d0af-181">Certificates</span></span>

<span data-ttu-id="4d0af-p114">Vérifiez que votre autorité de certification dispose d’un chemin HTTP pour la liste de révocation de certificats. Si ce n’est pas le cas, mettez à jour votre CA pour en inclure un.</span><span class="sxs-lookup"><span data-stu-id="4d0af-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="4d0af-184">Installer des certificats dans le paramétrage de l’administration du système, espace Skype sous Paramètres du système \> Gestionnaire de certificats.</span><span class="sxs-lookup"><span data-stu-id="4d0af-184">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="4d0af-185">Vous aurez besoin d’une autorité de certification racine d’entreprise pour votre certificat interne.</span><span class="sxs-lookup"><span data-stu-id="4d0af-185">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="4d0af-186">Une des façons d’obtenir les certificats dont vous avez besoin est de découvrir l’autorité de certification qui a émis les certificats.</span><span class="sxs-lookup"><span data-stu-id="4d0af-186">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="4d0af-187">Pour Skype pour Business Server, sur un PC dans Skype pour entreprise, cliquez sur paramètres \> outils \> paramètres de conférence à distance.</span><span class="sxs-lookup"><span data-stu-id="4d0af-187">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="4d0af-188">Cette opération ouvre une page web sécurisée par l’autorité de certification qui a émis les certificats Lync internes.</span><span class="sxs-lookup"><span data-stu-id="4d0af-188">This opens a web page secured by the CA that issued the internal Lync certificates.</span></span> <span data-ttu-id="4d0af-189">Cliquez sur l’icône Verrouiller dans la barre d’adresse du navigateur pour afficher un rapport de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4d0af-189">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="4d0af-190">Cliquez sur Afficher les certificats et passez en revue la propriété Point de distribution de liste de révocation.</span><span class="sxs-lookup"><span data-stu-id="4d0af-190">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="4d0af-191">Le deuxième paramètre CN doit être le nom de serveur de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="4d0af-191">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="4d0af-192">Ouvrez maintenant l’Explorateur Windows pour cette adresse de \\ \< nom de serveur d’autorité de certification \>\CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="4d0af-192">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="4d0af-193">Copiez les deux fichiers .crl et .crt sur un lecteur flash et placez-les dans la partie gauche du tableau de bord SMART.</span><span class="sxs-lookup"><span data-stu-id="4d0af-193">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="4d0af-194">Importer le fichier .crt sur le système de salle de Skype sous dossier de l’autorité de Certification de salle de confiance.</span><span class="sxs-lookup"><span data-stu-id="4d0af-194">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="4d0af-195">Importez les fichiers .crl sur le système de salle Skype sous le dossier autorités de certification intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="4d0af-195">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="4d0af-196">(Vous devez modifier le filtre d’extension de fichier dans le Gestionnaire de certificats pour voir les fichiers .crl).</span><span class="sxs-lookup"><span data-stu-id="4d0af-196">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="4d0af-p118">Remarque : le serveur Office Web Apps 2013 peut partager la même autorité de certification que Lync. Si ce n’est pas le cas, vous ne serez pas en mesure de partager PowerPoint lors d’une réunion. Vérifiez auprès de votre service informatique et obtenez les fichiers CRT et CRL à partir du CertEnroll partage réseau de l’autorité de certification, comme expliqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="4d0af-p118">Note: The Office Web Apps 2013 server may share the same CA as Lync. If it doesn't you won't be able to share PowerPoint in a meeting. Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="4d0af-200">L’appartenance au domaine peut simplifier certaines choses étant donné que vous pouvez traiter le système de salle Skype sous la forme d’un système Windows et il peut reposer sur Active Directory pour certains aspects du certificat.</span><span class="sxs-lookup"><span data-stu-id="4d0af-200">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="4d0af-201">Toutefois, il est préférable de gérer cela manuellement.</span><span class="sxs-lookup"><span data-stu-id="4d0af-201">However, it's best to manually manage this.</span></span>
  

