---
title: Demande de certificat (retournée)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'La page État de la demande de certificat en ligne vous présente les informations importantes faisant suite à la création et l’émission d’une demande de certificat en ligne. Elle fournit l’empreinte du certificat qui l’identifie de manière unique. Par défaut, la case à cocher Affecter ce certificat aux utilisations de certificat Skype Entreprise Server est sélectionnée. Si vous cliquez sur Terminer, le certificat est automatiquement affecté à Skype Entreprise Server aux fins que vous avez définies lors des étapes de création de la demande de certificat. Par défaut, le certificat sera assigné aux fins suivantes :'
ms.openlocfilehash: 8d7d1dc5013505b7874bccd2ee415f9211713e70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801834"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="1ef15-107">Demande de certificat (retournée)</span><span class="sxs-lookup"><span data-stu-id="1ef15-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="1ef15-108">La page **État de la demande de certificat en ligne** vous présente les informations importantes faisant suite à la création et l’émission d’une demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="1ef15-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="1ef15-109">Elle fournit l’empreinte du certificat qui l’identifie de manière unique.</span><span class="sxs-lookup"><span data-stu-id="1ef15-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="1ef15-110">Par défaut, la case à **cocher Affecter ce** certificat aux utilisations de certificat Skype Entreprise Server est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1ef15-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="1ef15-111">Si vous cliquez **sur Terminer,** le certificat est automatiquement affecté à Skype Entreprise Server aux fins que vous avez définies lors des étapes de création de la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="1ef15-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="1ef15-112">Par défaut, le certificat sera assigné aux fins suivantes :</span><span class="sxs-lookup"><span data-stu-id="1ef15-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="1ef15-113">Serveur par défaut pour MTLS (Mutual Transport Layer Security) : connexions aux clients et autres serveurs</span><span class="sxs-lookup"><span data-stu-id="1ef15-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="1ef15-114">Services Web internes : connexions client et serveur sur le site des services Web internes pour TLS/SSL (Transport Layer Security/Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="1ef15-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="1ef15-115">Services Web externes : connexions client et serveur sur le site de services Web externes pour TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="1ef15-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="1ef15-116">Cliquez sur **Afficher les détails du certificat** pour voir le certificat et confirmer que ses propriétés correspondent à vos souhaits et qu’il est prêt à être appliqué et utilisé sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="1ef15-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="1ef15-117">Cliquez sur **Terminer** pour achever le processus de demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="1ef15-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="1ef15-118">Si vous avez cocher la case Affecter ce certificat aux utilisations de certificat Skype Entreprise **Server,** le certificat sera automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="1ef15-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="1ef15-119">Si vous choisissez de ne pas activer cette case à cocher, vous devez assigner le certificat lors d’une étape différente.</span><span class="sxs-lookup"><span data-stu-id="1ef15-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1ef15-120">Si le certificat racine de l’autorité de certification émettrice ne se trouve pas dans le magasin de l’autorité de certification racine de confiance de l’ordinateur, ou si les certificats d’autorité de certification intermédiaires ne sont pas dans le magasin approprié, vous verrez l’état récapitulatif, comme illustré dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="1ef15-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="1ef15-121">Vous n’avez pas l’option d’assigner le certificat.</span><span class="sxs-lookup"><span data-stu-id="1ef15-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="1ef15-122">Pour terminer le processus d’affectation de certificat, vous devez importer le certificat racine de l’autorité de certification ainsi que tous les certificats intermédiaires de l’autorité de certification, puis assigner le certificat en cliquant sur **Assigner** dans la page principale de l’Assistant Certificat.</span><span class="sxs-lookup"><span data-stu-id="1ef15-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

