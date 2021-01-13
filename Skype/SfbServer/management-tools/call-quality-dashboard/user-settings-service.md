---
title: Service de paramètres utilisateur pour le tableau de bord de qualité des appels (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Résumé : Découvrez le service paramètres utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels. Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803035"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="28b79-104">Service de paramètres utilisateur pour le tableau de bord de qualité des appels (CQD)</span><span class="sxs-lookup"><span data-stu-id="28b79-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="28b79-105">**Résumé :** Découvrez le service de paramètres utilisateur, qui fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="28b79-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="28b79-106">Le Tableau de bord de qualité des appels est un outil pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="28b79-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="28b79-107">Le service paramètres utilisateur fait partie de l’API référentiel pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="28b79-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="28b79-108">Service de paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="28b79-108">User Settings Service</span></span>

<span data-ttu-id="28b79-109">Les paramètres utilisateur sont des paires clé-valeur que les applications peuvent utiliser pour stocker des métadonnées à diverses fins, y compris la personnalisation des comportements d’application par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28b79-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="28b79-110">Chaque utilisateur reçoit un stockage pour les paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28b79-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="28b79-111">Seuls les propriétaires peuvent ajouter, modifier et supprimer des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="28b79-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="28b79-112">**Paramètres globaux**</span><span class="sxs-lookup"><span data-stu-id="28b79-112">**Global Settings**</span></span>
  
<span data-ttu-id="28b79-113">Les paramètres globaux sont les paramètres utilisateur de l’utilisateur système, et tous les utilisateurs y ont accès en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="28b79-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="28b79-114">Les paramètres globaux sont des constantes : ils sont créés lors de la création du référentiel et ne changent jamais.</span><span class="sxs-lookup"><span data-stu-id="28b79-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="28b79-115">Chaque utilisateur peut remplacer les paramètres globaux en créant des paramètres utilisateur avec les mêmes clés.</span><span class="sxs-lookup"><span data-stu-id="28b79-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="28b79-116">Lorsque l’application demande les paramètres utilisateur effectifs, l’API renvoie un ensemble de paramètres globaux fusionnés avec les paramètres utilisateur, chaque paramètre utilisateur ayant pour effet de se supercaler au paramètre global respectif si les clés sont identiques.</span><span class="sxs-lookup"><span data-stu-id="28b79-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="28b79-117">L’API peut également renvoyer uniquement les paramètres utilisateur afin que les applications trouvent les paramètres qui sont à la place.</span><span class="sxs-lookup"><span data-stu-id="28b79-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="28b79-118">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="28b79-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="28b79-119">**Opération**</span><span class="sxs-lookup"><span data-stu-id="28b79-119">**Operation**</span></span>|<span data-ttu-id="28b79-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="28b79-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="28b79-121">Obtention des paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="28b79-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="28b79-122">Obtenir les paramètres utilisateur renvoie la liste des paramètres d’un utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="28b79-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="28b79-123">Obtention d’un paramètre utilisateur</span><span class="sxs-lookup"><span data-stu-id="28b79-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="28b79-124">Obtenir le paramètre utilisateur renvoie un paramètre utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="28b79-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

