---
title: Demande de certificat (renvoyé)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/1/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'La page d’état de demande de certificat en ligne vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne. Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher attribuer ce certificat à Skype pour les utilisations de certificats de serveur d’entreprise est sélectionnée. Si vous cliquez sur Terminer, le certificat est automatiquement affecté à Lync Server 2013 pour fins que vous avez définies au cours de la procédure de création de la demande de certificat. Par défaut, les besoins qui recevra le certificat sont :'
ms.openlocfilehash: 392fbdf4cae860152a5ed96e9e347a0c51aa6f70
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-request-returned"></a><span data-ttu-id="31f63-107">Demande de certificat (renvoyé)</span><span class="sxs-lookup"><span data-stu-id="31f63-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="31f63-108">La page **Statut de la demande de certificat en ligne** vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="31f63-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="31f63-109">Cette page fournit l’empreinte numérique du certificat qui identifie de manière unique le certificat.</span><span class="sxs-lookup"><span data-stu-id="31f63-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="31f63-110">Par défaut, la case à cocher **attribuer ce certificat à Skype pour les utilisations du certificat Business Server** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="31f63-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="31f63-111">Si vous cliquez sur **Terminer**, le certificat est automatiquement affecté à Lync Server 2013 pour fins que vous avez définies au cours de la procédure de création de la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="31f63-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="31f63-112">Par défaut, les besoins qui recevra le certificat sont :</span><span class="sxs-lookup"><span data-stu-id="31f63-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="31f63-113">Serveur par défaut pour couche sécurité MTLS (Mutual Transport) - connexions aux clients et autres serveurs</span><span class="sxs-lookup"><span data-stu-id="31f63-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="31f63-114">Services Web internes - connexions Client et serveur sur le site Web interne site services de Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="31f63-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="31f63-115">Les services Web externes - connexions Client et serveur sur le site Web externe site services pour TLS/SSL.</span><span class="sxs-lookup"><span data-stu-id="31f63-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="31f63-116">Cliquez sur **Afficher les détails du certificat** pour afficher le certificat pour vérifier que les propriétés du certificat sont correctes et que le certificat est prêt à être appliqué et mis en service sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="31f63-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="31f63-117">Cliquez sur **Terminer** pour terminer le processus de demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="31f63-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="31f63-118">Si vous avez sélectionné la case à cocher **attribuer ce certificat à Skype pour les utilisations du certificat serveur de l’entreprise**, le certificat sera automatiquement assigné.</span><span class="sxs-lookup"><span data-stu-id="31f63-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="31f63-119">Si vous avez choisi de désactiver cette case à cocher, vous devez attribuer le certificat dans une étape distincte.</span><span class="sxs-lookup"><span data-stu-id="31f63-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="31f63-120">Si le certificat émettrice de certification authority (CA) racine n’est pas dans le magasin de l’ordinateur de l’autorité de Certification racine de confiance, ou si les certificats d’autorité de certification intermédiaires ne sont pas dans le magasin approprié, vous verrez le résumé de l’état, comme illustré dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="31f63-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="31f63-121">Vous n’avez pas de l’option pour attribuer le certificat.</span><span class="sxs-lookup"><span data-stu-id="31f63-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="31f63-122">Pour terminer le processus d’affectation de certificat, vous devez importer le certificat de racine d’autorité de certification émettrice et tout certificat CA intermédiaire et ensuite affecter le certificat en cliquant sur **affecter** sur la page principale de l’Assistant certificat.</span><span class="sxs-lookup"><span data-stu-id="31f63-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

