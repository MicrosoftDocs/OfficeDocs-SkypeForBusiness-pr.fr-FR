---
title: Activer ou désactiver l’archivage dans Skype Entreprise Server
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Résumé : Découvrez comment activer ou désactiver l’archivage dans Skype Entreprise Server.'
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817594"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="4a339-103">Activer ou désactiver l’archivage dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4a339-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="4a339-104">**Résumé :** Découvrez comment activer ou désactiver l’archivage dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4a339-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="4a339-105">Activer ou désactiver l’archivage à l’aide du Panneau de contrôle</span><span class="sxs-lookup"><span data-stu-id="4a339-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="4a339-106">À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4a339-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="4a339-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4a339-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4a339-108">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="4a339-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="4a339-109">Sélectionnez la configuration de pool, de site ou globale appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4a339-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="4a339-110">Pour activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.</span><span class="sxs-lookup"><span data-stu-id="4a339-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="4a339-111">Pour activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.</span><span class="sxs-lookup"><span data-stu-id="4a339-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="4a339-112">Pour désactiver l’archivage pour la configuration, cliquez **sur Désactiver l’archivage.**</span><span class="sxs-lookup"><span data-stu-id="4a339-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="4a339-113">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4a339-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="4a339-114">Activer ou désactiver l’archivage à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a339-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="4a339-115">Vous pouvez également activer ou désactiver l’archivage à l’aide de l’cmdlet **Set-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="4a339-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="4a339-116">Par exemple, la commande suivante modifie tous les paramètres de configuration de l’archivage afin que seules les sessions de messagerie instantanée soient archivées.</span><span class="sxs-lookup"><span data-stu-id="4a339-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="4a339-117">La commande appelle l’cmdlet **Get-CsArchivingConfiguration** sans aucun paramètre afin de retourner tous les paramètres de configuration d’archivage actuellement utilisés dans l’organisation.</span><span class="sxs-lookup"><span data-stu-id="4a339-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="4a339-118">Cette collection est ensuite canaliser vers l’cmdlet **Where-Object,** qui sélectionne uniquement les paramètres pour lesquels la propriété EnableArchiving est égale à (-eq) « ImAndWebConf ».</span><span class="sxs-lookup"><span data-stu-id="4a339-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="4a339-119">La collection filtrée est ensuite canalë vers l';cmdlet **Set-CsArchivingConfiguration** qui prend chaque élément de la collection et modifie la valeur de EnableArchiving en « ImOnly » :</span><span class="sxs-lookup"><span data-stu-id="4a339-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
