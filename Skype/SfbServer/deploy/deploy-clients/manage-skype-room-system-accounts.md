---
title: Gestion des comptes Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b389efc-9685-42e9-9504-be437d20ff57
ms.collection: M365-voice
description: Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.
ms.openlocfilehash: 4c276d4acf0cf15df7689fa5c11a0e6e2cde785b
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012523"
---
# <a name="manage-skype-room-system-accounts"></a><span data-ttu-id="0e8cb-103">Gestion des comptes Skype Room System</span><span class="sxs-lookup"><span data-stu-id="0e8cb-103">Manage Skype Room System accounts</span></span>
 
<span data-ttu-id="0e8cb-104">Consultez cette rubrique pour apprendre à gérer les comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-104">Read this topic to learn how to manage Skype Room System accounts.</span></span> 

> [!NOTE]
> <span data-ttu-id="0e8cb-105">Salles d’équipes Microsoft est un autre produit avec des dépendances différents et des procédures de déploiement.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="0e8cb-106">Pour plus d’informations sur les espaces des équipes Microsoft, voir [vue d’ensemble de la gestion des](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [management overview](../../manage/skype-room-systems-v2/skype-room-systems-v2.md).</span></span>
  
## <a name="move-the-skype-room-system-account-between-pools"></a><span data-ttu-id="0e8cb-107">Déplacer le compte de système de salle Skype entre pools</span><span class="sxs-lookup"><span data-stu-id="0e8cb-107">Move the Skype Room System account between pools</span></span>

<span data-ttu-id="0e8cb-108">Si vous devez déplacer le compte système local de Skype à partir d’un seul Skype pour le pool de serveurs d’entreprise à un autre (par exemple, pendant les mises à jour), utilisez la commande suivante pour déplacer le pool de compte Skype salle système :</span><span class="sxs-lookup"><span data-stu-id="0e8cb-108">If you need to move the Skype Room System account from one Skype for Business Server pool to another (for example, during upgrades), use the following command to move the Skype Room System account pool:</span></span> 
  
```
Move-CsMeetingRoom -Identity LRS01 -Target "LYNCPool15-2.contoso.com"
```

## <a name="disable-the-skype-room-system-account-for-skype-for-business-services"></a><span data-ttu-id="0e8cb-109">Désactiver le compte de système de salle Skype pour Skype pour les services</span><span class="sxs-lookup"><span data-stu-id="0e8cb-109">Disable the Skype Room System account for Skype for Business services</span></span>

<span data-ttu-id="0e8cb-110">Si vous devez désactiver un système de salle Skype compte existant à partir de Skype pour les services sur un Skype pour le pool de serveurs d’entreprise, utilisez la commande suivante pour désactiver le compte :</span><span class="sxs-lookup"><span data-stu-id="0e8cb-110">If you need to disable an existing Skype Room System account from Skype for Business services on a Skype for Business Server pool, use the following command to disable the account:</span></span> 
  
```
Disable-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com
```

## <a name="optional-create-a-skype-room-system-administrator-group-in-active-directory"></a><span data-ttu-id="0e8cb-111">Facultatif : Créer un groupe d’administrateurs système de salle Skype dans Active Directory</span><span class="sxs-lookup"><span data-stu-id="0e8cb-111">Optional: Create a Skype Room System administrator group in Active Directory</span></span>

<span data-ttu-id="0e8cb-112">Chaque client Skype salle système qui rejoint le domaine pouvant être entièrement géré par un utilisateur de domaine disposant de droits d’administrateur local sur l’appliance Skype salle système PC.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-112">Each Skype Room System client that joins the domain can be fully managed by a domain user with local administrator rights on the Skype Room System appliance PC.</span></span> <span data-ttu-id="0e8cb-113">Par conséquent, vous pouvez créer le groupe des administrateurs dédié dans Active Directory et abandonner cette droits d’administration du groupe de définition du nouvel ordinateur Skype salle système.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-113">Therefore, you can create a dedicated administrators' group in Active Directory and give this group administrative rights during set up of the new Skype Room System machine.</span></span>
  

