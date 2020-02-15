---
title: 'Lync Server 2013 : y compris le service de sécurité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Including the security desk
ms:assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398299(v=OCS.15)
ms:contentKeyID: 48184084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99f35087d03b046fade741140dc3f5522e6c6d05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="including-the-security-desk-in-lync-server-2013"></a><span data-ttu-id="e4d2c-102">Inclusion du service de sécurité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d2c-102">Including the security desk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d2c-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e4d2c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e4d2c-p101">Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.</span><span class="sxs-lookup"><span data-stu-id="e4d2c-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>

  - <span data-ttu-id="e4d2c-106">**Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**</span><span class="sxs-lookup"><span data-stu-id="e4d2c-106">**Do you want the security desk to be notified when there is an emergency call?**</span></span>  
    <span data-ttu-id="e4d2c-107">Vous pouvez configurer la stratégie d’emplacement afin que Lync Server envoie des alertes de messagerie instantanée aux adresses SIP Lync d’un ou de plusieurs membres du personnel de sécurité.</span><span class="sxs-lookup"><span data-stu-id="e4d2c-107">You can configure the location policy so that Lync Server sends instant messaging (IM) alerts to the Lync SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="e4d2c-108">Ces alertes contiennent le nom, le numéro et l’emplacement de la personne qui passe l’appel d’urgence, et facilitent le personnel de sécurité à l’aide de la situation d’urgence.</span><span class="sxs-lookup"><span data-stu-id="e4d2c-108">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>

<!-- end list -->

  - <span data-ttu-id="e4d2c-109">**Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**</span><span class="sxs-lookup"><span data-stu-id="e4d2c-109">**Do you want to conference the security desk in on each emergency call?**</span></span>  
    <span data-ttu-id="e4d2c-p103">Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.</span><span class="sxs-lookup"><span data-stu-id="e4d2c-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e4d2c-p104">Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir.</span><span class="sxs-lookup"><span data-stu-id="e4d2c-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

