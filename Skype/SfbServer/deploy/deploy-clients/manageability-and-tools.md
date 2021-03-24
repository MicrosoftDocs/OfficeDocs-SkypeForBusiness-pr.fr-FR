---
title: Gestion et outils de Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lisez cette rubrique pour en savoir plus sur les outils de gestion pour Skype Room System.
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093548"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="df6ac-103">Gestion et outils de Skype Room System</span><span class="sxs-lookup"><span data-stu-id="df6ac-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="df6ac-104">Lisez cette rubrique pour en savoir plus sur les outils de gestion pour Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="df6ac-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="df6ac-105">Portail d’administration</span><span class="sxs-lookup"><span data-stu-id="df6ac-105">Administrative Portal</span></span>

<span data-ttu-id="df6ac-106">Pour les déploiements locaux de Skype Entreprise Server, vous pouvez utiliser le portail d’administration Skype Room System pour gérer et surveiller activement les déploiements de Skype Room System au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="df6ac-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="df6ac-107">Pour plus d’informations, voir l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="df6ac-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="df6ac-108">Déployer le portail Web d’administration de SRS v1 dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="df6ac-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="df6ac-109">Liste de vérification Exchange</span><span class="sxs-lookup"><span data-stu-id="df6ac-109">Exchange Checklist</span></span>

- <span data-ttu-id="df6ac-110">Confirmez que la découverte automatique est bien définie et qu’un enregistrement DNS A/CNAME interne est disponible pour autodiscover.domain.com.</span><span class="sxs-lookup"><span data-stu-id="df6ac-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="df6ac-111">Découverte automatique ping (par exemple, ping Autodiscover.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="df6ac-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="df6ac-112">Testez votre service de découverte automatique à l’aide de l’outil Analyseur de connectivité Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df6ac-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="df6ac-113">Choisissez le premier test, « Je ne peux pas me connecter avec Office Outlook ».</span><span class="sxs-lookup"><span data-stu-id="df6ac-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="df6ac-114">Si la salle de réunion dispose déjà d’une boîte aux lettres de ressources, étendez ce compte pour Skype Room System (exemple de script en bas de la page).</span><span class="sxs-lookup"><span data-stu-id="df6ac-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="df6ac-115">Liste de vérification Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="df6ac-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="df6ac-116">Exécutez les outils suivants :</span><span class="sxs-lookup"><span data-stu-id="df6ac-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="df6ac-117">Skype Entreprise Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="df6ac-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="df6ac-118">Outil d’analyse de l’état de Skype Entreprise (Excel)</span><span class="sxs-lookup"><span data-stu-id="df6ac-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="df6ac-119">Analyseur de connectivité Skype Entreprise 32 bits ou 64 bits</span><span class="sxs-lookup"><span data-stu-id="df6ac-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="df6ac-120">Passer en revue les nouveaux outils de dépannage et [d’analyse utiles pour Office 365.](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="df6ac-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span></span> <span data-ttu-id="df6ac-121">Confirmez que vous avez un pool Skype Entreprise et un serveur Office Web Apps et que vous pouvez partager une présentation PowerPoint à l’aide du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="df6ac-122">Si la salle de réunion dispose déjà d’une boîte aux lettres de ressources, activez-la pour Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="df6ac-123">Si nécessaire, demandez un DID (numéro de téléphone) pour le système de salle de réunion et mettez à jour le champ Téléphone général dans l’outil Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6ac-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="df6ac-124">Réseau</span><span class="sxs-lookup"><span data-stu-id="df6ac-124">Network</span></span>

