---
title: Modifier une stratégie d’archivage existante dans Skype Entreprise Server
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Résumé : Découvrez comment modifier les stratégies d’archivage utilisateur pour Skype Entreprise Server.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817704"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="1bf55-103">Modifier une stratégie d’archivage existante dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1bf55-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="1bf55-104">**Résumé :** Découvrez comment modifier les stratégies d’archivage des utilisateurs pour Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1bf55-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="1bf55-105">Lorsque vous déployez Skype Entreprise Server pour la première fois, vous définissez des stratégies d’archivage initiales qui déterminent la façon dont l’archivage est implémenté pour les utilisateurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="1bf55-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="1bf55-106">Cette rubrique décrit comment gérer et modifier des stratégies.</span><span class="sxs-lookup"><span data-stu-id="1bf55-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="1bf55-107">Modifier les stratégies d’archivage à l’aide du Panneau de contrôle</span><span class="sxs-lookup"><span data-stu-id="1bf55-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="1bf55-108">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1bf55-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="1bf55-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1bf55-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="1bf55-110">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="1bf55-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="1bf55-111">Dans la liste des stratégies, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1bf55-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="1bf55-112">Pour modifier la stratégie pour l’ensemble de votre déploiement, cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1bf55-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="1bf55-113">Pour modifier la stratégie pour un seul site, cliquez sur le nom du site dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1bf55-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="1bf55-114">Pour modifier la stratégie pour un seul utilisateur ou groupe d’utilisateurs, cliquez sur l’utilisateur ou le groupe d’utilisateurs dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1bf55-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="1bf55-115">Dans la page **Modifier la stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1bf55-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="1bf55-116">Pour activer ou désactiver l’archivage interne de la stratégie, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="1bf55-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="1bf55-117">Pour activer ou désactiver l’archivage externe de la stratégie, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="1bf55-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="1bf55-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1bf55-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1bf55-119">Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie.</span><span class="sxs-lookup"><span data-stu-id="1bf55-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="1bf55-120">Pour plus d’informations, voir [Appliquer une stratégie d’archivage](apply-a-policy-to-users.md)aux utilisateurs dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1bf55-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="1bf55-121">Modifier les stratégies d’archivage à l’aide Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bf55-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="1bf55-122">Vous pouvez également modifier les stratégies d’archivage à l’aide Windows PowerShell cmdlet **Set-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="1bf55-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="1bf55-123">Activer les stratégies d’archivage</span><span class="sxs-lookup"><span data-stu-id="1bf55-123">Enable archiving policies</span></span>

<span data-ttu-id="1bf55-124">Pour activer l’archivage des sessions de communication internes, définissez la valeur du paramètre ArchiveInternal sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="1bf55-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="1bf55-125">Pour activer l’archivage des sessions de communication externes, définissez la valeur du paramètre ArchiveExternal sur True ($True) :</span><span class="sxs-lookup"><span data-stu-id="1bf55-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="1bf55-126">Pour activer l’archivage des sessions de communication internes et externes, définissez la valeur des paramètres ArchiveInternal et ArchiveExternal sur True :</span><span class="sxs-lookup"><span data-stu-id="1bf55-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="1bf55-127">Désactiver les stratégies d’archivage</span><span class="sxs-lookup"><span data-stu-id="1bf55-127">Disable archiving policies</span></span>

<span data-ttu-id="1bf55-128">Pour désactiver complètement l’archivage, définissez la valeur des paramètres ArchiveInternal et ArchiveExternal sur False ($False) :</span><span class="sxs-lookup"><span data-stu-id="1bf55-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
