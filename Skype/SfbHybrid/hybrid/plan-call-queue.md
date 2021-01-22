---
title: Planifier une file d’attente d’appels cloud
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
description: Vue d’ensemble de l’utilisation d’un service de gestion automatique cloud avec Skype Entreprise Server 2019.
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918740"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="c937b-103">Planifier les files d’attente d’appels cloud</span><span class="sxs-lookup"><span data-stu-id="c937b-103">Plan Cloud call queues</span></span>

<span data-ttu-id="c937b-104">La file d’attente d’appels cloud est un service qui accepte les appels des clients, lit un message d’accueil, puis place ces appels dans une file d’attente lors de la recherche d’une liste pré-configurée d’agents pour répondre à ces appels.</span><span class="sxs-lookup"><span data-stu-id="c937b-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="c937b-105">Vous pouvez définir l’ensemble des agents dans les listes de distribution à messagerie ou les groupes de sécurité.</span><span class="sxs-lookup"><span data-stu-id="c937b-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="c937b-106">Votre organisation peut avoir une ou plusieurs files d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c937b-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="c937b-107">Les files d’attente d’appels sont généralement utilisées en combinaison avec les attendants automatiques.</span><span class="sxs-lookup"><span data-stu-id="c937b-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="c937b-108">En outre, les files d’attente d’appels cloud peuvent fournir :</span><span class="sxs-lookup"><span data-stu-id="c937b-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="c937b-109">Musique pendant l’attente des appelants</span><span class="sxs-lookup"><span data-stu-id="c937b-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="c937b-110">Paramètres personnalisés pour la taille maximale de la file d’attente d’appels, le délai d’attente et les options de gestion des appels</span><span class="sxs-lookup"><span data-stu-id="c937b-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="c937b-111">Un compte de ressource **(voir** [Configurer](configure-onprem-ra.md)les comptes de ressources) est affecté à chaque file d’attente d’appels sur votre système Skype Entreprise Server 2019 qui sera lié directement à une file d’attente d’appels dans le Centre d’administration Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c937b-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c937b-112">Pour plus [d’informations sur](/MicrosoftTeams/create-a-phone-system-call-queue) les files d’attente d’appels et les options et fonctionnalités existantes pour les files d’attente d’appels, voir Créer une file d’attente d’appels cloud.</span><span class="sxs-lookup"><span data-stu-id="c937b-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="c937b-113">Vous pouvez affecter plusieurs numéros de téléphone à une file d’attente d’appels, mais il doit s’agit de numéros de service Microsoft, de numéros de routage direct ou de numéros hybrides.</span><span class="sxs-lookup"><span data-stu-id="c937b-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="c937b-114">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="c937b-114">Requirements</span></span>

<span data-ttu-id="c937b-115">Les conditions suivantes supposent que Skype Entreprise Server 2019 est déjà déployé dans une topologie prise en charge.</span><span class="sxs-lookup"><span data-stu-id="c937b-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="c937b-116">Vos besoins dépendent de votre scénario :</span><span class="sxs-lookup"><span data-stu-id="c937b-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="c937b-117">Pour une nouvelle configuration des files d’attente d’appels cloud, suivez les étapes décrites dans [Configurer les comptes de ressources.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="c937b-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="c937b-118">Vous devrez créer des comptes de ressources en ligne ou dans Skype Entreprise Server 2019, et vous devrez peut-être également associer un numéro de téléphone à la file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="c937b-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="c937b-119">Outre la configuration requise ci-dessus, les conditions ci-dessous doivent être configurées pour se connecter au service de file d’attente des appels Microsoft Cloud :</span><span class="sxs-lookup"><span data-stu-id="c937b-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="c937b-120">Connectivité hybride.</span><span class="sxs-lookup"><span data-stu-id="c937b-120">Hybrid connectivity.</span></span> <span data-ttu-id="c937b-121">Si Skype Entreprise Server est déjà déployé et que vous souhaitez activer les files d’attente d’appels cloud pour vos utilisateurs locaux, vous devez vous assurer que la connectivité hybride est définie entre vos environnements locaux et en ligne.</span><span class="sxs-lookup"><span data-stu-id="c937b-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="c937b-122">Il s’agit parfois d’une configuration de domaine fractionnement.</span><span class="sxs-lookup"><span data-stu-id="c937b-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="c937b-123">Pour plus d’informations, voir Planifier la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365](plan-hybrid-connectivity.md) et configurer la connectivité hybride entre Skype Entreprise Server et [Microsoft 365 ou Office 365.](configure-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="c937b-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="c937b-124">Si vous affectez un numéro de téléphone à un compte de ressource, vous pouvez désormais utiliser la licence d’utilisateur virtuel du système téléphonique sans frais.</span><span class="sxs-lookup"><span data-stu-id="c937b-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="c937b-125">Cela offre des fonctionnalités de système téléphonique pour les numéros de téléphone au niveau de l’organisation, et vous permet de créer des fonctionnalités de numéro de téléphone et de attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="c937b-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="c937b-126">Créez un compte de ressource [local](configure-onprem-ra.md) pour chaque file d’attente d’appels et attribuez une licence et un numéro de téléphone si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c937b-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="c937b-127">Lorsque vous avez une structure solide qui répond à vos besoins et un script qui guide efficacement les clients, procédez à la configuration des comptes [de ressources.](configure-onprem-ra.md)</span><span class="sxs-lookup"><span data-stu-id="c937b-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c937b-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c937b-128">See Also</span></span>

[<span data-ttu-id="c937b-129">Configurer des comptes de ressource</span><span class="sxs-lookup"><span data-stu-id="c937b-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="c937b-130">Activer l'enregistrement des invites personnalisées à l'aide de l'interface utilisateur de téléphonie</span><span class="sxs-lookup"><span data-stu-id="c937b-130">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="c937b-131">Un standard Cloud automatique, qu’est-ce que c’est ?</span><span class="sxs-lookup"><span data-stu-id="c937b-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="c937b-132">Configurer un standard automatique dans le cloud</span><span class="sxs-lookup"><span data-stu-id="c937b-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="c937b-133"> Planifier une connectivité hybride entre Skype pour serveur d'entreprise et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="c937b-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="c937b-134">Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="c937b-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="c937b-135">Gérer les comptes de ressources dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c937b-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
