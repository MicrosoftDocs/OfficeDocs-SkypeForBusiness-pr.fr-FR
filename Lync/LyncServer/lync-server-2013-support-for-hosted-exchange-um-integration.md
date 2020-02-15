---
title: Prise en charge de Lync Server 2013 pour l’intégration de la messagerie unifiée Exchange hébergée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0625d983f05e5b9b22bf5086d0689c117b2ecda
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="a1f97-102">Prise en charge de l’intégration de la messagerie unifiée Exchange hébergée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1f97-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1f97-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a1f97-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a1f97-104">L’application de routage ExUM de Lync Server 2013 prend en charge l’intégration à la messagerie unifiée Exchange dans un environnement local, où Lync Server 2013 et la messagerie unifiée Exchange sont tous les deux installés localement dans votre entreprise ou avec la messagerie unifiée Exchange hébergée par un fournisseur de services, comme illustré dans le diagramme suivant.</span><span class="sxs-lookup"><span data-stu-id="a1f97-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="a1f97-105">![Déploiement de la messagerie unifiée Lync Server Exchange sur site](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Déploiement de la messagerie unifiée Lync Server Exchange sur site")</span><span class="sxs-lookup"><span data-stu-id="a1f97-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="a1f97-106">Les modes suivants sont pris en charge :</span><span class="sxs-lookup"><span data-stu-id="a1f97-106">The following modes are supported:</span></span>

  - <span data-ttu-id="a1f97-107">**Le mode**   local Lync Server 2013 et la messagerie unifiée Exchange sont tous deux déployés sur des serveurs locaux dans votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="a1f97-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="a1f97-108">**Mode intersites**   Lync Server 2013 est déployé sur des serveurs locaux au sein de votre entreprise et la messagerie unifiée Exchange est hébergée dans une installation de fournisseur de services en ligne, telle qu’un centre de données Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a1f97-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="a1f97-109">**Mode mixte le**   déploiement de Lync Server 2013 comporte des boîtes aux lettres d’utilisateur hébergées sur des serveurs locaux exécutant Microsoft Exchange Server au sein de votre entreprise et des boîtes aux lettres hébergées dans un centre de données de service Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="a1f97-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1f97-110">Le mode mixte peut être utilisé comme solution transitoire lors de l’évaluation et de la migration progressive des utilisateurs vers la messagerie unifiée Exchange hébergée, ou comme solution permanente si vous décidez de conserver les services de messagerie unifiée Exchange de certains utilisateurs en local après avoir migré les autres.</span><span class="sxs-lookup"><span data-stu-id="a1f97-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="a1f97-111">Pour intégrer Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez configurer un *espace d’adressage SIP partagé* (également appelé *domaine fractionné*).</span><span class="sxs-lookup"><span data-stu-id="a1f97-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="a1f97-112">Dans cette configuration, Lync Server 2013 et le fournisseur de services de messagerie unifiée Exchange hébergé par un tiers peuvent accéder au même espace d’adressage de domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="a1f97-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="a1f97-113">Pour plus d’informations, reportez-vous à [Hosted Exchange um Integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="a1f97-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

