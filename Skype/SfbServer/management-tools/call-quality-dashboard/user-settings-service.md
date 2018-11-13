---
title: Service de paramètres utilisateur pour le tableau de bord qualité appel (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 'Résumé : En savoir plus sur le Service de paramètres utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité. Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.'
ms.openlocfilehash: 9e72d051699269b404d72e77ca00923b8ca240a3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293762"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="5f891-104">Service de paramètres utilisateur pour le tableau de bord qualité appel (CQD)</span><span class="sxs-lookup"><span data-stu-id="5f891-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="5f891-105">**Résumé :** Obtenir des informations sur le Service de paramètres utilisateur, qui fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="5f891-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5f891-106">Tableau de bord de qualité des appels est un outil de Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f891-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5f891-107">Le Service de paramètres utilisateur fait partie de l’API de référentiel pour appeler le tableau de bord qualité.</span><span class="sxs-lookup"><span data-stu-id="5f891-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="5f891-108">Service de paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f891-108">User Settings Service</span></span>

<span data-ttu-id="5f891-109">Paramètres de l’utilisateur sont des paires clé-valeur que les applications peuvent utiliser pour stocker les métadonnées à des fins diverses, notamment la personnalisation de l’application à la fois par utilisateur comportements.</span><span class="sxs-lookup"><span data-stu-id="5f891-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="5f891-110">Chaque utilisateur reçoit un stockage pour les paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f891-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="5f891-111">Seuls les propriétaires peuvent ajouter, modifier et supprimer les paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5f891-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="5f891-112">**Paramètres globaux**</span><span class="sxs-lookup"><span data-stu-id="5f891-112">**Global Settings**</span></span>
  
<span data-ttu-id="5f891-113">Les paramètres globaux sont les paramètres utilisateur appartenant à l’utilisateur du système et tous les utilisateurs ont accès en lecture seule pour les.</span><span class="sxs-lookup"><span data-stu-id="5f891-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="5f891-114">Les paramètres globaux sont des constantes : ils sont créés pendant la création du référentiel, et ils ne changent jamais.</span><span class="sxs-lookup"><span data-stu-id="5f891-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="5f891-115">Chaque utilisateur peut remplacer les paramètres globaux en créant des paramètres utilisateur avec les mêmes clés.</span><span class="sxs-lookup"><span data-stu-id="5f891-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="5f891-116">Lorsque l’application demande les paramètres utilisateur effectif, l’API renvoie un ensemble de paramètres globaux fusionnés avec les paramètres utilisateur, avec chaque paramètre de l’utilisateur remplaçant la respectifs paramètre global si les clés sont les mêmes.</span><span class="sxs-lookup"><span data-stu-id="5f891-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="5f891-117">L’API peut aussi renvoyer uniquement les paramètres utilisateur, afin que les applications peuvent savoir quels paramètres sont remplacés.</span><span class="sxs-lookup"><span data-stu-id="5f891-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="5f891-118">Les opérations REST sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5f891-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="5f891-119">**Opération**</span><span class="sxs-lookup"><span data-stu-id="5f891-119">**Operation**</span></span>|<span data-ttu-id="5f891-120">**Description**</span><span class="sxs-lookup"><span data-stu-id="5f891-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="5f891-121">Obtenir les paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f891-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="5f891-122">Obtenir les paramètres utilisateur renvoie une liste des paramètres pour un utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f891-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="5f891-123">Obtenir les paramètres utilisateur</span><span class="sxs-lookup"><span data-stu-id="5f891-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="5f891-124">Obtenir le paramètre utilisateur renvoie un paramètre d’utilisateur unique.</span><span class="sxs-lookup"><span data-stu-id="5f891-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   

