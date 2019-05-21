---
title: Service des paramètres utilisateur pour le tableau de bord de qualité des appels (bord)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Résumé: en savoir plus sur le service des paramètres d’utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels. Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.'
ms.openlocfilehash: e5e068d66adb325900b055a19aedcfaeabf4f2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274484"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="a9f4c-104">Service des paramètres utilisateur pour le tableau de bord de qualité des appels (bord)</span><span class="sxs-lookup"><span data-stu-id="a9f4c-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="a9f4c-105">**Résumé:** En savoir plus sur le service des paramètres d’utilisateur, qui fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a9f4c-106">Le tableau de bord de qualité des appels est un outil pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a9f4c-107">Le service de paramètres utilisateur fait partie de l’API du référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="a9f4c-108">Service de paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="a9f4c-108">User Settings Service</span></span>

<span data-ttu-id="a9f4c-109">Les paramètres utilisateur sont des paires clé-valeur que les applications peuvent utiliser pour stocker des métadonnées pour différentes raisons, notamment la personnalisation des comportements d’application par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="a9f4c-110">Chaque utilisateur reçoit un espace de stockage pour les paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="a9f4c-111">Seuls les propriétaires peuvent ajouter, modifier et supprimer des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="a9f4c-112">**Paramètres globaux**</span><span class="sxs-lookup"><span data-stu-id="a9f4c-112">**Global Settings**</span></span>
  
<span data-ttu-id="a9f4c-113">Les paramètres globaux sont les paramètres utilisateur appartenant à l’utilisateur système, et tous les utilisateurs y ont accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="a9f4c-114">Les paramètres globaux sont des constantes: elles sont créées lors de la création du référentiel et ne changent jamais.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="a9f4c-115">Chaque utilisateur peut remplacer les paramètres globaux en créant des paramètres utilisateur avec les mêmes clés.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="a9f4c-116">Lorsque l’application demande les paramètres d’utilisateur efficaces, l’API renvoie un ensemble de paramètres globaux fusionnés avec les paramètres utilisateur, et chaque paramètre utilisateur remplace le paramètre global correspondant si les clés sont identiques.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="a9f4c-117">L’API peut également renvoyer uniquement les paramètres utilisateur de sorte que les applications puissent savoir quels paramètres sont remplacés.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="a9f4c-118">Les opérations REST sont comprises dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="a9f4c-119">**Opération**</span><span class="sxs-lookup"><span data-stu-id="a9f4c-119">**Operation**</span></span>|<span data-ttu-id="a9f4c-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="a9f4c-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a9f4c-121">Obtention des paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="a9f4c-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="a9f4c-122">Obtenir les paramètres d’utilisateur renvoie une liste de paramètres pour un utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="a9f4c-123">Obtention d’un paramètre utilisateur</span><span class="sxs-lookup"><span data-stu-id="a9f4c-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="a9f4c-124">Le paramètre Get est un paramètre utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="a9f4c-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

