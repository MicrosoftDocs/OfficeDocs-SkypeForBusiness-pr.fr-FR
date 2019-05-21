---
title: Demander, installer ou assigner des certificats
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: 'L’Étape 3 : Demander, installer ou assigner les certificats démarre l’Assistant Certificat lorsque vous cliquez sur Exécuter. Les certificats qui sont configurés par le biais de l’Assistant dépendent de la définition de la topologie de Skype entreprise Server 2015 configurée et publiée par le générateur de topologie dans le magasin de gestion central. Pour exécuter correctement l’Assistant Certificat pour une autorité de certification en ligne dans votre organisation, vous devez être connecté à un ordinateur en tant que membre du groupe Administrateurs local de cet ordinateur. Vous devez également être un utilisateur de domaine authentifié dans le domaine où l’ordinateur et l’autorité de certification existent. L’Assistant Certificat fournit la possibilité de spécifier d’autres informations d’identification pour accéder à l’autorité de certification de votre organisation.'
ms.openlocfilehash: fe9fe2d994541656d81d934ed1f16fd72978d037
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283575"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="670d8-107">Demander, installer ou assigner des certificats</span><span class="sxs-lookup"><span data-stu-id="670d8-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="670d8-108">L’**Étape 3 : Demander, installer ou assigner les certificats** démarre l’Assistant Certificat lorsque vous cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="670d8-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="670d8-109">Les certificats qui sont configurés par le biais de l’Assistant dépendent de la définition de la topologie de Skype entreprise Server 2015 configurée et publiée par le générateur de topologie dans le magasin de gestion central.</span><span class="sxs-lookup"><span data-stu-id="670d8-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server 2015 topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="670d8-110">Pour exécuter correctement l’Assistant Certificat pour une autorité de certification en ligne dans votre organisation, vous devez être connecté à un ordinateur en tant que membre du groupe Administrateurs local de cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="670d8-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="670d8-111">Vous devez également être un utilisateur de domaine authentifié dans le domaine où l’ordinateur et l’autorité de certification existent.</span><span class="sxs-lookup"><span data-stu-id="670d8-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="670d8-112">L’Assistant Certificat fournit la possibilité de spécifier d’autres informations d’identification pour accéder à l’autorité de certification de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="670d8-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="670d8-p103">Vous pouvez également utiliser l’Assistant Certificat pour demander et traiter des demandes de certificat hors connexion qui sont envoyées à une autorité de certification publique ou à une autre infrastructure à clé publique (PKI) hors connexion. Il n’est pas nécessaire d’appartenir à des groupes spécifiques autres que ceux nécessaires pour se connecter à l’ordinateur, pour générer une demande hors connexion. Pour traiter la réponse de l’autorité de certification publique et assigner le certificat à l’ordinateur et au rôle, vous devez être connecté en tant que membre du groupe Administrateurs local ou équivalent.</span><span class="sxs-lookup"><span data-stu-id="670d8-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

