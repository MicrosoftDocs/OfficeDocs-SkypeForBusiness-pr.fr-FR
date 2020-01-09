---
title: Activation ou désactivation de l’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Résumé : Découvrez comment activer ou désactiver l’archivage dans Skype entreprise Server.'
ms.openlocfilehash: 603ffece7d3b0dabe27ee95d27eaee1e84f48fb9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991579"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="6fb0d-103">Activation ou désactivation de l’archivage dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="6fb0d-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="6fb0d-104">**Résumé :** Découvrez comment activer ou désactiver l’archivage dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="6fb0d-105">Activer ou désactiver l’archivage à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="6fb0d-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="6fb0d-106">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="6fb0d-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6fb0d-108">Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6fb0d-109">Sélectionnez la configuration de pool, de site ou globale appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6fb0d-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="6fb0d-110">Afin d’activer l’archivage seulement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="6fb0d-111">Pour activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="6fb0d-112">Afin de désactiver l’archivage pour la configuration, cliquez sur **Désactiver l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="6fb0d-113">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="6fb0d-114">Activer ou désactiver l’archivage à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fb0d-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="6fb0d-115">Vous pouvez activer ou désactiver l’archivage à l’aide de l’applet de commande **Set-CsArchivingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="6fb0d-116">Par exemple, la commande suivante modifie tous les paramètres de configuration de l’archivage pour que seules les sessions de messagerie instantanée soient archivées.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="6fb0d-117">Pour cela, la commande appelle d’abord l’applet de commande **Get-CsArchivingConfiguration** sans paramètre afin de retourner une collection de tous les paramètres de configuration de l’archivage utilisés dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="6fb0d-118">Cette collection est alors redirigée vers l’applet de commande **Where-Object** qui sélectionne uniquement les paramètres dont la propriété EnableArchiving est égale à (-eq) « ImAndWebConf ».</span><span class="sxs-lookup"><span data-stu-id="6fb0d-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="6fb0d-119">La collection filtrée est ensuite redirigée vers l’applet de commande **Set-CsArchivingConfiguration** qui extrait chaque élément de la collection et définit la valeur de la propriété EnableArchiving sur « ImOnly » :</span><span class="sxs-lookup"><span data-stu-id="6fb0d-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
