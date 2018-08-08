---
title: Inclure le service de sécurité dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planifiez la façon d’inclure le bureau de sécurité de votre organisation dans un déploiement E9-1-1, dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 9363956a9b0f1cc598224b9d573677ff424c9e23
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989563"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="ff29b-103">Inclure le service de sécurité dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="ff29b-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="ff29b-104">Planifiez la façon d’inclure le bureau de sécurité de votre organisation dans un déploiement E9-1-1, dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ff29b-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ff29b-p101">Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="ff29b-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="ff29b-107">**Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**</span><span class="sxs-lookup"><span data-stu-id="ff29b-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="ff29b-108">Vous pouvez configurer la stratégie d’emplacement afin que Skype pour Business Server envoie des alertes par messagerie instantanée (IM) à la Skype pour les adresses SIP Business du personnel de sécurité un ou plusieurs.</span><span class="sxs-lookup"><span data-stu-id="ff29b-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="ff29b-109">Ces alertes contiennent le nom, le nombre et l’emplacement de la personne à l’appel d’urgence et facilitent le personnel de sécurité en aidant à la situation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="ff29b-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="ff29b-110">**Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**</span><span class="sxs-lookup"><span data-stu-id="ff29b-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="ff29b-p103">Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="ff29b-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ff29b-p104">Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir.</span><span class="sxs-lookup"><span data-stu-id="ff29b-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

