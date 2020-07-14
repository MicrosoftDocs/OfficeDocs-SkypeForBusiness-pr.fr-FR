---
title: Conformité de la communication pour Microsoft teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: En savoir plus sur la conformité des communications, qui fait partie de la solution de risque Insider de Microsoft Teams (incluse dans la fonctionnalité de conformité des communications M365).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01d9906044fe0ea8472cd8bb2ba8ccf247cdbeb9
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121694"
---
# <a name="communication-compliance-for-microsoft-teams"></a><span data-ttu-id="a5a9f-103">Conformité de la communication pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a5a9f-103">Communication compliance for Microsoft Teams</span></span>

<span data-ttu-id="a5a9f-104">La conformité aux communications fait partie de la nouvelle solution de risque Insider dans Microsoft 365 qui permet de réduire les risques de communication en vous aidant à détecter, capturer et utiliser les actions de correction pour les messages inappropriés au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-104">Communication compliance is part of the new insider risk solution set in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and take remediation actions for inappropriate messages in your organization.</span></span> <span data-ttu-id="a5a9f-105">Il permet d’identifier le langage injurieux et le harcèlement dans les canaux d’équipe ou 1:1 et les discussions de groupe.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-105">It helps in identifying Offensive language and anti-harassment in Team Channels or 1:1 and Group chats.</span></span> <span data-ttu-id="a5a9f-106">Vous pouvez également définir des stratégies pour voir si des informations sensibles sont partagées dans le cadre de canaux d’équipe ou de la 1:1 et des discussions de groupe.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-106">You can also set policies to see if any Sensitive information is being shared as part of Team channels or 1:1 and Group chats.</span></span> <span data-ttu-id="a5a9f-107">Pour plus d’informations sur les différents types de stratégies et la façon de procéder à la configuration, reportez-vous à l' [article M365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span><span class="sxs-lookup"><span data-stu-id="a5a9f-107">For more information on different types of policies and how to set up refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-teams"></a><span data-ttu-id="a5a9f-108">Utilisation de la conformité de la communication dans teams</span><span class="sxs-lookup"><span data-stu-id="a5a9f-108">How to use communication compliance in Teams</span></span>

### <a name="identify-inappropriate-messages"></a><span data-ttu-id="a5a9f-109">Identifier les messages indésirables</span><span class="sxs-lookup"><span data-stu-id="a5a9f-109">Identify inappropriate messages</span></span>

<span data-ttu-id="a5a9f-110">Si vous voulez identifier les messages envoyés dans Microsoft Teams (1:1, les conversations de groupe ou les conversations de canal), vous pouvez activer les stratégies pour détecter ce problème et le réviseur peut consulter les messages et prendre les mesures nécessaires comme envoyer du matériel de formation ou faire remonter aux autorités appropriées.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-110">If you want to identify any messages that are sent in Microsoft Teams (1:1, Group Chats or Channel conversations) contain Offensive Language or anti-harassment, you can enable policies to identify this and the reviewer can look into the messages and take necessary steps like sending training material or escalate to the right authorities.</span></span>

### <a name="identify-sensitive-or-regulatory-information"></a><span data-ttu-id="a5a9f-111">Identifier les informations sensibles ou réglementaires</span><span class="sxs-lookup"><span data-stu-id="a5a9f-111">Identify sensitive or Regulatory information</span></span>

<span data-ttu-id="a5a9f-112">Si vous souhaitez analyser les messages envoyés dans Microsoft Teams (1:1, discussions de groupe ou conversations de canal) pour les informations sensibles ou les types de réglementation, vous pouvez choisir des stratégies qui prennent en charge les types de conformité ou sensibles prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-112">If you want to scan messages sent in Microsoft Teams (1:1, Group Chats or Channel conversations) for sensitive information or regulatory types, you can choose policies that support predefined sensitive or regulatory types.</span></span>

> [!NOTE]
> <span data-ttu-id="a5a9f-113">Les canaux privés ne sont pas pris en charge par la conformité des communications.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-113">Private channels are not supported by communication compliance.</span></span>

