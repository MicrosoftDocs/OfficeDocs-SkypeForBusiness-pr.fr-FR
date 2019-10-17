---
title: Facilité de gestion et outils Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.
ms.openlocfilehash: c9289d3fffa78dd7ffd94fa17784c1b06c2278b1
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547257"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="4583f-103">Facilité de gestion et outils Skype Room System</span><span class="sxs-lookup"><span data-stu-id="4583f-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="4583f-104">Consultez cette rubrique pour en savoir plus sur les outils de gestion de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="4583f-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="4583f-105">Portail d’administration</span><span class="sxs-lookup"><span data-stu-id="4583f-105">Administrative Portal</span></span>

<span data-ttu-id="4583f-106">Pour les déploiements sur site de Skype entreprise Server, vous pouvez utiliser le portail d’administration du système de salle Skype pour gérer et surveiller activement les déploiements de systèmes de salle Skype au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4583f-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="4583f-107">Pour plus d’informations, consultez l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="4583f-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="4583f-108">Déploiement du portail Web d’administration de SRS v1 dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4583f-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="4583f-109">Liste de vérification Exchange</span><span class="sxs-lookup"><span data-stu-id="4583f-109">Exchange Checklist</span></span>

- <span data-ttu-id="4583f-110">Vérifiez qu’Autodiscover est configuré et qu’un DNS A/CNAME RECORD interne est disponible pour autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="4583f-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="4583f-111">Ping Autodiscover (par ex., ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4583f-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="4583f-112">Testez votre service Autodiscover avec l’outil d’analyse de connectivité de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4583f-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="4583f-113">Choisissez le premier test « je ne peux pas me connecter à Office Outlook ».</span><span class="sxs-lookup"><span data-stu-id="4583f-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="4583f-114">Si la salle de réunion possède déjà une boîte aux lettres de ressources, développez ce compte pour le système de salle Skype (exemple de script en bas de la page).</span><span class="sxs-lookup"><span data-stu-id="4583f-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="4583f-115">Liste de vérification Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="4583f-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="4583f-116">Exécutez les outils suivants :</span><span class="sxs-lookup"><span data-stu-id="4583f-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="4583f-117">Analyseur de meilleures pratiques Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="4583f-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="4583f-118">Outil d’analyse de l’intégrité de Skype entreprise (Excel)</span><span class="sxs-lookup"><span data-stu-id="4583f-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="4583f-119">Analyseur de connectivité Skype entreprise 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="4583f-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="4583f-120">Consultez les [nouveaux outils d’analyse et de dépannage utiles pour Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span><span class="sxs-lookup"><span data-stu-id="4583f-120">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="4583f-121">Vérifiez que vous disposez d’un pool Skype entreprise et d’un serveur Office Web Apps et que vous pouvez partager une présentation PowerPoint à l’aide du client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="4583f-122">Si la salle de réunion possède déjà une boîte aux lettres de ressources, activez-la pour Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="4583f-123">Si nécessaire, demandez un numéro SDA (numéro de téléphone) pour Meeting Room System, et mettez à jour le champ de l’outil Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4583f-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="4583f-124">Réseau</span><span class="sxs-lookup"><span data-stu-id="4583f-124">Network</span></span>

- <span data-ttu-id="4583f-125">Vérifiez que vous disposez d’une connexion réseau filaire pour le système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="4583f-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="4583f-126">Consultez le Guide de planification réseau pour Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="4583f-127">Demandez une analyse du réseau Skype entreprise auprès d’un partenaire Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="4583f-128">Lire les données de performance capturées dans l’outil d’analyse de l’intégrité de Skype entreprise (Excel).</span><span class="sxs-lookup"><span data-stu-id="4583f-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="4583f-129">Exécutez l’outil d’analyse réseau.</span><span class="sxs-lookup"><span data-stu-id="4583f-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="4583f-130">Exécutez l’outil de diagnostic avant appel.</span><span class="sxs-lookup"><span data-stu-id="4583f-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="4583f-131">Sécurité du système de salle Skype</span><span class="sxs-lookup"><span data-stu-id="4583f-131">Skype Room System Security</span></span>

<span data-ttu-id="4583f-132">Le système de salle Skype est un système incorporé qui peut être entièrement intégré dans un déploiement Windows, avec le modèle de sécurité Skype entreprise, la gestion des droits et les outils de gestion tels que SCOM.</span><span class="sxs-lookup"><span data-stu-id="4583f-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="4583f-133">Parmi les fonctionnalités figurent :</span><span class="sxs-lookup"><span data-stu-id="4583f-133">Features include:</span></span>
  
- <span data-ttu-id="4583f-134">Un filtre d’écriture pour empêcher les écritures sur disque en mode utilisateur</span><span class="sxs-lookup"><span data-stu-id="4583f-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="4583f-p104">Un verrouilleur d’applications pour empêcher toute application de s’exécuter. Tous les ports USB sont désactivés en mode utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4583f-p104">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="4583f-137">Il n’y a pas d’applications ou d’observateurs standard dans le système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="4583f-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="4583f-138">Tout le contenu est généré via des protocoles HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="4583f-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="4583f-p106">Le PC applicatif exécute le système d’exploitation Windows Embedded Standard 7. Tout le matériel, y compris les périphériques, est fourni par les partenaires OEM.</span><span class="sxs-lookup"><span data-stu-id="4583f-p106">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="4583f-141">Facultatif : rejoindre un domaine pour les Active Directory Domain Services (AD DS). La gestion locale de la sécurité et le contrôle du compte est alors possible.</span><span class="sxs-lookup"><span data-stu-id="4583f-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="4583f-142">Vous pouvez également gérer le compte d’administrateur local à l’aide du centre d’administration Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="4583f-143">Le système de salle Skype est mis à jour par le biais de processus Microsoft Update standard.</span><span class="sxs-lookup"><span data-stu-id="4583f-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="4583f-144">Le système de salle Skype se connecte à Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="4583f-145">Skype entreprise utilise le chiffrement et l’autorisation de bout en bout pour tous les modes de communication.</span><span class="sxs-lookup"><span data-stu-id="4583f-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="4583f-146">Le système de salle Skype prend en charge les normes de sécurité et de conformité de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="4583f-147">Pour plus d’informations, reportez-vous à la rubrique [planification de la sécurité dans Skype entreprise Server](../../plan-your-deployment/security/security.md) .</span><span class="sxs-lookup"><span data-stu-id="4583f-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="4583f-148">Licence</span><span class="sxs-lookup"><span data-stu-id="4583f-148">License</span></span>

<span data-ttu-id="4583f-149">Vérifiez que vous utilisez un KMS pour l’activation du logiciel.</span><span class="sxs-lookup"><span data-stu-id="4583f-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="4583f-150">Si tel est le cas, vous devrez peut-être vérifier ou ajouter la clé KMS du client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="4583f-151">Si vous n’utilisez pas KMS, demandez la clé de licence en volume pour le client de MAK Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="4583f-152">Clés de licence</span><span class="sxs-lookup"><span data-stu-id="4583f-152">License keys</span></span>

<span data-ttu-id="4583f-153">Le système de salle Skype exécute le client de bureau Skype entreprise en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="4583f-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="4583f-154">Si le système de salle Skype est membre du domaine, il découvre votre KMS.</span><span class="sxs-lookup"><span data-stu-id="4583f-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="4583f-155">(et si la clé KMS du programme de licence en volume sera activée automatiquement).</span><span class="sxs-lookup"><span data-stu-id="4583f-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="4583f-156">Le programme de licence en volume fournit également une MAK, que vous entrez pour afficher xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="4583f-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="4583f-157">(Vous devez disposer d’un accès à Internet pour l’activer à l’aide de MAK mais pas du KMS).</span><span class="sxs-lookup"><span data-stu-id="4583f-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="4583f-158">Pour plus d’informations, voir activation en volume d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="4583f-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="4583f-159">Pour entrer la clé MAK, accédez à l’outil \> de gestion des licences de paramètres OEM.</span><span class="sxs-lookup"><span data-stu-id="4583f-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="4583f-160">Cliquez sur Vérifier l’état.</span><span class="sxs-lookup"><span data-stu-id="4583f-160">Click Check Status.</span></span> <span data-ttu-id="4583f-161">Lorsque l’état indique « le produit n’est pas activé », entrez la clé.</span><span class="sxs-lookup"><span data-stu-id="4583f-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="4583f-162">Si, au cours de l’activation, vous recevez un message d’erreur indiquant que le service de gestion de licences des logiciels a signalé que la clé de produit n’est pas valide, vérifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4583f-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="4583f-163">Vous avez saisi la clé correctement.</span><span class="sxs-lookup"><span data-stu-id="4583f-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="4583f-164">Vous avez entré la clé MAK Skype entreprise et non une autre clé.</span><span class="sxs-lookup"><span data-stu-id="4583f-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="4583f-165">Le système a accès à Internet.</span><span class="sxs-lookup"><span data-stu-id="4583f-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="4583f-166">Vous pouvez effectuer l’activation par téléphone, mais vous devez d’abord avoir tenté d’activer l’aide de l’outil de gestion des licences SRS.</span><span class="sxs-lookup"><span data-stu-id="4583f-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="4583f-167">Pour effectuer l’activation par téléphone, lancez une réunion test (pas un appel de test car cela est trop court).</span><span class="sxs-lookup"><span data-stu-id="4583f-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="4583f-168">Dans l’Assistant Activation de Microsoft Office, sélectionnez activation par téléphone, appelez Microsoft, tapez le numéro long et entrez une réponse.</span><span class="sxs-lookup"><span data-stu-id="4583f-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="4583f-169">Autorité de certification</span><span class="sxs-lookup"><span data-stu-id="4583f-169">Certificate Authority</span></span>

<span data-ttu-id="4583f-170">Vérifiez que l’autorité de certification utilisée pour émettre le certificat Office Web Apps Server 2013 dispose d’un chemin HTTP inclus dans la propriété Liste de révocation de certificats.</span><span class="sxs-lookup"><span data-stu-id="4583f-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="4583f-171">Importez le fichier de certificat (. CRT) dans le système de salle Skype si vous utilisez Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4583f-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="4583f-172">Vous pouvez l’obtenir facilement à partir du partage CertEnroll du serveur CA, ou dans le dossier racine de confiance de n’importe quel PC lié au domaine.</span><span class="sxs-lookup"><span data-stu-id="4583f-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="4583f-173">Certificats</span><span class="sxs-lookup"><span data-stu-id="4583f-173">Certificates</span></span>

<span data-ttu-id="4583f-p113">Vérifiez que votre autorité de certification dispose d’un chemin HTTP pour la liste de révocation de certificats. Si ce n’est pas le cas, mettez à jour votre CA pour en inclure un.</span><span class="sxs-lookup"><span data-stu-id="4583f-p113">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="4583f-176">Dans le cadre de la procédure d’administration du système de salle Skype, \> dans le gestionnaire de certificats des paramètres système, installez les certificats.</span><span class="sxs-lookup"><span data-stu-id="4583f-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="4583f-177">Vous aurez besoin d’une autorité de certification racine d’entreprise pour votre certificat interne.</span><span class="sxs-lookup"><span data-stu-id="4583f-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="4583f-178">Une des façons d’obtenir les certificats dont vous avez besoin est de découvrir l’autorité de certification qui a émis les certificats.</span><span class="sxs-lookup"><span data-stu-id="4583f-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="4583f-179">Pour Skype entreprise Server, sur un PC dans Skype entreprise, cliquez sur paramètres de \> Conférence \> rendez-vous des outils de paramètres.</span><span class="sxs-lookup"><span data-stu-id="4583f-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="4583f-180">Cette action ouvre une page Web sécurisée par l’autorité de certification qui a émis les certificats internes.</span><span class="sxs-lookup"><span data-stu-id="4583f-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="4583f-181">Cliquez sur l’icône Verrouiller dans la barre d’adresse du navigateur pour afficher un rapport de sécurité.</span><span class="sxs-lookup"><span data-stu-id="4583f-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="4583f-182">Cliquez sur Afficher les certificats et passez en revue la propriété Point de distribution de liste de révocation.</span><span class="sxs-lookup"><span data-stu-id="4583f-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="4583f-183">Le deuxième paramètre CN doit être le nom de serveur de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="4583f-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="4583f-184">Ouvrez l’Explorateur Windows pour cette adresse \\ \< nom \>du serveur \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="4583f-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="4583f-185">Copiez les deux fichiers .crl et .crt sur un lecteur flash et placez-les dans la partie gauche du tableau de bord SMART.</span><span class="sxs-lookup"><span data-stu-id="4583f-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="4583f-186">Importez le fichier. CRT dans le système de salle Skype sous le dossier autorité de certification de la salle d’approbation.</span><span class="sxs-lookup"><span data-stu-id="4583f-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="4583f-187">Importez les fichiers. lrc dans le système de salle Skype dans le dossier autorités de certification intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="4583f-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="4583f-188">(Vous devez remplacer le filtre d’extension de fichier dans le gestionnaire de certificats par. crl pour voir les fichiers).</span><span class="sxs-lookup"><span data-stu-id="4583f-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="4583f-189">Remarque : le serveur Office Web Apps 2013 risque de partager la même autorité de certification que Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4583f-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="4583f-190">Si ce n’est pas le cas, vous ne serez pas en mesure de partager PowerPoint lors d’une réunion.</span><span class="sxs-lookup"><span data-stu-id="4583f-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="4583f-191">Vérifiez auprès de votre service informatique et obtenez les fichiers CRT et CRL à partir du CertEnroll partage réseau de l’autorité de certification, comme expliqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="4583f-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="4583f-192">L’appartenance aux domaines peut simplifier certains éléments, car vous pouvez considérer le système de salle Skype comme un système Windows et il peut s’appuyer sur Active Directory pour certains aspects du certificat.</span><span class="sxs-lookup"><span data-stu-id="4583f-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="4583f-193">Toutefois, il est préférable de gérer cela manuellement.</span><span class="sxs-lookup"><span data-stu-id="4583f-193">However, it's best to manually manage this.</span></span>
  

