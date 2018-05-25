---
title: Demande de certificat (retournée)
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
description: 'La page État de demande de certificat en ligne vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne. Cette page fournit l’empreinte de certificat qui identifie de manière unique le certificat. Par défaut, la case à cocher attribuer ce certificat Skype pour utilisations de certificat Business Server est sélectionnée. Si vous cliquez sur Terminer, le certificat sera automatiquement assigné à Lync Server 2013 à des fins que vous avez définis dans la procédure de création de la demande de certificat. Par défaut, les besoins le certificat sera attribué sont les suivants :'
ms.openlocfilehash: 392fbdf4cae860152a5ed96e9e347a0c51aa6f70
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="certificate-request-returned"></a><span data-ttu-id="ead6f-107">Demande de certificat (retournée)</span><span class="sxs-lookup"><span data-stu-id="ead6f-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="ead6f-108">La page **État de la demande de certificat en ligne** vous présente des informations importantes qui résulte de la création et l’émission de la demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="ead6f-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="ead6f-109">Cette page fournit l’empreinte de certificat qui identifie de manière unique le certificat.</span><span class="sxs-lookup"><span data-stu-id="ead6f-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="ead6f-110">Par défaut, la case à cocher **attribuer ce certificat Skype pour utilisations de certificat Business Server** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ead6f-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="ead6f-111">Si vous cliquez sur **Terminer**, le certificat sera automatiquement assigné à Lync Server 2013 à des fins que vous avez définis dans la procédure de création de la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="ead6f-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="ead6f-112">Par défaut, les besoins le certificat sera attribué sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ead6f-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="ead6f-113">Serveur par défaut pour MTLS Mutual Transport Layer Security () - connexions vers les clients et autres serveurs</span><span class="sxs-lookup"><span data-stu-id="ead6f-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="ead6f-114">Services Web internes - connexions Client et serveur sur le site Web interne services pour Transport Layer Security/Secure Sockets Layer (SSL/TLS)</span><span class="sxs-lookup"><span data-stu-id="ead6f-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="ead6f-115">Services Web externes - connexions Client et serveur sur le site Web externe services pour TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="ead6f-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="ead6f-116">Cliquez sur **Afficher les détails du certificat** pour afficher le certificat pour confirmer que les propriétés du certificat sont correctes, et que le certificat est prêt à être appliquée et mis en service sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ead6f-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="ead6f-117">Cliquez sur **Terminer** pour terminer le processus de demande de certificat en ligne.</span><span class="sxs-lookup"><span data-stu-id="ead6f-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="ead6f-118">Si vous avez sélectionné la case à cocher **attribuer ce certificat Skype pour les utilisations de certificat de serveur d’entreprise**, le certificat sera automatiquement assigné.</span><span class="sxs-lookup"><span data-stu-id="ead6f-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="ead6f-119">Si vous avez choisi de désactiver cette case à cocher, vous devez assigner le certificat dans une étape distincte.</span><span class="sxs-lookup"><span data-stu-id="ead6f-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ead6f-120">Si le certificat racine d’autorité de certification émettrice certification ne figure pas dans le magasin de l’ordinateur autorité de Certification racine de confiance, ou si les certificats d’autorité de certification intermédiaires ne sont pas dans le magasin approprié, vous verrez le statut de synthèse, comme illustré dans l’image suivante.</span><span class="sxs-lookup"><span data-stu-id="ead6f-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="ead6f-121">Vous n’avez pas l’option pour assigner le certificat.</span><span class="sxs-lookup"><span data-stu-id="ead6f-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="ead6f-122">Pour terminer le processus d’affectation de certificat, vous devez importer le certificat racine Autorité de certification émettrice et les certificats d’autorité de certification intermédiaires et puis assigner le certificat en cliquant sur **affecter** sur la page Assistant Certificat principale.</span><span class="sxs-lookup"><span data-stu-id="ead6f-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