### <a name="custom-policy"></a><span data-ttu-id="a5a9f-114">Stratégie personnalisée</span><span class="sxs-lookup"><span data-stu-id="a5a9f-114">Custom Policy</span></span>

<span data-ttu-id="a5a9f-115">Utilisez ce modèle pour configurer des canaux de communication spécifiques, des conditions de détection individuelles et la quantité de contenu à surveiller et à réviser au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-115">Use this template to configure specific communication channels, individual detection conditions, and the amount of content to monitor and review in your organization.</span></span>

### <a name="custom-trainable-classifier"></a><span data-ttu-id="a5a9f-116">Classificateur pour le convoi personnalisé</span><span class="sxs-lookup"><span data-stu-id="a5a9f-116">Custom Trainable classifier</span></span>

<span data-ttu-id="a5a9f-117">Utilisez des classifieurs à la demande quand l’un des classifieurs prêts à l’emploi ne répond pas à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-117">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="a5a9f-118">Le classificateur Microsoft 365 est un outil qui vous permet d’apprendre à reconnaître divers types de contenu en leur fournissant des exemples.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-118">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="a5a9f-119">Formation le classificateur implique d’abord de lui donner des exemples qui sont sélectionnés par l’utilisateur et qui correspondent à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-119">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="a5a9f-120">Ensuite, après avoir traité ces exemples, vous testez les prédictions en lui donnant un mélange d’échantillons positifs et négatifs.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-120">Then, after it has processed those samples, you test the predictions by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="a5a9f-121">Pour plus d’informations à ce sujet, reportez-vous à l' [article M365](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) pour plus d’informations sur cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-121">To Lean more about this refer to the [M365 article](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier) for more on this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="a5a9f-122">La conformité des communications prend désormais en charge les déploiements hybrides Exchange.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-122">Communication compliance now supports Exchange hybrid deployments.</span></span>

<span data-ttu-id="a5a9f-123">Compliance Compliance prend en charge l’historique des conversations pour les messages correspondant aux stratégies.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-123">Communication compliance supports conversation history for any messages that match the polices.</span></span> <span data-ttu-id="a5a9f-124">Cela fournit un contexte à l’examen de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-124">This provides context to the investigating admin.</span></span>

:::image type="content" source="media/communication-compliance-1.png" alt-text="Écran de conformité de la communication dans Microsoft Teams.":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a><span data-ttu-id="a5a9f-126">Où les stratégies de communication peuvent être appliquées dans teams</span><span class="sxs-lookup"><span data-stu-id="a5a9f-126">Where communication policies can be applied in Teams</span></span>

<span data-ttu-id="a5a9f-127">Les stratégies de conformité des communications peuvent être configurées pour les messages envoyés en équipe aux niveaux suivants :</span><span class="sxs-lookup"><span data-stu-id="a5a9f-127">Communication compliance policies can be setup for messages sent in Teams at the following levels:</span></span>

- <span data-ttu-id="a5a9f-128">Niveau utilisateur : un administrateur peut configurer des stratégies à un niveau utilisateur individuel ou l’appliquer à tous les utilisateurs du client.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-128">User level : An admin can set up policies at an individual user level or apply it to all the users on the tenant.</span></span> <span data-ttu-id="a5a9f-129">Cela ne concerne que les messages envoyés par un utilisateur dans 1:1 ou les discussions de groupe.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-129">This will only covers messages that a user sent in 1:1 or Group chats.</span></span>
- <span data-ttu-id="a5a9f-130">Niveau d’équipe : un administrateur peut également configurer des stratégies pour une équipe.</span><span class="sxs-lookup"><span data-stu-id="a5a9f-130">Team Level: An admin can also set up policies on a team.</span></span> <span data-ttu-id="a5a9f-131">Tous les messages envoyés dans ce canal par l’équipe (messages de canal privé ne sont pas pris en charge).</span><span class="sxs-lookup"><span data-stu-id="a5a9f-131">This covers all the messages sent in the channel in that team (Private channel messages are not supported).</span></span>
