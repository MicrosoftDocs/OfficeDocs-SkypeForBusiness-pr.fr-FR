---
title: Modification d’une stratégie d’archivage existante dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Résumé : Découvrez comment modifier les stratégies d’archivage des utilisateurs pour Skype entreprise Server.'
ms.openlocfilehash: 010365b5805517db8f40aa7e3e839fdb15115c06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818986"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="f7747-103">Modification d’une stratégie d’archivage existante dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="f7747-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="f7747-104">**Résumé :** Découvrez comment modifier les stratégies d’archivage des utilisateurs pour Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f7747-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="f7747-105">Lorsque vous déployez Skype entreprise Server pour la première fois, vous configurez les stratégies d’archivage initial qui déterminent la façon dont l’archivage est implémenté pour les utilisateurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="f7747-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="f7747-106">Cette rubrique explique comment gérer et modifier des stratégies.</span><span class="sxs-lookup"><span data-stu-id="f7747-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="f7747-107">Modifier des options d’archivage via le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="f7747-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="f7747-108">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f7747-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f7747-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f7747-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f7747-110">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="f7747-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="f7747-111">Dans la liste des stratégies, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="f7747-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="f7747-112">Pour modifier la stratégie pour l’ensemble de votre déploiement, cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f7747-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="f7747-113">Pour modifier la stratégie pour un seul site, cliquez sur le nom du site dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f7747-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="f7747-114">Pour modifier la stratégie pour un seul utilisateur ou groupe d’utilisateurs, cliquez sur l’utilisateur ou le groupe d’utilisateurs dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f7747-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f7747-115">Dans la page **Modifier la stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f7747-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="f7747-116">Pour activer ou désactiver l’archivage interne de la stratégie, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="f7747-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="f7747-117">Pour activer ou désactiver l’archivage externe de la stratégie, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="f7747-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="f7747-118">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="f7747-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f7747-119">Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie.</span><span class="sxs-lookup"><span data-stu-id="f7747-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="f7747-120">Pour plus d’informations, reportez-vous [à appliquer une stratégie d’archivage aux utilisateurs de Skype entreprise Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="f7747-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="f7747-121">Modifier les stratégies d’archivage via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7747-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="f7747-122">Vous pouvez également modifier les stratégies d’archivage via l’applet de commande **Set-CsArchivingPolicy** de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f7747-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="f7747-123">Activer des stratégies d’archivage</span><span class="sxs-lookup"><span data-stu-id="f7747-123">Enable archiving policies</span></span>

<span data-ttu-id="f7747-124">Pour activer l’archivage des sessions de communication internes, affectez la valeur True ($True) au paramètre ArchiveInternal :</span><span class="sxs-lookup"><span data-stu-id="f7747-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="f7747-125">Pour activer l’archivage des sessions de communication externes, affectez la valeur True ($True) au paramètre ArchiveExternal :</span><span class="sxs-lookup"><span data-stu-id="f7747-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="f7747-126">Pour activer l’archivage des sessions de communication interne et externe, définissez la valeur des paramètres ArchiveInternal et ArchiveExternal sur true :</span><span class="sxs-lookup"><span data-stu-id="f7747-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="f7747-127">Désactiver des stratégies d’archivage</span><span class="sxs-lookup"><span data-stu-id="f7747-127">Disable archiving policies</span></span>

<span data-ttu-id="f7747-128">Pour désactiver complètement l’archivage, affectez la valeur False ($False) aux deux propriétés ArchiveInternal et ArchiveExternal :</span><span class="sxs-lookup"><span data-stu-id="f7747-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