- <span data-ttu-id="df6ac-125">Assurez-vous que vous avez une connexion réseau câblé pour Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="df6ac-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="df6ac-126">Lisez le Guide de planification du réseau pour Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="df6ac-127">Demandez une évaluation du réseau Skype Entreprise auprès d’un partenaire Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="df6ac-128">Lisez les données de performances capturées dans l’outil d’analyse de l’état d’état de Skype Entreprise (Excel).</span><span class="sxs-lookup"><span data-stu-id="df6ac-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="df6ac-129">Exécutez l’outil d’analyse réseau.</span><span class="sxs-lookup"><span data-stu-id="df6ac-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="df6ac-130">Exécutez l’outil de diagnostic de pré-appel.</span><span class="sxs-lookup"><span data-stu-id="df6ac-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="df6ac-131">Sécurité du système Skype Room</span><span class="sxs-lookup"><span data-stu-id="df6ac-131">Skype Room System Security</span></span>

<span data-ttu-id="df6ac-132">Skype Room System est un système incorporé qui peut être entièrement intégré dans un déploiement Windows, à l’aide du modèle de sécurité Skype Entreprise, de la gestion des droits et des outils de gestion tels que SCOM.</span><span class="sxs-lookup"><span data-stu-id="df6ac-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="df6ac-133">Les fonctionnalités sont les suivantes : </span><span class="sxs-lookup"><span data-stu-id="df6ac-133">Features include:</span></span>
  
- <span data-ttu-id="df6ac-134">Un filtre d’écriture pour empêcher les écritures sur disque en mode utilisateur</span><span class="sxs-lookup"><span data-stu-id="df6ac-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="df6ac-135">Stockage d’application pour empêcher l’exécution d’applications non autorisées.</span><span class="sxs-lookup"><span data-stu-id="df6ac-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="df6ac-136">Tous les ports USB sont désactivés en mode utilisateur.</span><span class="sxs-lookup"><span data-stu-id="df6ac-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="df6ac-137">Aucune application ou visionneuse standard ne réside sur le matériel Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="df6ac-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="df6ac-138">Tout le contenu est rendu via des protocoles HTTP ou RDP.</span><span class="sxs-lookup"><span data-stu-id="df6ac-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="df6ac-139">L’appliance PC exécute le système d’exploitation Windows Embedded Standard 7.</span><span class="sxs-lookup"><span data-stu-id="df6ac-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="df6ac-140">Tout le matériel, y compris les appareils, est fourni par les partenaires OEM.</span><span class="sxs-lookup"><span data-stu-id="df6ac-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="df6ac-141">Joindre un domaine facultatif aux services de domaine Active Directory (AD DS), ce qui permet la gestion et le contrôle des comptes de sécurité locaux.</span><span class="sxs-lookup"><span data-stu-id="df6ac-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="df6ac-142">Vous pouvez également gérer le compte d’administrateur local à l’aide du Centre d’administration Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="df6ac-143">Skype Room System est mis à jour par le biais de processus Microsoft Update standard.</span><span class="sxs-lookup"><span data-stu-id="df6ac-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="df6ac-144">Skype Room System se connecte à Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="df6ac-145">Skype Entreprise utilise le chiffrement et l’autorisation de bout en bout pour tous les modes de communication</span><span class="sxs-lookup"><span data-stu-id="df6ac-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="df6ac-146">Skype Room System prend en charge les normes de sécurité et de conformité de Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="df6ac-147">Pour [plus d’informations, voir Planifier](../../plan-your-deployment/security/security.md) la sécurité dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="df6ac-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="df6ac-148">Licence</span><span class="sxs-lookup"><span data-stu-id="df6ac-148">License</span></span>

<span data-ttu-id="df6ac-149">Vérifiez que vous utilisez un service KMS pour activer le logiciel.</span><span class="sxs-lookup"><span data-stu-id="df6ac-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="df6ac-150">Si c’est le cas, vous devrez peut-être vérifier ou y ajouter la clé KMS du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="df6ac-151">Si vous n’utilisez pas kmS, demandez la clé de licence en volume pour la clé MAK du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="df6ac-152">Clés de licence</span><span class="sxs-lookup"><span data-stu-id="df6ac-152">License keys</span></span>

