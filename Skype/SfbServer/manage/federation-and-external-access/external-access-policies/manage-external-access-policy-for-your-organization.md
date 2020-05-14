---
title: Gestion de la stratégie d’accès externe pour votre organisation
ms.reviewer: ''
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Une fois que vous avez déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès externes qui seront pris en charge pour votre organisation.
ms.openlocfilehash: e3feecfffa591df5433ce45526ec236ca6ef8b42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221658"
---
# <a name="manage-external-access-policy-for-your-organization"></a><span data-ttu-id="29761-103">Gestion de la stratégie d’accès externe pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="29761-103">Manage external access policy for your organization</span></span>

<span data-ttu-id="29761-104">Une fois que vous avez déployé un ou plusieurs serveurs Edge, vous devez activer les types d’accès externes qui seront pris en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="29761-104">After deploying one or more Edge Servers, you must enable the types of external access that will be supported for your organization.</span></span>

<span data-ttu-id="29761-p101">Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge. Les étendues de stratégies suivantes sont disponibles à des fins de création et de configuration. Par défaut, la stratégie globale est créée mais elle ne peut pas être supprimée.</span><span class="sxs-lookup"><span data-stu-id="29761-p101">By default, there are no policies configured to support external user access, including remote user access, federated user access, even if you have already enabled external user access support for your organization. To control the use of external user access, you must configure one or more policies, specifying the type of external user access supported for each policy. The following policy scopes are available for creation and configuration. By default, the Global policy is created, but cannot be deleted.</span></span>

  - <span data-ttu-id="29761-109">**Stratégie globale**   la stratégie globale est créée lorsque vous déployez vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="29761-109">**Global policy**   The global policy is created when you deploy your Edge Servers.</span></span> <span data-ttu-id="29761-110">Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="29761-110">By default, no external user access options are enabled in the global policy.</span></span> <span data-ttu-id="29761-111">Pour prendre en charge l’accès utilisateur externe au niveau global, vous devez configurer la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateur externe.</span><span class="sxs-lookup"><span data-stu-id="29761-111">To support external user access at the global level, you configure the global policy to support one or more types of external user access options.</span></span> <span data-ttu-id="29761-112">La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="29761-112">The global policy applies to all users in your organization, but site policies and user policies override the global policy.</span></span> <span data-ttu-id="29761-113">Si vous supprimez la stratégie globale, vous ne la supprimez pas.</span><span class="sxs-lookup"><span data-stu-id="29761-113">If you delete the global policy, you do not remove it.</span></span> <span data-ttu-id="29761-114">Au lieu de cela, vous la réinitialisez au paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="29761-114">Instead, you reset it to the default setting.</span></span>

  - <span data-ttu-id="29761-115">**Stratégie de site**   Vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="29761-115">**Site policy**   You can create and configure one or more site policies to limit support for external user access to specific sites.</span></span> <span data-ttu-id="29761-116">La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="29761-116">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="29761-117">Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné.</span><span class="sxs-lookup"><span data-stu-id="29761-117">For example, if you enable remote user access in the global policy, you might specify a site policy that disables remote user access for a specific site.</span></span> <span data-ttu-id="29761-118">Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur qui supplante la configuration de la stratégie de site.</span><span class="sxs-lookup"><span data-stu-id="29761-118">By default, a site policy is applied to all users of that site, but you can assign a user policy to a user to override the site policy setting.</span></span>

  - <span data-ttu-id="29761-119">**Stratégie d’utilisateur**   Vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="29761-119">**User policy**   You can create and configure one or more user policies to limit support for remote user access to specific users.</span></span> <span data-ttu-id="29761-120">La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée.</span><span class="sxs-lookup"><span data-stu-id="29761-120">The configuration in the user policy overrides the global and site policy, but only for the specific users to whom the user policy is assigned.</span></span> <span data-ttu-id="29761-121">Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="29761-121">For example, if you enable remote user access in the global policy and site policy, you might specify a user policy that disables remote user access and then assign that user policy to specific users.</span></span> <span data-ttu-id="29761-122">Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs pour qu’elle prenne effet.</span><span class="sxs-lookup"><span data-stu-id="29761-122">If you create a user policy, you must apply it to one or more users before it takes effect.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="29761-123">Les paramètres de stratégie appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="29761-123">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="29761-124">La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente).</span><span class="sxs-lookup"><span data-stu-id="29761-124">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="29761-125">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="29761-125">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


