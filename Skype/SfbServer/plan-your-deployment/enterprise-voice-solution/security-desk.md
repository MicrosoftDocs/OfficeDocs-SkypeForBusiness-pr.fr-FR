---
title: Inclure le service de sécurité dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planification de l’utilisation du service de sécurité de votre organisation dans un déploiement E9-1-1, dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813404"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="b1a0d-103">Inclure le service de sécurité dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b1a0d-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="b1a0d-104">Planification de l’utilisation du service de sécurité de votre organisation dans un déploiement E9-1-1, dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="b1a0d-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b1a0d-p101">Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="b1a0d-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="b1a0d-107">**Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**</span><span class="sxs-lookup"><span data-stu-id="b1a0d-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="b1a0d-108">Vous pouvez configurer la stratégie d’emplacement de sorte que Skype Entreprise Server envoie des alertes de messagerie instantanée aux adresses SIP Skype Entreprise d’un ou plusieurs membres du personnel de sécurité.</span><span class="sxs-lookup"><span data-stu-id="b1a0d-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="b1a0d-109">Ces alertes contiennent le nom, le numéro et l’emplacement de la personne qui passe l’appel d’urgence et facilitent l’assistance du personnel de sécurité en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="b1a0d-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="b1a0d-110">**Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**</span><span class="sxs-lookup"><span data-stu-id="b1a0d-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="b1a0d-p103">Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="b1a0d-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b1a0d-p104">Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir.</span><span class="sxs-lookup"><span data-stu-id="b1a0d-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