<span data-ttu-id="df6ac-153">Skype Room System exécute le client de bureau Skype Entreprise en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="df6ac-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="df6ac-154">Si Skype Room System est membre du domaine, il découvrira votre kmS.</span><span class="sxs-lookup"><span data-stu-id="df6ac-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="df6ac-155">(et s’il dispose de la clé KMS de licence en volume, il s’active automatiquement).</span><span class="sxs-lookup"><span data-stu-id="df6ac-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="df6ac-156">Les licences en volume fournissent également une mak, que vous entrez quand elle affiche xxxxx-xxxxx-xxxxx-xxxxx.</span><span class="sxs-lookup"><span data-stu-id="df6ac-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="df6ac-157">(Vous avez besoin d’un accès à Internet pour l’activer à l’aide de LA MAK, mais pas du service KMS).</span><span class="sxs-lookup"><span data-stu-id="df6ac-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="df6ac-158">Pour plus d’informations, voir Activation en volume d’Office 2013.</span><span class="sxs-lookup"><span data-stu-id="df6ac-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="df6ac-159">Pour entrer la clé MAK, allez à l’outil de gestion des licences \> SRS des paramètres OEM.</span><span class="sxs-lookup"><span data-stu-id="df6ac-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="df6ac-160">Cliquez sur Vérifier l’état.</span><span class="sxs-lookup"><span data-stu-id="df6ac-160">Click Check Status.</span></span> <span data-ttu-id="df6ac-161">Lorsque l’état indique « le produit n’est pas activé », entrez la clé.</span><span class="sxs-lookup"><span data-stu-id="df6ac-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="df6ac-162">Si, au cours de l’activation, vous obtenez une erreur qui indique « Le service de gestion des licences logicielles a signalé que la clé de produit n’est pas valide », vérifiez que :</span><span class="sxs-lookup"><span data-stu-id="df6ac-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="df6ac-163">La clé a été entrée correctement.</span><span class="sxs-lookup"><span data-stu-id="df6ac-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="df6ac-164">Vous avez entré la clé MAK Skype Entreprise et non une autre clé.</span><span class="sxs-lookup"><span data-stu-id="df6ac-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="df6ac-165">Le système dispose d’un accès à Internet.</span><span class="sxs-lookup"><span data-stu-id="df6ac-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="df6ac-166">Vous pouvez activer par téléphone, mais vous devez d’abord avoir tenté de l’activer à l’aide de l’outil de gestion des licences SRS.</span><span class="sxs-lookup"><span data-stu-id="df6ac-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="df6ac-167">Pour l’activer par téléphone, démarrez une réunion de test (pas un appel de test, car c’est trop court).</span><span class="sxs-lookup"><span data-stu-id="df6ac-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="df6ac-168">Dans l’Assistant Activation d’Office, sélectionnez Activation téléphonique, appelez Microsoft, tapez le numéro long et entrez une réponse.</span><span class="sxs-lookup"><span data-stu-id="df6ac-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="df6ac-169">Autorité de certification</span><span class="sxs-lookup"><span data-stu-id="df6ac-169">Certificate Authority</span></span>

<span data-ttu-id="df6ac-170">Confirmez que l’autorité de certification utilisée pour émettre le certificat Office Web Apps Server 2013 possède un chemin d’accès HTTP inclus dans la propriété Liste de révocation de certificats.</span><span class="sxs-lookup"><span data-stu-id="df6ac-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="df6ac-171">Importez le fichier de certificat (.crt) dans Skype Room System si vous utilisez Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="df6ac-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="df6ac-172">Il est facilement obtenu à partir du partage CertEnroll du serveur ca, ou dans le dossier Racine de confiance d’un PC joint à un domaine.</span><span class="sxs-lookup"><span data-stu-id="df6ac-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="df6ac-173">Certificats</span><span class="sxs-lookup"><span data-stu-id="df6ac-173">Certificates</span></span>