<span data-ttu-id="29761-126">Ces options incluent les types d’accès externe suivants :</span><span class="sxs-lookup"><span data-stu-id="29761-126">These options include the following types of external access:</span></span>

  - <span data-ttu-id="29761-127">**Activer les communications avec les utilisateurs fédérés**   Activez cette option si vous voulez assurer la prise en charge de l’accès des utilisateurs aux domaines partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="29761-127">**Enable communications with federated users**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="29761-128">Ce paramètre configure la possibilité pour les utilisateurs de communiquer avec d’autres domaines fédérés SIP, ainsi que des fournisseurs hébergés comme Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="29761-128">This setting configures the ability for users to communicate with other SIP federated domains, as well as Hosted providers like Microsoft 365 or Office 365.</span></span> 


  - <span data-ttu-id="29761-129">**Autoriser les communications avec des utilisateurs distants**   Activez cette option si vous souhaitez que les utilisateurs de votre organisation qui se trouvent à l’extérieur de votre pare-feu, par exemple les télétravailleurs et les travailleurs itinérants, puissent se connecter à Skype Entreprise Server via Internet.</span><span class="sxs-lookup"><span data-stu-id="29761-129">**Enable communications with remote users**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server over the Internet.</span></span>

  - <span data-ttu-id="29761-130">**Autoriser les communications avec des utilisateurs publics**   Activez cette option si vous souhaitez que les utilisateurs internes puissent communiquer avec les contacts du fournisseur de services de messagerie instantanée publics.</span><span class="sxs-lookup"><span data-stu-id="29761-130">**Enable communications with public users**   Enable this option if you want internal users to be able to communicate with public IM provider contacts.</span></span>
   

> [!NOTE]  
> <span data-ttu-id="29761-131">En plus d’activer la prise en charge de l’accès des utilisateurs externes, vous devez aussi configurer les stratégies permettant de contrôler l’utilisation de l’accès des utilisateurs externes dans votre organisation avant que tout type d’accès des utilisateurs externes ne soit mis à la disposition des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="29761-131">In addition to enabling external user access support, you must also configure policies to control the use of external user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="29761-132">Pour plus d’informations sur la création, la configuration et l’application des stratégies d’accès des utilisateurs externes, consultez [Activer ou désactiver l'accès des utilisateurs à distance](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="29761-132">For details about creating, configuring, and applying policies for external user access see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>



<span data-ttu-id="29761-133">**Pour afficher les stratégies d’accès externe à l’aide des applets de commande Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="29761-133">**To view external access policies by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="29761-134">Vous pouvez afficher les stratégies d’accès externe à l’aide de Skype Entreprise Server Management Shell et de l’applet de commande **Get-CsExternalAccessPolicy**.</span><span class="sxs-lookup"><span data-stu-id="29761-134">You can view external access policies by using Skype for Business Server Management Shell and the **Get-CsExternalAccessPolicy** cmdlet.</span></span> <span data-ttu-id="29761-135">Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29761-135">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="29761-136">Pour afficher des informations sur l’ensemble de vos stratégies d’accès externes, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="29761-136">To view information about all your external access policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
    `Get-CsExternalAccessPolicy`
    
    <span data-ttu-id="29761-137">Cette commande renvoie des informations comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="29761-137">This command returns information similar to the following:</span></span>
    
    ```console
    Identity                          : Global
    Description                       :
    EnableFederationAccess            : False
    EnableXmppAccess                  : False
    EnablePublicCloudAccess           : False
    EnablePublicCloudAudioVideoAccess : False
    EnableOutsideAccess               : False
    ```
