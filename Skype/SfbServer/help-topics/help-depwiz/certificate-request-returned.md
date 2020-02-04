---
title: Demande de certificat (retournée)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'La page État de la demande de certificat en ligne présente des informations importantes qui résultent de la création réussie et de l’envoi de la demande de certificat en ligne. Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher affecter ce certificat aux utilisations des certificats de Skype entreprise Server est activée. Si vous cliquez sur terminer, le certificat est automatiquement attribué à Lync Server 2013 conformément aux étapes de création de la demande de certificat. Par défaut, le certificat est affecté par défaut :'
ms.openlocfilehash: 885de54ec8deeef1d326e39b5a35e7b08c633973
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687747"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="afa5d-107">Demande de certificat (retournée)</span><span class="sxs-lookup"><span data-stu-id="afa5d-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="afa5d-108">La page État de la **demande de certificat en ligne** présente des informations importantes qui résultent de la création réussie et de l’envoi de la demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="afa5d-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="afa5d-109">Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat.</span><span class="sxs-lookup"><span data-stu-id="afa5d-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="afa5d-110">Par défaut, la case à cocher **affecter ce certificat aux utilisations des certificats de Skype entreprise Server** est activée.</span><span class="sxs-lookup"><span data-stu-id="afa5d-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="afa5d-111">Si vous cliquez sur **Terminer**, le certificat est automatiquement attribué à Lync Server 2013 conformément aux étapes de création de la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="afa5d-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="afa5d-112">Par défaut, le certificat est affecté par défaut :</span><span class="sxs-lookup"><span data-stu-id="afa5d-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="afa5d-113">Serveur par défaut de Mutual Transport Layer Security (MTLS)-connexions aux clients et autres serveurs</span><span class="sxs-lookup"><span data-stu-id="afa5d-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="afa5d-114">Services Web internes-client et connexions serveur sur le site des services Web interne pour le protocole TLS/SSL (Transport Layer Security/Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="afa5d-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="afa5d-115">Services Web externes-client et connexions serveur sur le site des services Web externes pour TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="afa5d-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="afa5d-116">Cliquez sur le bouton **afficher les détails du certificat** pour afficher le certificat pour vérifier que les propriétés du certificat vous conviennent et que le certificat est prêt à être appliqué et mis en place sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="afa5d-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="afa5d-117">Cliquez sur **Terminer** pour terminer le processus de demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="afa5d-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="afa5d-118">Si vous avez coché la case **affecter ce certificat aux utilisations des certificats de Skype entreprise Server**, le certificat est automatiquement attribué.</span><span class="sxs-lookup"><span data-stu-id="afa5d-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="afa5d-119">Si vous avez choisi de désactiver cette case à cocher, vous devez affecter le certificat dans une étape distincte.</span><span class="sxs-lookup"><span data-stu-id="afa5d-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="afa5d-120">Si le certificat racine de l’autorité de certification émettrice ne se trouve pas dans le magasin d’autorités de certification de confiance de l’ordinateur ou s’il ne se trouve pas dans le magasin approprié, vous verrez le statut de synthèse, comme illustré dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="afa5d-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="afa5d-121">Vous n’avez pas la possibilité d’attribuer le certificat.</span><span class="sxs-lookup"><span data-stu-id="afa5d-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="afa5d-122">Pour finaliser le processus d’attribution de certificats, vous devez importer le certificat racine de l’autorité de certification émettrice et les certificats d’autorité de certification intermédiaires, puis attribuer le certificat en cliquant sur **affecter** dans la page de l’Assistant certificat principal.</span><span class="sxs-lookup"><span data-stu-id="afa5d-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

