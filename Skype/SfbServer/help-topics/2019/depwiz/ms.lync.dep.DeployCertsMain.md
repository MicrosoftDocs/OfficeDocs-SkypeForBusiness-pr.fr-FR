---
title: Assistant Certificat
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: Pour Demander, Assigner, Supprimer ou Afficher des certificats, utilisez l’Assistant Certificat. Vous devez être connecté en tant que membre du groupe RTCUniversalServerAdmins. Pour demander un certificat à une autorité de certification publique, il n’est pas nécessaire que vous soyez membre d’autres groupes. Pour demander un certificat à partir clé publique de votre organisation (PKI), vous devez vérifier que supplémentaires, le cas échéant, vous aurez besoin des appartenances de groupe. Au cours de la tâche de demande, vous pouvez entrer les informations d’identification de substitution qui seront utilisées pour demander que le certificat à partir de votre infrastructure à clé publique de l’autorité de certification.
ms.openlocfilehash: afa36085fb4e8a1937facac204d78d5c0c61af9b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216297"
---
# <a name="certificate-wizard"></a><span data-ttu-id="d9018-107">Assistant Certificat</span><span class="sxs-lookup"><span data-stu-id="d9018-107">Certificate Wizard</span></span>
 
<span data-ttu-id="d9018-108">Pour **Demander**, **Assigner**, **Supprimer** ou **Afficher** des certificats, utilisez l’Assistant Certificat.</span><span class="sxs-lookup"><span data-stu-id="d9018-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="d9018-109">Vous devez être connecté en tant que membre du groupe RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d9018-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="d9018-110">Pour demander un certificat à une autorité de certification publique, il n’est pas nécessaire que vous soyez membre d’autres groupes.</span><span class="sxs-lookup"><span data-stu-id="d9018-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="d9018-111">Pour demander un certificat à partir clé publique de votre organisation (PKI), vous devez vérifier que supplémentaires, le cas échéant, vous aurez besoin des appartenances de groupe.</span><span class="sxs-lookup"><span data-stu-id="d9018-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="d9018-112">Au cours de la tâche de demande, vous pouvez entrer les informations d’identification de substitution qui seront utilisées pour demander que le certificat à partir de votre infrastructure à clé publique de l’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="d9018-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="d9018-113">Pour demander un nouveau certificat, cliquez sur **Demander**.</span><span class="sxs-lookup"><span data-stu-id="d9018-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="d9018-114">Pour assigner un certificat qui n’a pas encore été assigné, cliquez sur **Assigner**.</span><span class="sxs-lookup"><span data-stu-id="d9018-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="d9018-115">Pour supprimer un certificat que vous avez précédemment assigné, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d9018-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9018-p103">Le bouton **Supprimer** est disponible uniquement si un certificat a été précédemment assigné. Si le bouton **Supprimer** n’est pas disponible (grisé), cela signifie qu’aucun certificat n’a été assigné.</span><span class="sxs-lookup"><span data-stu-id="d9018-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="d9018-118">Pour afficher un certificat assigné, cliquez sur **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="d9018-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9018-p104">Le bouton **Afficher** est disponible uniquement si un certificat a été précédemment assigné. Si le bouton **Afficher** est grisé, cela signifie qu’aucun certificat n’a été assigné.</span><span class="sxs-lookup"><span data-stu-id="d9018-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="d9018-121">Pour actualiser l’écran d’assignation du certificat actuel, cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="d9018-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="d9018-122">Pour importer un certificat qui n’est pas présent dans le magasin de certificats, cliquez sur **Importer un certificat**.</span><span class="sxs-lookup"><span data-stu-id="d9018-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9018-123">L’option **Importer un certificat** est généralement utilisée pour traiter un certificat qui est reçu par le biais d’un processus autre qu’une demande de l’Assistant Certificat.</span><span class="sxs-lookup"><span data-stu-id="d9018-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="d9018-124">Par exemple, l’administrateur de votre infrastructure à clé publique crée un certificat et vous permet d’y accéder.</span><span class="sxs-lookup"><span data-stu-id="d9018-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="d9018-125">**Importer un certificat** pour importer le certificat dans le certificat de l’ordinateur stocker et rendre accessible aux Skype pour Business Server à affecter.</span><span class="sxs-lookup"><span data-stu-id="d9018-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="d9018-p106">Pour terminer le processus de demande de certificat auprès d’une autorité de certification de votre organisation qui nécessite l’approbation de l’administrateur de l’autorité de certification, cliquez sur **Traiter une demande en attente**. La demande de certificat affiche un statut en attente, ainsi que le numéro d’identification de la demande en attente. Pour poursuivre le traitement d’un certificat dont le statut est en attente, cliquez sur **Actualiser** pour activer le bouton **Traiter une demande en attente**. Le bouton **Traiter une demande en attente** n’est plus inaccessible (grisé). Vous pouvez ensuite essayer de récupérer la demande en attente, mais le statut de la demande restera en attente tant que le certificat n’aura pas été émis ou rejeté par l’administrateur de l’autorité de certification. Le bouton est inaccessible si aucune demande en attente valide n’a été créée par l’Assistant Certificat.</span><span class="sxs-lookup"><span data-stu-id="d9018-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

