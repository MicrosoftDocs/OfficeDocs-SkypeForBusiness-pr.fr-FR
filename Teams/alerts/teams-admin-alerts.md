---
title: Microsoft Teams Surveillance et alerte
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
description: Découvrez les fonctionnalités Teams d’alertes et de notifications disponibles dans le Microsoft Teams d’administration.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: c99cc9af08fb1353e0c94e6f8bf156df04327d49
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684604"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="b32e9-103">Microsoft Teams surveillance et alertes</span><span class="sxs-lookup"><span data-stu-id="b32e9-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="b32e9-104">De nouvelles fonctionnalités de surveillance et d’alerte Microsoft Teams fonctionnalités sont disponibles dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="b32e9-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="b32e9-105">Utilisez différents jeux de règles disponibles sous la section **Notifications & alertes** dans le Centre d’administration Teams pour surveiller Teams fonctionnalités et recevoir des alertes.</span><span class="sxs-lookup"><span data-stu-id="b32e9-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="b32e9-106">Par exemple, vous pouvez surveiller activement l’état d’Teams de certains appareils, tels que les téléphones IP, les barres de collaboration, etc., s’ils se déconnectent de manière inattendue.</span><span class="sxs-lookup"><span data-stu-id="b32e9-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="b32e9-107">Votre organisation peut utiliser la surveillance Teams’alerte pour les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b32e9-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="b32e9-108">Gérer automatiquement les Teams fonctionnalités de gestion des ressources</span><span class="sxs-lookup"><span data-stu-id="b32e9-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="b32e9-109">Soyez averti s’ils indiquent quelque chose d’inattendu.</span><span class="sxs-lookup"><span data-stu-id="b32e9-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="b32e9-110">Pour revenir sur la bonne voie, faites des actions correctives.</span><span class="sxs-lookup"><span data-stu-id="b32e9-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="b32e9-111">Gérer la surveillance et les alertes</span><span class="sxs-lookup"><span data-stu-id="b32e9-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="b32e9-112">Vous devez être un administrateur global dans Microsoft 365 ou un Teams de service pour configurer des règles d’alerte.</span><span class="sxs-lookup"><span data-stu-id="b32e9-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="b32e9-113">Voir [Utiliser Teams](../using-admin-roles.md) rôles d’administrateur pour gérer Teams pour en savoir plus sur Teams rôles d’administrateur et les rapports accessibles à chaque rôle d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="b32e9-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="b32e9-114">Se connecter au Centre d’administration de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b32e9-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="b32e9-115">Dans le groupe de navigation de gauche, **sélectionnez Notifications & les alertes.**</span><span class="sxs-lookup"><span data-stu-id="b32e9-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="b32e9-116">Choisissez la règle à configurer à partir de **Règles.**</span><span class="sxs-lookup"><span data-stu-id="b32e9-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="b32e9-117">Teams référence des règles de surveillance</span><span class="sxs-lookup"><span data-stu-id="b32e9-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="b32e9-118">Nous continuons d’ajouter et d’améliorer l Teams de surveillance en ajoutant diverses fonctionnalités de surveillance et de configuration.</span><span class="sxs-lookup"><span data-stu-id="b32e9-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="b32e9-119">Voici une liste des règles de surveillance Teams disponibles dans le Centre Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="b32e9-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="b32e9-120">Règle</span><span class="sxs-lookup"><span data-stu-id="b32e9-120">Rule</span></span>  |<span data-ttu-id="b32e9-121">Fonctionnalité de surveillance</span><span class="sxs-lookup"><span data-stu-id="b32e9-121">Monitoring capability</span></span>|<span data-ttu-id="b32e9-122">Qu’est-ce qui est surveillé ?</span><span class="sxs-lookup"><span data-stu-id="b32e9-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="b32e9-123">État d’état des appareils</span><span class="sxs-lookup"><span data-stu-id="b32e9-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="b32e9-124">Teams Appareils</span><span class="sxs-lookup"><span data-stu-id="b32e9-124">Teams Devices</span></span> | <span data-ttu-id="b32e9-125">Pro surveiller activement les Teams s’ils se déconnectent.</span><span class="sxs-lookup"><span data-stu-id="b32e9-125">Pro-actively monitor Teams devices if they go offline.</span></span>|