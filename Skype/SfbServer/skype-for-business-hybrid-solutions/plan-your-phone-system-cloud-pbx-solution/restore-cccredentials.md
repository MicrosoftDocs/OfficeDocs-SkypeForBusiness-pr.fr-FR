---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 'L’applet de connexion de restauration des informations d’identification cc : restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector.'
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003244"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="18dca-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="18dca-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="18dca-104">L’applet de connexion de restauration des informations d’identification cc : restaure toutes les informations d’identification du déploiement actuel de Skype entreprise version Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="18dca-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="18dca-105">Cette cmdlet s’applique à Skype entreprise version Cloud Connector 2,1.</span><span class="sxs-lookup"><span data-stu-id="18dca-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="18dca-106">Description détaillée</span><span class="sxs-lookup"><span data-stu-id="18dca-106">Detailed Description</span></span>

<span data-ttu-id="18dca-107">L’applet de commande Restore-CcCredentials nettoie toutes les informations d’identification et vous invite à entrer à nouveau toutes les informations d’identification utilisées pour le déploiement actuel de Skype entreprise Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="18dca-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="18dca-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="18dca-108">Parameters</span></span>

<span data-ttu-id="18dca-109">Aucune</span><span class="sxs-lookup"><span data-stu-id="18dca-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="18dca-110">Types d’entrées</span><span class="sxs-lookup"><span data-stu-id="18dca-110">Input Types</span></span>

<span data-ttu-id="18dca-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="18dca-111">None.</span></span> <span data-ttu-id="18dca-112">L’applet de commande Restore-CcCredentials n’accepte pas les entrées pipelines.</span><span class="sxs-lookup"><span data-stu-id="18dca-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="18dca-113">Types de retours</span><span class="sxs-lookup"><span data-stu-id="18dca-113">Return Types</span></span>

<span data-ttu-id="18dca-114">Aucun.</span><span class="sxs-lookup"><span data-stu-id="18dca-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="18dca-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="18dca-115">Example</span></span>

<span data-ttu-id="18dca-116">L’exemple suivant restaure toutes les informations d’identification du déploiement actuel du connecteur Cloud :</span><span class="sxs-lookup"><span data-stu-id="18dca-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="18dca-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18dca-117">See also</span></span>

[<span data-ttu-id="18dca-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="18dca-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="18dca-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="18dca-119">Set-CcCredential</span></span>](set-cccredential.md)
  

