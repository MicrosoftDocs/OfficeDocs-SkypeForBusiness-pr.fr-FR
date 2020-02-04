---
title: 'Lync Server 2013 : Gestion des objets Contact Exchange hébergés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="72d46-102">Gestion des objets Contact Exchange hébergés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72d46-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72d46-103">_**Dernière modification de la rubrique :** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="72d46-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="72d46-104">Vous devez configurer un objet contact pour chaque numéro de standard automatique et ce numéro d’accès d’abonné dans votre déploiement sur site.</span><span class="sxs-lookup"><span data-stu-id="72d46-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="72d46-105">Pour l’intégration à la messagerie unifiée Exchange hébergée, ocsumutil. exe ne peut pas être utilisé pour gérer les objets de contact, car cela dépend des paramètres de messagerie unifiée d’Exchange Active Directory.</span><span class="sxs-lookup"><span data-stu-id="72d46-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="72d46-106">Dans un déploiement sur site, Lync Server 2013 et la messagerie unifiée Exchange hébergée sont installés dans des forêts distinctes sans approbation.</span><span class="sxs-lookup"><span data-stu-id="72d46-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="72d46-107">Pour des raisons de sécurité, les administrateurs de Lync Server 2013 ne disposent pas d’un accès direct aux paramètres Active Directory UM Exchange.</span><span class="sxs-lookup"><span data-stu-id="72d46-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="72d46-108">Par conséquent, Lync Server 2013 fournit un modèle différent pour gérer les objets de contact dans un *espace d’adressage SIP partagé* , accessible à la fois à Lync Server 2013 et au service de messagerie unifiée Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="72d46-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="72d46-109">Flux de travail d’objets de contact hébergés</span><span class="sxs-lookup"><span data-stu-id="72d46-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="72d46-110">Vous trouverez ci-après les étapes générales d’utilisation de l’administrateur de votre client Exchange hébergé pour gérer les objets de contact :</span><span class="sxs-lookup"><span data-stu-id="72d46-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="72d46-111">L’administrateur Exchange demande des numéros de téléphone pour l’accès de l’abonné de messagerie unifiée et les objets de contact du standard automatique.</span><span class="sxs-lookup"><span data-stu-id="72d46-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="72d46-112">L’administrateur Lync Server 2013 crée un objet contact pour chaque numéro de téléphone et attribue une stratégie de messagerie vocale hébergée à chaque objet contact.</span><span class="sxs-lookup"><span data-stu-id="72d46-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="72d46-113">L’administrateur Lync Server 2013 fournit les numéros de téléphone à l’administrateur Exchange.</span><span class="sxs-lookup"><span data-stu-id="72d46-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="72d46-114">L’administrateur Exchange affecte les numéros de téléphone aux plans de numérotation de messagerie unifiée appropriés aux standards automatiques et aux abonnés.</span><span class="sxs-lookup"><span data-stu-id="72d46-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72d46-115">Il n’est pas nécessaire de configurer des paramètres de plan de numérotation Lync Server 2013 sur les objets de contact comme il y a des déploiements sur site.</span><span class="sxs-lookup"><span data-stu-id="72d46-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="72d46-116">Configuration d’objets de contact hébergés</span><span class="sxs-lookup"><span data-stu-id="72d46-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72d46-117">Pour que les objets de contact Lync Server 2013 puissent être activés pour la messagerie unifiée Exchange hébergée, une stratégie de messagerie vocale hébergée qui s’applique à ces derniers doit être déployée.</span><span class="sxs-lookup"><span data-stu-id="72d46-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="72d46-118">La stratégie peut être une étendue globale, de niveau site ou par utilisateur, dans la mesure où elle s’applique à l’objet de contact que vous souhaitez activer.</span><span class="sxs-lookup"><span data-stu-id="72d46-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="72d46-119">Pour plus d’informations, reportez-vous <A href="lync-server-2013-hosted-voice-mail-policies.md">à stratégies de messagerie vocale hébergées dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="72d46-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="72d46-120">Pour configurer les objets de contact du standard automatique et de l’accès abonné hébergés dans un déploiement en local, vous devez utiliser les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="72d46-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="72d46-121">**New-CsExUmContact** crée un nouvel objet contact pour la messagerie unifiée hébergée.</span><span class="sxs-lookup"><span data-stu-id="72d46-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="72d46-122">**Set-CsExUmContact** modifie un objet contact existant pour le message unifié Exchange hébergé.</span><span class="sxs-lookup"><span data-stu-id="72d46-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="72d46-123">L’exemple suivant crée un objet contact de standard automatique :</span><span class="sxs-lookup"><span data-stu-id="72d46-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="72d46-124">Cet exemple crée un nouvel objet de contact de MU Exchange avec l’adresse SIP sip :exumaa1@fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="72d46-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="72d46-125">Le nom du pool sur lequel le service de bureau d’enregistrement Lync Server 2013 est en cours d’exécution est RedmondPool.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="72d46-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="72d46-126">L’unité d’organisation Active Directory dans laquelle ces informations seront stockées est UO = ExUmContacts, DC = litwareinc, DC = com.</span><span class="sxs-lookup"><span data-stu-id="72d46-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="72d46-127">Le numéro de téléphone de l’objet contact est 2065554567.</span><span class="sxs-lookup"><span data-stu-id="72d46-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="72d46-128">Le paramètre facultatif-autoattende $True spécifie que cet objet est un objet de contact de standard automatique.</span><span class="sxs-lookup"><span data-stu-id="72d46-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="72d46-129">La définition du paramètre-standard automatique sur false (par défaut) spécifie un objet contact d’accès abonné.</span><span class="sxs-lookup"><span data-stu-id="72d46-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="72d46-130">Pour plus d’informations sur les applets de nouvelle-CsExUmContact et Set-CsExUmContact, voir la documentation Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72d46-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