<span data-ttu-id="df6ac-174">Vérifiez que votre autorité de certification dispose d’un chemin d’accès http pour la liste de révocation de certificats.</span><span class="sxs-lookup"><span data-stu-id="df6ac-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="df6ac-175">Si ce n’est pas le cas, mettez à jour votre ca pour en inclure un.</span><span class="sxs-lookup"><span data-stu-id="df6ac-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="df6ac-176">Installez les certificats dans la configuration d’administration de Skype Room System sous System Settings \> Certificate Manager.</span><span class="sxs-lookup"><span data-stu-id="df6ac-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="df6ac-177">Vous avez besoin de l’ac racine d’entreprise pour votre certificat interne.</span><span class="sxs-lookup"><span data-stu-id="df6ac-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="df6ac-178">Une façon d’obtenir les certificats dont vous avez besoin consiste à découvrir l’ac qui a émis vos certificats.</span><span class="sxs-lookup"><span data-stu-id="df6ac-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="df6ac-179">Pour Skype Entreprise Server, sur un PC dans Skype Entreprise, cliquez sur Paramètres de conférence d’accès aux \> \> outils de paramètres.</span><span class="sxs-lookup"><span data-stu-id="df6ac-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="df6ac-180">Cela ouvre une page web sécurisée par l’ac qui a émis les certificats internes.</span><span class="sxs-lookup"><span data-stu-id="df6ac-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="df6ac-181">Cliquez sur l’icône Verrouiller dans la barre d’adresses du navigateur pour afficher un rapport de sécurité.</span><span class="sxs-lookup"><span data-stu-id="df6ac-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="df6ac-182">Cliquez sur Afficher les certificats et examinez la propriété point de distribution de la CRL.</span><span class="sxs-lookup"><span data-stu-id="df6ac-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="df6ac-183">Le deuxième paramètre CN doit être le nom de serveur de l’ac.</span><span class="sxs-lookup"><span data-stu-id="df6ac-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="df6ac-184">Ouvrez l’Explorateur Windows pour cette \\ \< CA Server Name \> adresse \CertEnroll.</span><span class="sxs-lookup"><span data-stu-id="df6ac-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="df6ac-185">Copiez les deux fichiers .crl et le fichier .crt sur un disque mémoire flash et placez-le dans le côté gauche du tableau SMART.</span><span class="sxs-lookup"><span data-stu-id="df6ac-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="df6ac-186">Importez le fichier .crt dans Skype Room System sous le dossier Autorité de certification des salles de confiance.</span><span class="sxs-lookup"><span data-stu-id="df6ac-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="df6ac-187">Importez les fichiers .crl sur Skype Room System sous le dossier Autorités de certification intermédiaires.</span><span class="sxs-lookup"><span data-stu-id="df6ac-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="df6ac-188">(Vous devez modifier le filtre d’extension de fichier dans le Gestionnaire de certificats en .crl pour voir les fichiers).</span><span class="sxs-lookup"><span data-stu-id="df6ac-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="df6ac-189">Remarque : le serveur Office Web Apps 2013 peut partager la même cae que Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="df6ac-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="df6ac-190">Si ce n’est pas le cas, vous ne pourrez pas partager PowerPoint dans une réunion.</span><span class="sxs-lookup"><span data-stu-id="df6ac-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="df6ac-191">Consultez le programme informatique et obtenez les fichiers CRT et CRL à partir du partage réseau ca CertEnroll, comme expliqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="df6ac-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="df6ac-192">L’appartenance à un domaine peut simplifier certaines choses, car vous pouvez traiter Skype Room System comme un système Windows et il peut s’appuyer sur Active Directory pour certains aspects du certificat.</span><span class="sxs-lookup"><span data-stu-id="df6ac-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="df6ac-193">Toutefois, il est préférable de gérer cela manuellement.</span><span class="sxs-lookup"><span data-stu-id="df6ac-193">However, it's best to manually manage this.</span></span>
