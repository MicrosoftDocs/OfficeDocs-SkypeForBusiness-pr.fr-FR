---
title: Surveillance et alertes de Microsoft Teams
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Découvrez les fonctionnalités d’alertes et de notifications Teams disponibles dans le Centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1be3ca52d4b03cfbf82d82310148ef4c2bb7f06d
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819458"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="0b811-103">Surveillance et alertes de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0b811-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="0b811-104">De nouvelles fonctionnalités de surveillance et d’alerte pour Microsoft Teams sont disponibles dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="0b811-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="0b811-105">Utilisez différents jeux de règles disponibles sous la section **Notifications & dans** le Centre d’administration Teams pour surveiller les fonctionnalités de Teams et recevoir des alertes.</span><span class="sxs-lookup"><span data-stu-id="0b811-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="0b811-106">Par exemple, vous pouvez surveiller activement l’état d’état des appareils Teams, tels que les téléphones IP, les barres de collaboration, etc., s’ils se déconnectent de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="0b811-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="0b811-107">Votre organisation peut utiliser la surveillance et l’alerte de Teams pour faire les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0b811-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="0b811-108">Gérer automatiquement les fonctionnalités de Teams</span><span class="sxs-lookup"><span data-stu-id="0b811-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="0b811-109">Soyez averti s’ils indiquent quelque chose d’inattendu.</span><span class="sxs-lookup"><span data-stu-id="0b811-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="0b811-110">Pour revenir sur la bonne voie, faites des actions correctives.</span><span class="sxs-lookup"><span data-stu-id="0b811-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="0b811-111">Gérer la surveillance et les alertes</span><span class="sxs-lookup"><span data-stu-id="0b811-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="0b811-112">Vous devez être un administrateur global de Microsoft 365 ou un administrateur de service Teams pour configurer des règles d’alerte.</span><span class="sxs-lookup"><span data-stu-id="0b811-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="0b811-113">Pour en savoir plus sur les rôles d’administrateur teams et les rapports accessibles à chaque rôle d’administrateur, voir Utiliser les rôles d’administrateur Teams pour gérer [Teams.](../using-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0b811-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="0b811-114">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0b811-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="0b811-115">Dans le groupe de navigation de gauche, **sélectionnez Notifications & les alertes.**</span><span class="sxs-lookup"><span data-stu-id="0b811-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="0b811-116">Choisissez la règle à configurer à partir de **Règles.**</span><span class="sxs-lookup"><span data-stu-id="0b811-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="0b811-117">Référence aux règles de surveillance teams</span><span class="sxs-lookup"><span data-stu-id="0b811-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="0b811-118">Nous continuons d’ajouter et d’améliorer l’expérience de surveillance de Teams en ajoutant diverses fonctionnalités de surveillance et de configuration.</span><span class="sxs-lookup"><span data-stu-id="0b811-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="0b811-119">Voici une liste des règles de surveillance de Teams actuellement disponibles dans le Centre d’administration Teams.</span><span class="sxs-lookup"><span data-stu-id="0b811-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="0b811-120">Règle</span><span class="sxs-lookup"><span data-stu-id="0b811-120">Rule</span></span>  |<span data-ttu-id="0b811-121">Fonctionnalité de surveillance</span><span class="sxs-lookup"><span data-stu-id="0b811-121">Monitoring capability</span></span>|<span data-ttu-id="0b811-122">Qu’est-ce qui est surveillé ?</span><span class="sxs-lookup"><span data-stu-id="0b811-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="0b811-123">État d’état des appareils</span><span class="sxs-lookup"><span data-stu-id="0b811-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="0b811-124">Appareils Teams</span><span class="sxs-lookup"><span data-stu-id="0b811-124">Teams Devices</span></span> | <span data-ttu-id="0b811-125">Surveillez activement les appareils Teams s’ils sont hors connexion.</span><span class="sxs-lookup"><span data-stu-id="0b811-125">Pro-actively monitor Teams devices if they go offline.</span></span>|
