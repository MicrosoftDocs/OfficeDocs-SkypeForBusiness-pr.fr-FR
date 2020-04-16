---
title: Planifier une file d’attente d’appels sur le Cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Vue d’ensemble de l’utilisation d’un standard automatique Cloud avec Skype entreprise Server 2019.
ms.openlocfilehash: d14aeab9857f2a54e6622fb368193a2e270e0f49
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510793"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="b63e8-103">Planifier les files d’attente des appels Cloud</span><span class="sxs-lookup"><span data-stu-id="b63e8-103">Plan Cloud call queues</span></span>

<span data-ttu-id="b63e8-104">La file d’attente des appels sur le Cloud est un service qui accepte les appels client, lit un message d’accueil, puis passe ces appels dans une file d’attente lors de la recherche d’une liste préconfigurée d’agents pour répondre à ces appels.</span><span class="sxs-lookup"><span data-stu-id="b63e8-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="b63e8-105">Vous pouvez définir l’ensemble des agents dans les listes de distribution ou les groupes de sécurité à extension messagerie.</span><span class="sxs-lookup"><span data-stu-id="b63e8-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="b63e8-106">Votre organisation peut avoir une ou plusieurs files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="b63e8-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="b63e8-107">Les files d’attente d’appels sont généralement utilisées en combinaison avec des standards automatiques.</span><span class="sxs-lookup"><span data-stu-id="b63e8-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="b63e8-108">En outre, les files d’attente d’appels Cloud peuvent fournir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b63e8-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="b63e8-109">Musique pendant que les appelants sont en attente</span><span class="sxs-lookup"><span data-stu-id="b63e8-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="b63e8-110">Paramètres personnalisés pour la taille maximale, le délai d’expiration et les options de traitement des appels de la file d’attente d’appels</span><span class="sxs-lookup"><span data-stu-id="b63e8-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="b63e8-111">Chaque file d’attente est affectée à un **compte de ressource** (voir [Configure Resource Accounts](configure-onprem-ra.md)) sur votre système Skype entreprise Server 2019 qui sera lié directement à une file d’attente d’appels dans le centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b63e8-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b63e8-112">Pour plus d’informations sur les files d’attente d’appels et sur les options et les fonctionnalités disponibles pour les files d’attente d’appels, voir [Create a Cloud Call queue](/MicrosoftTeams/create-a-phone-system-call-queue) .</span><span class="sxs-lookup"><span data-stu-id="b63e8-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="b63e8-113">Vous pouvez affecter plusieurs numéros de téléphone à une file d’attente d’appels, mais il doit s’agir de numéros de service Microsoft, de numéros de routage directs ou de numéros hybrides.</span><span class="sxs-lookup"><span data-stu-id="b63e8-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="b63e8-114">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="b63e8-114">Requirements</span></span>

<span data-ttu-id="b63e8-115">La configuration requise suivante suppose que vous ayez déjà déployé Skype entreprise Server 2019 dans une topologie prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b63e8-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="b63e8-116">Vos besoins dépendent de votre scénario :</span><span class="sxs-lookup"><span data-stu-id="b63e8-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="b63e8-117">Pour une nouvelle configuration de files d’attente d’appels sur le Cloud, suivez les étapes décrites dans [Configure Resource Accounts](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="b63e8-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="b63e8-118">Vous devrez créer des comptes de ressources en ligne ou dans Skype entreprise Server 2019, et vous devrez peut-être également associer un numéro de téléphone à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="b63e8-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="b63e8-119">En plus de la configuration requise ci-dessus, les conditions suivantes doivent être configurées pour se connecter au service de file d’attente des appels de Microsoft Cloud :</span><span class="sxs-lookup"><span data-stu-id="b63e8-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="b63e8-120">Connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="b63e8-120">Hybrid connectivity.</span></span> <span data-ttu-id="b63e8-121">Si vous avez déjà déployé Skype entreprise Server et que vous souhaitez activer les files d’attente d’appels dans le Cloud pour vos utilisateurs locaux, vous devez vous assurer que la connectivité hybride est configurée entre vos environnements locaux et en ligne.</span><span class="sxs-lookup"><span data-stu-id="b63e8-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="b63e8-122">Il s’agit parfois d’une configuration de domaine fractionné.</span><span class="sxs-lookup"><span data-stu-id="b63e8-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="b63e8-123">Pour plus d’informations, voir [planifier une connectivité hybride entre Skype entreprise Server et office 365](plan-hybrid-connectivity.md) et [configurer la connectivité hybride entre Skype entreprise server et Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="b63e8-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="b63e8-124">Si vous affectez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence utilisateur virtuelle du système téléphonique économique.</span><span class="sxs-lookup"><span data-stu-id="b63e8-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="b63e8-125">Cela fournit des fonctionnalités de système téléphonique aux numéros de téléphone au niveau de l’organisation et vous permet de créer des fonctionnalités de standard automatique et de file d’attente d’appel.</span><span class="sxs-lookup"><span data-stu-id="b63e8-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="b63e8-126">Créez un [compte de ressource](configure-onprem-ra.md) local pour chaque file d’attente d’appels et attribuez une licence et un numéro de téléphone si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b63e8-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="b63e8-127">Ressources de planification supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b63e8-127">Additional planning resources</span></span>

<span data-ttu-id="b63e8-128">Le didacticiel intitulé [petite entreprise-configurer un standard automatique](/microsoftteams/tutorial-org-aa) passe par le processus de collecte d’informations sur les besoins des utilisateurs, de la planification d’une structure de standards automatiques et d’utilisateurs (et éventuellement d’appels de files d’attente), de l’écriture des invites de menu et de l’implémentation du plan dans le centre d’administration en ligne.</span><span class="sxs-lookup"><span data-stu-id="b63e8-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="b63e8-129">consultez le didacticiel et utilisez les exercices t créer votre plan.</span><span class="sxs-lookup"><span data-stu-id="b63e8-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="b63e8-130">Lorsque vous disposez d’une structure solide qui répond à vos besoins et d’un script qui guide les clients de manière efficace, passez à la [Configuration des comptes de ressources](configure-onprem-ra.md).</span><span class="sxs-lookup"><span data-stu-id="b63e8-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b63e8-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b63e8-131">See Also</span></span>

[<span data-ttu-id="b63e8-132">Configurer des comptes de ressources</span><span class="sxs-lookup"><span data-stu-id="b63e8-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="b63e8-133">Activer l'enregistrement des invites personnalisées à l'aide de l'interface utilisateur de téléphonie</span><span class="sxs-lookup"><span data-stu-id="b63e8-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="b63e8-134">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="b63e8-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="b63e8-135">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="b63e8-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="b63e8-136">Planifier la connectivité hybride entre Skype Entreprise Server et Office 365</span><span class="sxs-lookup"><span data-stu-id="b63e8-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

<span data-ttu-id="b63e8-137">[Configurer la connectivité hybride entre Skype Entreprise Server et Office 365](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="b63e8-137">[Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md)</span></span>

[<span data-ttu-id="b63e8-138">Gérer les comptes de ressources dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b63e8-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
