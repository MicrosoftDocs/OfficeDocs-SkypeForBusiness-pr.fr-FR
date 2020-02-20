---
title: 'Lync Server 2013 : contrats de niveau de service'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Service level agreements
ms:assetid: 10899bad-e8b0-422d-83c9-1599fb3a7d17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720321(v=OCS.15)
ms:contentKeyID: 63969580
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ae1a80975cf13030e51d711f00a70b80a54718
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="service-level-agreements-in-lync-server-2013"></a><span data-ttu-id="a7795-102">Contrats de niveau de service dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7795-102">Service level agreements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7795-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="a7795-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="a7795-104">Le contrat SLA est un document qui définit les services que votre client attend de vous.</span><span class="sxs-lookup"><span data-stu-id="a7795-104">The SLA is a document that defines the services that your customer expects from you.</span></span> <span data-ttu-id="a7795-105">La complexité et le contenu de ce document dépendent en grande partie du fait que les clients sont internes (au sein de votre environnement) ou externes.</span><span class="sxs-lookup"><span data-stu-id="a7795-105">The complexity and content of this document depends largely on whether customers are internal (within your environment) or external.</span></span>

<div>

## <a name="external-customers"></a><span data-ttu-id="a7795-106">Clients externes</span><span class="sxs-lookup"><span data-stu-id="a7795-106">External Customers</span></span>

<span data-ttu-id="a7795-107">Si votre client est externe, le contrat de niveau de service (SLA) peut faire partie d’un contrat juridique avec des incentives financiers et des pénalités de performances à l’intérieur ou à l’extérieur des niveaux de service définis.</span><span class="sxs-lookup"><span data-stu-id="a7795-107">If your customer is external, the SLA may be part of a legal contract with financial incentives and penalties for performance that falls inside or outside defined levels of service.</span></span> <span data-ttu-id="a7795-108">La définition de ces niveaux de service doit faire partie de la négociation contractuelle globale.</span><span class="sxs-lookup"><span data-stu-id="a7795-108">Defining these levels of service should be part of the overall contract negotiation.</span></span>

<span data-ttu-id="a7795-109">Comme pour tous les contrats, il est important que les deux parties comprennent les attentes.</span><span class="sxs-lookup"><span data-stu-id="a7795-109">As with all contracts, it’s important that both parties understand expectations.</span></span> <span data-ttu-id="a7795-110">Le contrat SLA définit ces attentes.</span><span class="sxs-lookup"><span data-stu-id="a7795-110">The SLA defines these expectations.</span></span> <span data-ttu-id="a7795-111">Le contenu du document doit changer rarement et uniquement en raison de négociations avec le client.</span><span class="sxs-lookup"><span data-stu-id="a7795-111">The contents of the document should change infrequently and only because of negotiations with the customer.</span></span>

</div>

<div>

## <a name="internal-customers"></a><span data-ttu-id="a7795-112">Clients internes</span><span class="sxs-lookup"><span data-stu-id="a7795-112">Internal Customers</span></span>

<span data-ttu-id="a7795-113">Si votre client est interne, vous pouvez toujours définir les services attendus des équipes opérationnelles et des systèmes informatiques.</span><span class="sxs-lookup"><span data-stu-id="a7795-113">If your customer is internal, you may still want to define the services that are expected of operations teams and of IT systems.</span></span> <span data-ttu-id="a7795-114">Le contrat SLA peut être créé par le personnel des opérations et être considéré comme un ensemble d’objectifs pour la disponibilité des services informatiques au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a7795-114">The SLA may be created by the operations staff and intended as a set of goals for the availability of IT services within your organization.</span></span> <span data-ttu-id="a7795-115">Ou, les niveaux de performances peuvent être définis par la gestion et utilisés comme points de référence lors de l’évaluation des performances du personnel.</span><span class="sxs-lookup"><span data-stu-id="a7795-115">Or, performance levels may be set by management and used as benchmarks when assessing staff performance.</span></span>

</div>

<div>

## <a name="typical-criteria"></a><span data-ttu-id="a7795-116">Critères typiques</span><span class="sxs-lookup"><span data-stu-id="a7795-116">Typical Criteria</span></span>

<span data-ttu-id="a7795-117">Les contrats de niveau de service incluent des sections qui définissent les critères des niveaux minimaux de disponibilité, de prise en charge et de capacité.</span><span class="sxs-lookup"><span data-stu-id="a7795-117">SLAs include sections that define criteria of minimum levels of availability, support, and capacity.</span></span>

  - <span data-ttu-id="a7795-118">**La disponibilité**   définit les heures et les systèmes d’exploitation sur lesquels les sites et les autres services Lync seront disponibles.</span><span class="sxs-lookup"><span data-stu-id="a7795-118">**Availability**   Define the hours and the operating systems on which sites and other Lync services will be available.</span></span> <span data-ttu-id="a7795-119">Toute maintenance de routine affectant la disponibilité du service doit être définie.</span><span class="sxs-lookup"><span data-stu-id="a7795-119">Any routine maintenance that affects service availability should be defined.</span></span> <span data-ttu-id="a7795-120">Définir les facteurs externes qui affectent le service, par exemple la perte de connectivité Internet.</span><span class="sxs-lookup"><span data-stu-id="a7795-120">Define external factors that affect service, for example, the loss of Internet connectivity.</span></span>

  - <span data-ttu-id="a7795-121">**Prise en charge**   définir les heures auxquelles la prise en charge d’un système sera disponible.</span><span class="sxs-lookup"><span data-stu-id="a7795-121">**Support**   Define the hours when support for a system will be available.</span></span> <span data-ttu-id="a7795-122">Spécifiez les méthodes permettant aux clients de contacter le personnel du support technique, le mode de regroupement des incidents et l’heure à laquelle ils doivent répondre et résoudre l’incident.</span><span class="sxs-lookup"><span data-stu-id="a7795-122">Specify methods for customers to contact support staff, how incidents are grouped, and target time to respond and to resolve the incident.</span></span> <span data-ttu-id="a7795-123">Définissez la fréquence et le contenu des commentaires pour le client.</span><span class="sxs-lookup"><span data-stu-id="a7795-123">Define frequency and content of feedback to the customer.</span></span>

  - <span data-ttu-id="a7795-124">**Capacité**   définissez la taille maximale activée des sites Lync et les étapes à suivre si la limite est dépassée.</span><span class="sxs-lookup"><span data-stu-id="a7795-124">**Capacity**   Define the maximum enabled size of Lync sites and the steps to take if the limit is exceeded.</span></span> <span data-ttu-id="a7795-125">Définir le temps maximal activé pour effectuer des tâches standard, telles que le temps de récupération d’un document dans une bibliothèque de documents.</span><span class="sxs-lookup"><span data-stu-id="a7795-125">Define the maximum enabled time to do standard tasks, such as the time to retrieve a document from a document library.</span></span> <span data-ttu-id="a7795-126">Définir le nombre maximal d’utilisateurs par pool Lync et accepter un processus pour augmenter la capacité si d’autres utilisateurs sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="a7795-126">Define the maximum number of users per Lync pool and agree to a process to increase capacity if more users are added.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

